---
id: csharp_consoleappexamples
title: چند مثال تحت کنسول
slug: /csharp/consoleappexamples
---

در این قسمت تعدادی برنامه‌ی تحت کنسول سی شارپ را برای مرور مطالبی که توضیح داده شد بررسی می‌کنیم.

## برنامه‌ی تشخیص مضرب بودن دو عدد نسبت به هم

این برنامه دو عدد به عنوان ورودی دریافت کرده و تشخیص می‌دهد که آیا یکی مضرب دیگری هست یا خیر:

```clike
using System;

namespace ConsoleApplication1
{
    internal class Program
    {
        public static void Main(string[] args)
        {
            int a, b;
            
            Console.WriteLine("Enter the first number:");
            a = Convert.ToInt32(Console.ReadLine());
            
            Console.WriteLine("Enter the second number:");
            b = Convert.ToInt32(Console.ReadLine());
            
            if (IsOneMultipleOfTheOther(a, b))
            {
                Console.WriteLine("One number is multiple of the other one.");
            }
            else
            {
                Console.WriteLine("None of the numbers are mulitiple of the other one.");
            }
        }
        
        public static bool IsOneMultipleOfTheOther(int x, int y)
        {
            if (x % y == 0 || y % x == 0)
            {
                return true;
            }
                
            return false;
        }
    }
}
```

از اصلی‌ترین ویژگی‌های کد که در نگاه اول به نظر می‌رسد وجود متدی به نام `IsOneMultipleOfTheOther` (آیا یکی از اعداد مضرب دیگری است؟) می‌باشد که دو ورودی عدد صحیح به نام‌های `x` و `y` دریافت می‌کند و خروجی آن از نوع `bool` می‌باشد. این متد به دلیل وارد نشدن به مباحث شی‌گرایی به صورت `static` تعریف شده است.

درون این متد یک if statement تعریف شده است که اگر باقیمانده‌ی عدد `x` بر `y` برابر `0` یا باقیمانده‌ی `y` بر `x` برابر `0` بود مقدار صحیح و در غیر این صورت مقدار غلط بازگردانده شود.

در بدنه‌ی متد اصلی برنامه ابتدا دو عدد صحیح به نام‌های `a` و `b` تعریف شده‌اند. سپس از کاربر خواسته می‌شود که عدد اول و دوم را وارد کند. این عمل با دستور `Console.ReadLine();` انجام می‌شود. از آن‌جا که داده‌ی دریافتی از این طریق از نوع `string` بوده و پردازش بر روی رشته امکان‌پذیر نیست، کل این دستور را در ورودی متد `Convert.ToInt32` قرار می‌دهیم. این از متد وظیفه‌ی تبدیل رشته به نوع داده‌ی `int` (در صورت امکان) را بر عهده دارد.

سپس در سطر 17 یک if statement قرار داده شده است که ورودی آن، خروجی متد `IsOneMultipleOfTheOther` می‌باشد. بر همین اساس بسته به خروجی این متد، متن مناسب در کنسول چاپ خواهد شد.

## برنامه‌ی به دست آوردن ب.م.م دو عدد

این برنامه دو عدد دریافت کرده و ب.م.م (بزرگ‌ترین مقسوم‌علیه مشترک) آن دو را به دست می‌آورد:

```clike
using System;

namespace ConsoleApplication1
{
    internal class Program
    {
        public static void Main(string[] args)
        {
            int a, b;
            
            Console.WriteLine("Enter the first number:");
            a = Convert.ToInt32(Console.ReadLine());
            
            Console.WriteLine("Enter the second number:");
            b = Convert.ToInt32(Console.ReadLine());
            
            Console.WriteLine("The GCD is: " + GreatestCommonDivisor(a, b));
        }
            
        public static int GreatestCommonDivisor(int x, int y)
        {
            int n = 0;
            
            for (int i = x; i >= 1; i--)
            {
                if (x % i == 0 && y % i == 0)
                {
                    n = i;
                    break;
                }
            }
            
            return n;
        }
    }
}
```

متد `GreatestCommonDivisor` که در خارج از بدنه‌ی متد اصلی است وظیفه‌ی محاسبه‌ی ب.م.م دو عددی که به آن داده می‌شود را بر عهده دارد. در این متد ابتدا متغیری به نام `n` تعریف می‌شود. سپس حلقه‌ای معکوس در این متد (سطر 24) از یکی از اعداد وارد شده به متد به صورت منفی شروع به کنتور انداختن می‌کند. در هر مرحله دو عدد وارد شده به متد تقسیم بر عدد کنتور حلقه (`i`) می‌شوند. در حالتی که باقیمانده‌ی تقسیم هر دو عدد بر `i` برابر صفر بشود برنامه `i` را در متغیر `n` قرار داده و از حلقه خارج می‌شود. در نهایت مقدار `n` از متد بازگردانده می‌شود.

## برنامه‌ی چاپ الگوی مثلثی با کاراکتر ستاره

این برنامه الگوی زیر را در کنسول چاپ می‌کند:

![image](/img/csharp_star_pattern.png)

```clike
using System;

namespace ConsoleApplication1
{
    internal class Program
    {
        public static void Main(string[] args)
        {
            for (int i = 1; i <= 5; i++)
            {
                for (int j = 0; j < i; j++)
                {
                    Console.Write("*");
                }
                Console.Write("\n");
            }
        }
    }
}
```

در این برنامه از دو حلقه‌ی تودرتو استفاده شده است. حلقه‌ی بیرونی از 1 تا 5 کنتور می‌اندازد و مقدار را در متغیر i ذخیره می‌کند. در هر بار اجرای حلقه‌ی بیرونی، حلقه‌ی درونی هم از 0 تا i-1 کنتور می‌اندازد (یعنی i بار) و به ازای هر بار کنتور انداختن یک ستاره در کنسول چاپ می‌کند. در نهایت بعد از هر بار اجرا شدن حلقه‌ی درونی، یک لاین بریک هم در کنسول چاپ می‌شود تا در نهایت این الگو حاصل شود.

در واقع ترتیب کاراکترهایی که در کنسول چاپ می‌شود به صورت زیر است:

![image](/img/star_pattern_linear_sequence.png)

قرار گیری این توالی از کاراکترها در کنار یکدیگر باعث ایجاد الگوی فوق می‌شود. به همین جهت به جای استفاده از متد معمول WriteLine که هر نتیجه را در یک سطر چاپ می‌کند از متد Write استفاده کرده‌ایم که نتیجه‌ها را به دنبال هم چاپ می‌کند.

### روش کلی حل مسئله‌های مرتبط با رسم الگوی هندسی

:::note نکته
هنگام رسم اشکال با استفاده از کاراکتر (ASCII art) فونتی که خروجی را نمایش می‌دهد باید monospaced باشد. monospaced بودن فونت به این معناست که تمام کاراکترهای آن فونت عرض یکسانی دارند. این امکان باعث می‌شود تا برای مثال تمام کاراکترهای nام سطرها در طول یکسانی قرار داشته باشند و شکل نهایی مرتب باشد.
:::

![image](/img/proportional_vs_monospaced_font.png)

معمولاً محیط IDEها و کنسول به طور پیش‌فرض فونتی monospaced دارند.

مثالهای مرتبط با رسم اشکال هندسی از حلقه‌های تودرتو استفاده می‌کنند. برای محاسبه‌ی نحوه‌ی نوشتن این حلقه‌ها ابتدا هر سطر را شماره‌گذاری می‌کنیم (مثال بالا):

![image](/img/csharp_star_pattern_num.png)

بعد از آن حلقه‌ی بیرونی را ایجاد می‌کنیم که شمارنده‌ی آن از 1 تا شماره‌ی آخرین سطر را بشمارد. در این مثال تعداد سطرها 5 است:

```clike
for (int i = 1; i <= 5; i++)
{

}
```

دقت شود که برخلاف حلقه‌های استاندارد که شمارنده‌ی آن‌ها از 0 شروع می‌شود، این حلقه باید شمارش را از 1 شروع کند. چرا که در این حلقه تنها تعداد دفعات اجرا شدن دستورات بدنه‌ی حلقه مهم نیست؛ بلکه شمارنده‌ی حلقه‌ی بیرونی (i) به عنوان پارامتری در حلقه‌های درونی هم استفاده می‌شود و در صورتی که این متغیر از 0 شروع شود حلقه‌ی درونی فرضی که به صورت for (int j = 0; j < i; j++) نوشته شده است برای بار اول هرگز چیزی را چاپ نخواهد کرد.

در مرحله‌ی بعد باید یک رابطه‌ی ریاضی بین تعداد کاراکترهای هم‌نوع در یک سطر و شماره‌ی آن سطر پیدا کرد. در این مثال تعداد ستاره‌ها برابر شماره‌ی سطر است. پس در هر سطر باید به تعداد i ستاره چاپ شود. بنابراین به حلقه‌ای درونی احتیاج داریم که i بار تکرار شود:

```clike
for (int i = 1; i <= 5; i++)
{
    for (int j = 0; j < i; j++)
    {

    }
}
```

در نهایت در حلقه‌ی درونی دستور چاپ یک ستاره را نوشته و پس از آکلاد بسته‌ی حلقه‌ی بیرونی دستور چاپ لاین بریک را می‌نویسیم. با این کار پس از هربار اجرای کامل حلقه‌ی درونی چاپ از سطر بعدی ادامه خواهد یافت.

## برنامه‌ی چاپ الگوی مثلثی برعکس با کاراکتر ستاره

این برنامه الگوی زیر را در کنسول چاپ می‌کند:

![image](/img/csharp_star_pattern_reversed.png)

برای حل این مسئله مطابق روش توضیح داده شده سطرها را شماره‌گذاری کرده و رابطه‌ی تعداد کاراکترها با شماره‌ی سطر را به دست می‌آوریم.

![image](/img/csharp_star_pattern_reversed_space_numbers.png)

*برای مشخص کردن کاراکترهای فاصله از مربع استفاده شده است*

در اینجا نیازمند یافتن تابعی (ریاضی) هستیم که با قرار دادن شماره‌ی سطر در درون آن تعداد فاصله به دست بیاید. بدیهی است که این تابع f(i)=5-i می‌باشد.

پس الگوریتم حل این مسئله به صورت زیر است:

* در حلقه‌ی بیرونی از 1 تا 5 بشمار (متغیر i)

    * در هر مرتبه از اجرای حلقه‌ی بیرونی از 1 تا 5-i بشمار و هر بار یک کاراکتر فاصله چاپ کن

    * در هر مرتبه از اجرای حلقه‌ی بیرونی از 1 تا i بشمار و هر بار یک کاراکتر ستاره چاپ کن

* قبل از رفتن به دور بعدی حلقه یک لاین بریک چاپ کن

ممکن است مثل این حالت دو کاراکتر مختلف (فاصله و ستاره) داشته باشیم. در این صورت یک حلقه‌ی بیرونی داریم که سطرها را می‌شمارد و به ازای هر نوع کاراکتر هم یک حلقه در درون حلقه‌ی بیرونی (که وظیفه‌ی چاپ دسته‌ی کاراکتر را بر عهده دارد). حلقه‌های درونی هم‌رده هستند و زیرمجموعه‌ی حلقه‌ی بیرونی می‌باشند.

سعی کنید یک بار خودتان این برنامه را بدون نگاه کردن به کد زیر بنویسید:

```clike
using System;

namespace ConsoleApplication1
{
    internal class Program
    {
        public static void Main(string[] args)
        {
            for (int i = 1; i <= 5; i++)
            {
                for (int j = 0; j < 5-i; j++)
                {
                    Console.Write(" ");
                }
                
                for (int j = 0; j < i; j++)
                {
                    Console.Write("*");
                }
                Console.Write("\n");
            }
        }
    }
}
```