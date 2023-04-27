# خطایابی در شبیه‌سازی دوبعدی

<div id="46640161910"><script type="text/JavaScript" src="https://www.aparat.com/embed/3aNor?data[rnddiv]=46640161910&data[responsive]=yes"></script></div>

> تیم رباتیک دانشگاه خواجه نصیر(KN2C) - خطایابی در شبیه‌سازی دوبعدی فوتبال

dlog یک متغیر global هست که برای دیباگ کردن خیلی به دیباگ کردن کد کمک میکند.

دیلاگ شامل توابع زیادی هست که با صدا کردن آنها هنگام اجرای بازی در صفحه soccerwindow2 با فعال سازی مود دیباگ میتوانیم اشکال کشیده  یا نوشته شده را در هر سایکل جداگانه از هم ببینیم و بررسی کنیم.



یکی از ویژگی‌های دیگر dlog این هست که با بخش بندی دیباگ‌ها مرتب سازی آن‌ها بر اساس رفتار انجام شده کار را برای ما راحت کرده است. مثلا: 

```c
dlog.addText(Logger::BLOCK, "HI BLOCK");
dlog.addText(Logger::INTERCEPT, "HI INTERCEPT");
```

خط اول متن را به قسمت بلاک و خط دوم متن را به قسمت اینترسپت اضافه میکند.



## addText

این تابع ‌string ورودی میگیرد و مانند scanf متغیرهای بعدی را بر اساس فرمت ‌رشته ورودی میگیرد.

```c
dlog.addText(Logger::BLOCK,"int: %d, double: %f test", 10, 2.24);
```

## addLine

این تابع با ورودی گرفتن نقطه‌ی سر و ته یک خط و رنگ آن خطی در صفحه بازی میکشد. این تابع به صورت چند نوع مختلف برای ورودی گرفتن تعریف شده است که یکی از پر استفاده‌ترین انها در زیر امده است.

```c
Vector2D start(0,0);
Vector2D end(10,10);

dlog.addLine(Logger::BLOCK, start, end, 255, 0, 0);
```

سه ورودی اخر آن رنگ خط هست که به صورت rgb تعریف شده اند و دارای مقادیر اولیه نیز هستند(میتوانیم رنگ را ورودی ندهیم.).

## addCircle

این تابع با ورودی گرفتن مرکز دایره و شعاع و رنگ آن و بولینی که مشخص میکند از داخل پر باشد یا نه دایره ای را روی صفحه بازی میکشد.

```c
Vector2D center(2,2);
double r = 4;
dlog.addCircle(Logger::BLOCK, center, r, 255,0,0, false)
```

چهار مقدار اخر یعنی رنگ و از داخل پر یا نه دارای مقادیر اولیه هستند.
