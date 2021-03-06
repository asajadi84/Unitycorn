---
id: unityscripting_monobehaviourfield
title: نقش فیلد در اسکریپت MonoBehaviour
slug: /unityscripting/monobehaviourfield
---

فیلد در کلاس سی شارپ فضایی از حافظه است که می‌تواند به ازای هر شی ساخته شده از روی کلاس در مکان متفاوتی از حافظه باشد و بنابراین مقدار متفاوتی را در خود ذخیره کند.

## انواع فیلد در سی شارپ

فیلدها در سی شارپ به دو دسته تقسیم می‌شوند: فیلدهای value-type و فیلدهای reference-type

### 1- فیلدهای value-type

فیلدهایی که نوع داده (دیتاتایپ) آن‌ها value-type باشد در این دسته قرار می‌گیرند. به طور کلی تمام نوع داده‌های اصلی سی شارپ (مانند int، float، bool و…) از نوع value-type هستند.

در این دسته از فیلدها مقدار داده شده به فیلد به صورت مستقیم در حافظه‌ای که در stack برای آن در نظر گرفته شده قرار می‌گیرد. stack به بخشی از RAM گفته می‌شود که مقادیر ایستا در آن قرار می‌گیرند.

در داده‌های value-type اگر مقدار یک متغیر با عملگر انتساب (`==`) به متغیر دیگری از همان نوع نسبت داده شود ابتدا این مقدار در نقطه‌ی دیگری از حافظه‌ی stack کپی شده و سپس به متغیر دوم نسبت داده می‌شود. بنابراین با تغییر مقدار متغیر دوم، مقدار متغیر اول دچار تغییر نمی‌شود:

![image](/img/unity_value_type_fields.png)

فیلدهای value-type می‌توانند بدون آن که از روی کلاس آن‌ها نمونه‌سازی صورت گرفته باشد مقداردهی اولیه شوند. در این صورت این مقدار به عنوان مقدار پیش‌فرض فیلد به شمار می‌رود. این مقدار می‌تواند به ازای هر شی ساخته شده تغییر کند که در چنین حالتی مقدار ثانویه بر مقدار اولیه ارجحیت دارد.

کاربرد اصلی فیلدهای value-type در اسکریپت‌های MonoBehaviour جلوگیری از hard coding می‌باشد. hard coding به این معناست که مقادیر استفاده شده در اسکریپت به صورت مستقیم در کد نوشته شده باشند. این عمل خوانایی کد را کاهش داده و امکان ویرایش آن را دشوار می‌کند. به همین جهت به جای نوشتن مستقیم مقادیر در درون کد، ابتدا آن‌ها را در فیلدهای کلاس تعریف کرده و سپس از نام فیلد استفاده می‌کنند که به این عمل soft coding گفته می‌شود:

```clike
//Hard Coding
class ExampleClass1 : MonoBehaviour {
    
    void Update() {
        ExampleMoveMethod(10f);
    }
}

//Soft Coding
class ExampleClass2 : MonoBehaviour {
    
    public float carSpeed = 10f;
    
    void Update() {
        ExampleMoveMethod(carSpeed);
    }
}
```

در این کد در کلاس `ExampleClass2` سرعت حرکت ماشین به یک فیلد وابسته شده است که امکان مدیریت آن را ساده‌تر و سریع‌تر می‌کند.

soft coding علاوه بر مزایایی که گفته شد امکان این را فراهم می‌کند که بتوان به ازای هر شی، مقادیر متفاوتی را در کدهای مشابه وارد نمود. برای مثال اگر قصد داشته باشیم در یک صحنه‌ی بازی دو ماشین با سرعت 20 متر در ثانیه و 30 متر در ثانیه قرار دهیم در صورتی که مقید به soft coding نباشیم باید دو اسکریپت جداگانه تعریف کنیم که یکی حرکت با سرعت 20 متر در ثانیه و دیگری حرکت با سرعت 30 متر بر ثانیه را به گیم آبجکتی که به آن متصل می‌شود اضافه کند؛ اما برای پیاده‌سازی صحیح این مکانیک کافی است اسکریپتی بنویسیم که دارای فیلدی به نام `carSpeed` باشد و به گیم‌آبجکتی که متصل می‌شود سرعت `carSpeed` متر در ثانیه را اضافه کند. سپس این اسکریپت را به هر دو گیم آبجکت نسبت داده و به ازای هر گیم آبجکت مقدار دلخواه را به آن نسبت دهیم. hard coding باعث کاهش انعطاف و کاربردی بودن کد می‌شود و باید تا حد ممکن از آن اجتناب کرد.

![image](/img/hard_coding_vs_soft_coding.png)

### 2- فیلدهای reference-type

فیلدهایی که نوع داده‌ی آن‌ها از نوع reference-type باشد در این دسته قرار می‌گیرند. هر نوع داده‌ای که برای مقداردهی شدن نیاز به نمونه‌سازی داشته باشد از نوع reference-type است که از بین آن‌ها می‌توان کلاس‌های تعریف شده توسط توسعه‌دهنده‌ی بازی و کلاس‌های کامپوننت‌های یونیتی (که در فضای نام `UnityEngine`) قرار دارند را نام برد.

در این دسته از فیلدها مقدار داده شده به فیلد درون قسمتی از حافظه‌ی RAM به نام heap قرار می‌گیرد. heap به بخشی از RAM گفته می‌شود که مقادیر پویا در آن قرار می‌گیرند. بعد از قرار گرفتن مقدار (شی ساخته شده از روی کلاس) در heap، آدرس آن نقطه از heap در حافظه‌ی stack ذخیره شده و به فیلد نسبت داده می‌شود. بنابراین اگر مقدار یک فیلد reference-type با عملگر انتساب (`==`) به فیلد دیگری نسبت داده شود، به فیلد دوم حافظه‌ای در stack اختصاص می‌یابد که در آن نیز آدرس حافظه‌ی heap قرار می‌گیرد. در نتیجه هر دو فیلد به یک نقطه از حافظه‌ی heap و در واقع یک شی اشاره می‌کنند. پس با تغییر اعضای شی از طریق هر کدام از فیلدها، شی اصلی تغییر می‌کند:

![image](/img/unity_reference_type_fields.png)

فیلدهای reference-type مقدار شی را در خود ذخیره نمی‌کنند و تنها آدرس آن‌ها در حافظه‌ی heap را نگهداری می‌کنند که به این عمل، اشاره کردن فیلد به شی گفته می‌شود.

:::note نکته
در مقداردهی اولیه، فیلدهای value-type تنها می‌توانند مقادیر ثابت و یا استاتیک را به عنوان مقدار در خود ذخیره کرده و فیلدهای reference-type نیز تنها می‌توانند مقادیر استاتیک را در خود ذخیره کنند (چرا؟). در صورت نیاز به مقداردهی فیلدها با سایر مقادیر لازم است که مقداردهی در یکی از متدهای چرخه‌ی عمر گیم آبجکت صورت بگیرد که در آینده به این متدها خواهیم پرداخت.
:::

:::note نکته
نوع داده‌ی srting با وجود این که reference-type است اما رفتاری شبیه به نوع داده‌های value-type دارد. دلیل reference-type بودن string به امکان زیاد بودن حجم آن باز می‌گردد که برای جلوگیری از پر کردن احتمالی حافظه‌ی stack، در حافظه‌ی heap ذخیره می‌شود.
:::

## سریالایز (serialize) کردن فیلدها در سی شارپ

![image](/img/unity_field_serialization.png)

ادیتور یونیتی برای امکان انجام مقداردهی ثانویه از قابلیتی به نام سریالایز کردن فیلدها بهره می‌برد. در این قابلیت امکان مشاهده و ویرایش فیلدهایی که شرایط خاصی را داشته باشند به صورت بصری در جعبه‌ی کامپوننت موجود در Inspector وجود دارد. این شرایط عبارتند از:

* نوع داده‌ی فیلد از نوع داده‌های قابل پشتیبانی برای سریالایز شدن باشد. این نوع داده‌ها عبارتند از: نوع داده‌های value-type، نوع داده‌ی `GameObject`، نوع داده‌های کامپوننت و آرایه‌های تمامی موارد ذکر شده و enumها (برای اطلاعات بیشتر به https://docs.unity3d.com/ScriptReference/SerializeField مراجعه کنید).

* سطح دسترسی (access modifier) فیلد مربوطه public باشد. به طور پیش‌فرض فیلدهای public در Inspector نمایش داده شده و فیلدهایی که سطح دسترسی دیگری دارند نمایش داده نمی‌شوند.

ذکر این نکته ضروری است که اگر فیلدی مقداردهی اولیه شده باشد و در Inspector نیز مقدار جدیدی به آن داده شود، مقدار داخل Inspector به مقدار اولیه ارجحیت خواهد داشت. در صورت تمایل به بازگشت مقادیر تغییر داده شده به مقدار اولیه‌شان در اسکریپت، بر روی آیکون چرخ دنده کامپوننت کلیک کرده و گزینه‌ی Reset را انتخاب می‌کنیم.

### تغییر وضعیت نمایش فیلد در inspector

همانطور که بررسی کردیم به طور پیش‌فرض در Inspector فیلدهای private غیرقابل مشاهده و فیلدهای public قابل مشاهده‌اند. در صورتی که بخواهیم یک فیلد private را نمایش دهیم و یا یک فیلد public را مخفی کنیم از روش‌های زیر استفاده می‌کنیم:

* برای نمایش یک فیلد private (و یا سایر سطوح دسترسی که باعث سریالایز نشدن فیلد می‌شوند) در Inspector به آن صفت `[SerializeField]` را می‌دهیم:

```clike
[SerializeField]
private int myInt1; //will be shown in the inspector

private int myInt2; //will be not shown in the inspector
```

* برای مخفی کردن یک فیلد public در Inspector نیز می‌توان از صفت `[HideInInspector]` استفاده کرد:

```clike
public int myInt3; //will be shown in the inspector

[HideInInspector]
public int myInt4; //will be not shown in the inspector
```

## اشاره کردن به کامپوننت‌ها و قرار دادن کامپوننت در فیلد

می‌دانیم هر کامپوننت یونیتی یک شی (reference-type) از نوع داده‌ای همنام کامپوننت است که این نوع داده‌ها در فضای نام `UnityEngine` قرار دارند (برای مثال یک کامپوننت Transform متصل به یک گیم آبجکت در واقع شی‌ای از نوع `Transform` است). خاصیت اشاره کردن فیلدهای reference-type باعث می‌شود تا بتوان در هر نقطه از هر اسکریپتی که احتیاج داریم به یک کامپوننت خاص موجود در صحنه دسترسی پیدا کنیم، نوع داده‌ای همنام کامپوننت تعریف کرده و به سپس به کامپوننت موردنظر اشاره کرده و حتی آدرس آن را در یک فیلد ذخیره کنیم.

معمولاً برای اشاره به یک کامپوننت خاص در یونیتی (که شی‌ای با نوع داده‌ای همنام کامپوننت است) از متد ژنریک `GetComponent<T>` استفاده می‌شود. این متد که بر روی اشیایی از نوع `GameObject` (هر گیم آبجکت در یونیتی یک شی از نوع `GameObject` است) صدا زده می‌شود می‌تواند به آدرس کامپوننت T متصل به گیم آبجکت اشاره کند.

:::note نکته
متد ژنریک (generic) در سی شارپ متدی است که علاوه بر امکان گرفتن مقدار به عنوان ورودی، امکان دریافت یک یا چندین ورودی دیتاتایپ را نیز دارد. سپس متد می‌تواند با توجه به دیتاتایپ وارد شده، متغیرهای محلی از آن نوع ساخته و خروجی مناسب را به کاربر تحویل دهد. همانند مقادیری که در بین ( و ) به متد وارد می‌شود، دیتاتایپ‌های متدهای ژنریک نیز در بین کاراکترهای < و > قرار می‌گیرند.
:::

```clike
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class TestScript : MonoBehaviour
{
    
    public GameObject testGameObject;
    public RigidBody2D testRigidBody2D;
    
    // Use this for initialization
    void Start ()
    {
        testRigidBody2D = testGameObject.GetComponent<RigidBody2D>();
    }
}
```

:::note نکته
کامپوننت Transform تنها کامپوننتی است که می‌توان برای اشاره به آن به جای نوشتن عبارت `GetComponent<Transform>` از عبارت کوتاه شده‌ی `Transform` نیز استفاده نمود. تا قبل از ورژن 5 یونیتی این امکان برای تمام کامپوننت‌ها وجود داشت. همچنین متد `GetComponent` متدی هزینه‌بر است و به همین جهت توصیه می‌شود تنها یک بار در متد `Awake` کامپوننت را در فیلدی از جنس کامپوننت قرار داده و در سایر قسمت‌های کد به آن فیلد اشاره شود. به این عمل cache کردن گفته می‌شود.
:::

همان‌طور که در کد بالا مشاهده می‌شود برای استفاده از متد `GetComponent<T>` ابتدا باید گیم آبجکتی که کامپوننت به آن متصل است را به کد معرفی کنیم. برای انجام این کار بسته به وضعیت گیم آبجکت می‌توان از یکی از سه روش زیر استفاده کرد:

1. اگر گیم آبجکتی که قصد اشاره به آن را داریم گیم آبجکتی باشد که اسکریپت ما به آن متصل خواهد شد: استفاده از کلمه‌ی کلیدی `gameObject` (g حرف کوچک است). این کلمه‌ی کلیدی به گیم آبجکتی که کامپوننت به آن متصل شده است اشاره می‌کند و معادل کلمه‌ی کلیدی `this` در سی شارپ است. البته نوشتن این کلمه‌ی کلیدی اختیاری است و تنها با نوشتن متد `GetComponent<T>` نیز می‌توان به کامپوننت‌ها دسترسی پیدا کرد.

2. اگر گیم آبجکتی که قصد اشاره به آن را داریم نام مشخصی در صحنه دارد: استفاده از متد `GameObject.Find(“Example”)` که با استفاده از آن می‌توان به گیم آبجکتی که در صحنه وجود دارد و نامش Example است دسترسی پیدا کرد.

3. تعریف فیلدی (با قابلیت سریالایز شدن) از نوع داده‌ی کامپوننت و سپس drag کردن گیم‌آبجکت حاوی کامپوننت موردنظر از لیست hierarchy بر روی فیلد در Inspector.

```clike
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class TestScript : MonoBehaviour
{
    //Case 1
    private GameObject testGameObject1;
    
    //Case 2
    private GameObject testGameObject2;
    
    //Case 3
    private GameObject testGameObject3;
    
    // Use this for initialization
    void Start ()
    {
        //Case 1
        testGameObject1 = gameObject;
        
        //Case 2
        testGameObject2 = GameObject.Find("Example");
        
        //Case 3
        //In this case, we drag the game object from the hierarchy to the field name in inspector
    }
}
```