---
id: unityscripting_monobehaviourmethod
title: نقش متد در اسکریپت MonoBehaviour
slug: /unityscripting/monobehaviourmethod
---

هر کلاس یونیتی از فیلدها و متدها تشکیل شده است. ملاحظه کردیم که در قسمت فیلدها تنها عملی که می‌توان انجام داد تعریف فیلد و نهایتاً مقداردهی آن است. بنابراین هر عمل دیگری که قصد پیاده‌سازی آن در اسکریپت را داریم باید در متد تعریف شود.

متدهایی که در اسکریپت‌های MonoBehaviour تعریف می‌کنیم دو دسته هستند:

1. متدهای MonoBehaviour که در چرخه‌ی عمر گیم آبجکتی که اسکریپت به آن متصل خواهد شد روی می‌دهند. به عنوان مثال دو متد `Start` و `Update` که به صورت پیش‌فرض در هر اسکریپت جدید قرار داده می‌شوند پس از اتصال اسکریپت به عنوان کامپوننت به گیم‌آبجکت به ترتیب «در اولین فریم حضور گیم آبجکت در صحنه» و «در هر فریم از حضور گیم آبجکت در صحنه» اجرا خواهند شد. در واقع متدهای MonoBehaviour در نقش پل ارتباطی کدهای اسکریپت‌نویس را در محیط بازی اجرا می‌کنند. به وسیله‌ی متدهای MonoBehaviour می‌توان اجرای کدهای دلخواه خود را وارد چرخه‌ی عمر (Life Cycle) گیم‌آبجکت‌ها کرده و بالتبع صحنه را تحت تاثیر آن‌ها قرار داد. علاوه بر این دو متد، متدهای MonoBehaviour دیگری نیز وجود دارند که در صورت لزوم می‌توان به اضافه کردن دستی آن‌ها اقدام نمود.

2. متدهایی که توسط اسکریپت‌نویس نوشته می‌شوند. این متدها امکان فراخوانی مستقیم در محیط بازی را ندارند؛ مگر آن که توسط یکی از متدهای MonoBehaviour فراخوانده شوند.

## چرخه‌ی عمر (life cycle) گیم آبجکت

چرخه‌ی عمر یک گیم آبجکت مجموعه‌ای از رویدادهایی است که برای گیم آبجکت از لحظه‌ی ایجاد شدن تا از بین رفتن رخ می‌دهد. به ازای هر کدام از این رویدادها، یک متد فراخوانی می‌شود که در صورت نیاز به اجرای یک کد در آن رویداد، متد مربوطه را به صورت دستی به اسکریپت MonoBehaviour اضافه می‌کنیم. فلوچارت مقابل چرخه‌ی عمر گیم آبجکت را نشان می‌دهد:

![image](/img/unity_life_cycle.png)

## بررسی متدهای پراستفاده‌ی MonoBehaviour

در ادامه پراستفاده‌ترین متدهای MonoBehaviour و رویدادی که موجب فراخوانی آن متد می‌شود را به ترتیب فراخوانی بررسی می‌کنیم و کاربرد معمول آن‌ها را بیان می‌کنیم. هر کدام از این متدها پس از آن فراخوانی می‌شوند که تمام متدهای مرحله بالاترشان در تمامی کامپوننت‌های گیم‌آبجکت فراخوانی شده باشند. متد `Awake` تنها متدی است که در صورت غیرفعال بودن کامپوننت نیز اجرا می‌شود.

![image](/img/monobehaviour_useful_methods.png)

### متدهای برخورد و نفوذ

در اغلب بازی‌های ویدیویی برخورد دو شی با یکدیگر و یا نفوذ یک شی در شی‌ای دیگر از جمله رویدادهای متعارفی بوده که منجر به رخ دادن اتفاقی خاص (مثل تصادف اتومبیل، باز شدن در خانه و…) در چارچوب قوانین بازی می‌شوند؛ بنابراین متدهای برخورد (`OnColliderXXX`) و نفوذ (`OnTriggerXXX`) که هنگام رخ دادن این رویدادها فراخوانی می‌شوند از پرکاربردترین متدهای MonoBehaviour مورداستفاده در اسکریپت‌نویسی یونیتی هستند.

برای تشخیص برخورد/نفوذ دو گیم آبجکت به برخورد/نفوذ colliderهای آن‌ها به یکدیگر استناد می‌شود. در حالت پیش‌فرض که پراپرتی Is Trigger کامپوننت Collider غیرفعال است، collider قابلیت نفوذپذیری نداشته و تنها امکان برخورد به آن وجود دارد (به عنوان مثال برخورد دو سنگ به یکدیگر)؛ در این حالت برخورد یک collider ثانویه به collider گیم آبجکت منجر به فراخوانی متدهای `OnColliderXXX` متصل به گیم آبجکت می‌شود.

با فعال کردن پراپرتی Is Trigger امکان نفوذ به collider توسط سایر colliderها به وجود می‌آید. از این قابلیت بیشتر برای تشخیص ورود به یک حریم خاص استفاده می‌شود (به عنوان مثال افتادن یک سنگ به درون دریا). در این حالت هنگام نفوذ یک collider به collider گیم آبجکت، متدهای `OnTriggerXXX` متصل به گیم آبجکت فراخوانی می‌شوند.

:::note نکته
هرکدام از متدهای برخورد و نفوذ دارای دو نسخه‌ی دوبعدی و سه‌بعدی هستند که متناسب با دوبعدی یا سه‌بعدی بودن collider مربوطه فراخوانی می‌شوند. متدهای مربوط به موتور فیزیک دوبعدی در جلوی نام خود و نوع داده‌ی ورودی یک عبارت 2D اضافه دارند. به عنوان مثال:
:::

![image](/img/monobehaviour_physics_2d_methods.png)

:::note نکته
برای تشخیص برخورد/نفوذ لازم است که حداقل یکی از گیم آبجکت‌ها متناسب با دوبعدی یا سه‌بعدی بودن colliderاش دارای کامپوننت Rigidbody یا Rigidbody 2D باشد. چرا که هندل کردن collision eventها یکی از وظایف rigidbody است.
:::

متدهای برخورد و نفوذ دوبعدی عبارتند از:

![image](/img/monobehaviour_collision_and_trigger_methods.png)

*برای دسترسی به گیم آبجکتی که other متعلق به آن است از dot operator و پراپرتی gameObject استفاده می‌کنیم.*

:::note تمرین
با استفاده از اضافه کردن اسکریپت زیر به چندین گیم آبجکت دوبعدی، رویدادهای برخورد صورت گرفته را بررسی کنید.

```clike
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class CollisionMethodsTest : MonoBehaviour
{
    
    private string myString;
    
    private void Awake()
    {
        myString = gameObject.name;
    }
    
    private void OnCollisionEnter2D(Collision2D other)
    {
        Debug.Log("OnCollisionEnter2D " + myString);
    }
    
    private void OnCollisionStay2D(Collision2D other)
    {
        Debug.Log("OnCollisionStay2D " + myString);
    }
    
    private void OnCollisionExit2D(Collision2D other)
    {
        Debug.Log("OnCollisionExit2D " + myString);
    }
    
    private void OnTriggerEnter2D(Collider2D other)
    {
        Debug.Log("OnTriggerEnter2D " + myString);
    }
    
    private void OnTriggerStay2D(Collider2D other)
    {
        Debug.Log("OnTriggerStay2D " + myString);
    }
    
    private void OnTriggerExit2D(Collider2D other)
    {
        Debug.Log("OnTriggerExit2D " + myString);
    }
    
}
```
:::