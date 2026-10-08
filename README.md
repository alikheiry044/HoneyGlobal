# HoneyGlobal
# Global [COMMODITY] Production & Trade Dashboard (Power BI)

**Languages:** English · [فارسی](#-فارسی)

> **Before publishing:** replace every `[...]` with real information, then delete this line.
> Do not publish numbers in "Key Findings" until the validation step below is done.

An interactive Power BI report that combines **production data** and **international trade data** for [COMMODITY, e.g. honey] across countries, covering **2018–2024**. It helps answer: *who produces the most, who exports and imports the most, and which trade partners matter?*

## Business Questions

1. Which countries produce the most [COMMODITY], and how did production change from 2018 to 2024?
2. Which countries are the largest exporters and importers?
3. Which countries run a trade surplus or deficit?
4. Which partner countries account for most of a reporter's trade?

## Dataset

| Item | Details |
|---|---|
| Production data | [source name + link, e.g. FAOSTAT] |
| Trade data | [source name + link, e.g. UN Comtrade] |
| Period | 2018–2024 |
| Units | Production in tonnes; trade value in USD [confirm: USD or thousand USD] |
| Size | [number of rows per table] |

## Data Model

Star-schema style model with dimension and fact tables:

- **Dimensions:** `Dim_Country`, `Dim_Year`
- **Facts:** `Fact_Production`, `Fact_Trade_Bilateral`, `Fact_Trade_Comtrade`, `Fact_Trade_Country`, `Fact_Production_Value`, `Fact_Supply_Utilization`

[Add a screenshot of the Model view: `screenshots/data-model.png`]

## DAX Measures

`Total Production`, `Total Export`, `Total Import`, `Total Trade Value`, `Trade Balance`, `Trade Value USD`, `YoY Growth %`, `Production Growth`

```DAX
-- paste your real formulas here, for example:
Trade Balance = [Total Export] - [Total Import]

YoY Growth % =
VAR Current = [Total Production]
VAR Previous = CALCULATE ( [Total Production], DATEADD ( Dim_Year[Date], -1, YEAR ) )
RETURN DIVIDE ( Current - Previous, Previous )
```

## Dashboard Pages

| Page | What it shows |
|---|---|
| Executive Summary | KPI cards (trade value, exports, imports, trade balance, production) and top producing countries |
| Production Analysis | Production by country and by year, average production, growth |
| Trade Map | Geographic view of exports and imports by reporter country |
| Partner Network | Trade value between reporter and partner countries (donut, bar, matrix) |
| Waterfall Analysis | Breakdown of export and import value contributions |

[Add screenshots: `screenshots/executive-summary.png`, `screenshots/production.png`, `screenshots/trade-map.png`, `screenshots/partner-network.png`, `screenshots/waterfall.png`]

## Data Preparation

[Describe what you really did in Power Query / before loading, for example:]
- [Combined files from X and Y]
- [Standardized country names between production and trade sources]
- [Handled missing values / blank countries]
- [Converted data types and units]

## Data Validation

[Write what you checked, for example: compared dashboard totals with the source tables; checked that exports and imports are in the same units.]

## Key Findings

[Fill in only after validation. Each finding must contain a number from the dashboard, for example:]
- [Country X produced Y tonnes in 2024, Z% of the total.]
- [Country A has the largest trade surplus: B USD.]

## Limitations

- [Missing or incomplete data for some countries/years]
- [Trade data is reported by each country, so exports and imports can differ between partners]
- [Anything else you know about]

## How to Open

1. Install [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (Windows).
2. Download `HOUNY.pbix` from this repository.
3. Open it. If the data source path breaks, update it in **Transform data → Data source settings**.

A PDF export of the report is in `dashboard/`.

## Repository Structure

```
├── README.md
├── dashboard/
│   ├── HOUNY.pbix
│   └── HOUNY-Global.pdf
├─            
└── screenshots/
```

## Future Improvements

- [Only list things you genuinely plan to do]

## Author

Ali — [LinkedIn](https://www.linkedin.com/in/ali-kheiry-1b89b0237/) · alikhaire11@gmail.com


---

<a id="-فارسی"></a>

<div dir="rtl" align="right">

# 🇮🇷 فارسی

> **قبل از انتشار:** همه‌ی `[...]` را با اطلاعات واقعی جایگزین کن و این خط را حذف کن.
> تا مرحله‌ی «اعتبارسنجی داده» انجام نشده، عددی در بخش «یافته‌های کلیدی» ننویس.

# داشبورد جهانی تولید و تجارت [نام کالا] (Power BI)

یک گزارش تعاملی Power BI که داده‌های **تولید** و **تجارت بین‌المللی** [نام کالا، مثلاً عسل] را بین کشورها در بازه‌ی **۲۰۱۸ تا ۲۰۲۴** کنار هم قرار می‌دهد. این گزارش به این سؤال‌ها پاسخ می‌دهد: کدام کشورها بیشترین تولید را دارند، چه کشورهایی بیشترین صادرات و واردات را دارند، و شریک‌های تجاری اصلی چه کشورهایی هستند.

## سؤال‌های کسب‌وکاری

1. کدام کشورها بیشترین [نام کالا] را تولید می‌کنند و تولید از ۲۰۱۸ تا ۲۰۲۴ چطور تغییر کرده است؟
2. بزرگ‌ترین صادرکننده‌ها و واردکننده‌ها چه کشورهایی هستند؟
3. کدام کشورها مازاد یا کسری تجاری دارند؟
4. هر کشور گزارش‌دهنده بیشتر با کدام کشورهای شریک تجارت می‌کند؟

## داده‌ها

| مورد | جزئیات |
|---|---|
| داده‌ی تولید | [نام منبع + لینک، مثلاً FAOSTAT] |
| داده‌ی تجارت | [نام منبع + لینک، مثلاً UN Comtrade] |
| بازه‌ی زمانی | ۲۰۱۸ تا ۲۰۲۴ |
| واحدها | تولید بر حسب تن؛ ارزش تجارت بر حسب دلار [تأیید کن: دلار یا هزار دلار] |
| حجم داده | [تعداد ردیف هر جدول] |

## مدل داده

مدل به سبک Star Schema با جدول‌های بُعد و جدول‌های واقعیت:

- **بُعدها:** `Dim_Country` و `Dim_Year`
- **واقعیت‌ها:** `Fact_Production`، `Fact_Trade_Bilateral`، `Fact_Trade_Comtrade`، `Fact_Trade_Country`، `Fact_Production_Value`، `Fact_Supply_Utilization`

[اسکرین‌شات نمای Model را اضافه کن: `screenshots/data-model.png`]

## فرمول‌های DAX

`Total Production`، `Total Export`، `Total Import`، `Total Trade Value`، `Trade Balance`، `Trade Value USD`، `YoY Growth %`، `Production Growth`

فرمول‌های واقعی خودت را اینجا بگذار (مثال در بخش انگلیسی بالا).

## صفحه‌های داشبورد

| صفحه | محتوا |
|---|---|
| Executive Summary | کارت‌های شاخص (ارزش تجارت، صادرات، واردات، تراز تجاری، تولید) و کشورهای برتر تولید |
| Production Analysis | تولید بر اساس کشور و سال، میانگین تولید، رشد |
| Trade Map | نقشه‌ی صادرات و واردات بر اساس کشور گزارش‌دهنده |
| Partner Network | ارزش تجارت بین کشور گزارش‌دهنده و شریک (دونات، میله‌ای، ماتریس) |
| Waterfall Analysis | تفکیک سهم صادرات و واردات در ارزش کل |

[اسکرین‌شات هر صفحه را در پوشه‌ی `screenshots/` بگذار.]

## آماده‌سازی داده

[کارهایی که واقعاً انجام دادی را بنویس، مثلاً:]
- [ترکیب فایل‌های منبع X و Y]
- [یکسان‌سازی نام کشورها بین داده‌ی تولید و تجارت]
- [مدیریت مقدارهای خالی و کشورهای Blank]
- [تبدیل نوع داده و واحدها]

## اعتبارسنجی داده

[بنویس چه چیزهایی را بررسی کردی، مثلاً: مقایسه‌ی جمع‌های داشبورد با جدول منبع، و یکسان بودن واحد صادرات و واردات.]

## یافته‌های کلیدی

[فقط بعد از اعتبارسنجی پر کن. هر یافته باید یک عدد از داشبورد داشته باشد، مثلاً:]
- [کشور X در ۲۰۲۴ مقدار Y تن تولید کرد، یعنی Z درصد کل.]
- [کشور A بیشترین مازاد تجاری را دارد: B دلار.]

## محدودیت‌ها

- [نبود یا ناقص بودن داده برای بعضی کشورها و سال‌ها]
- [داده‌ی تجارت را هر کشور خودش گزارش می‌دهد، پس صادرات و واردات بین دو شریک ممکن است با هم نخواند]
- [هر محدودیت دیگری که می‌دانی]

## نحوه‌ی باز کردن

1. [Power BI Desktop](https://powerbi.microsoft.com/desktop/) را نصب کن (ویندوز).
2. فایل `HOUNY.pbix` را از این ریپو دانلود کن.
3. بازش کن. اگر مسیر منبع داده خطا داد، از **Transform data ← Data source settings** اصلاحش کن.

خروجی PDF گزارش در پوشه‌ی `dashboard/` است.

## ساختار ریپو

```
├── README.md
├── dashboard/
│   ├── HOUNY.pbix
│   └── HOUNY-Global.pdf
  
└── screenshots/
```

## بهبودهای آینده

- [فقط مواردی که واقعاً قصد انجامشان را داری]

## سازنده

Ali — [LinkedIn](https://www.linkedin.com/in/ali-kheiry-1b89b0237/) · alikhaire11@gmail.com

</div>
