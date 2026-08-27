<div align="center">

# CableSizer

**Cable cross-section calculator for low-voltage installations**
<br>
**محاسبه‌گر سطح مقطع کابل برای تأسیسات فشار ضعیف**

[**▶ Launch the app / اجرای برنامه**](https://m0000hamad.github.io/CableSizer/)

[![Latest version](https://img.shields.io/github/v/tag/m0000hamad/CableSizer?label=version&sort=semver)](https://github.com/m0000hamad/CableSizer/blob/main/CHANGELOG.md)
[![License: MIT](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)

</div>

---

## English

CableSizer selects the smallest standard cable cross-section that satisfies **both** governing
requirements of a low-voltage circuit: current-carrying capacity and voltage drop. It runs entirely
in the browser — no installation, no server, no data leaves the page.

### Features

- **Dual sizing criteria** — checks ampacity and voltage drop, and reports which one governed the result.
- **Ambient temperature** applied along both of its physical paths: derating of the cable's
  current-carrying capacity, and the increase in conductor resistance that raises voltage drop.
- **Installation method** — six IEC reference methods (A1, A2, B1, B2, C, E/F).
- **Grouping factor** for circuits bunched together in a common route.
- **Copper and aluminium** conductors, **PVC (70 °C)** and **XLPE/EPR (90 °C)** insulation.
- Load defined by either **power (kW)** with power factor, or directly by **design current (A)**.
- Voltage drop computed from both **resistance and reactance**.
- **Bilingual interface** (Persian / English) with automatic RTL–LTR switching, plus light and dark themes.
- Fully **responsive** and printable.

### Method

| Step | Basis |
|---|---|
| Design current | `Ib = P / (V · cosφ)` single phase · `Ib = P / (√3 · V · cosφ)` three phase |
| Derated capacity | `Iz = I_table × k_temp × k_group` — must satisfy `Iz ≥ Ib` |
| Conductor temperature | `θ_op = θ_amb + (θ_max − θ_amb) · (Ib / Iz)²` |
| Resistivity | `ρ(θ) = ρ₂₀ · [1 + α · (θ − 20)]` |
| Voltage drop | `ΔV = m · L · Ib · (R'·cosφ + X'·sinφ)`, with `m = 2` (1-ph) or `√3` (3-ph) |

Base current-carrying capacities and correction factors follow **IEC 60364-5-52**
(Tables B.52.4, B.52.5, B.52.14 and B.52.17). Values between tabulated ambient
temperatures are linearly interpolated. Standard cross-sections range from 1.5 mm² to 300 mm².

### Assumptions and limitations

- Base capacities are tabulated for copper; aluminium uses an approximate 0.78 factor.
- Reactance is taken as a typical 0.08 Ω/km for LV multicore cables.
- Harmonic loading, motor starting current, and cables buried directly in soil are not modelled.
- Coordination with the protective device (`Ib ≤ In ≤ Iz`) and short-circuit withstand must be
  verified separately.

> This tool is intended for engineering estimation and preliminary studies. Its results do not
> replace detailed design calculations, national wiring regulations, or sign-off by a qualified
> electrical engineer.

### Running locally

The app is a single self-contained HTML file with no build step and no dependencies:

```bash
git clone https://github.com/m0000hamad/CableSizer.git
cd CableSizer
# open index.html in any modern browser
```

---

<div dir="rtl">

## فارسی

**CableSizer** کوچک‌ترین سطح مقطع استاندارد کابل را انتخاب می‌کند که **هر دو** شرط اصلی یک مدار فشار ضعیف
را همزمان برآورده کند: ظرفیت جریان‌دهی و افت ولتاژ. تمام محاسبات درون مرورگر انجام می‌شود — بدون نصب،
بدون سرور، و بدون ارسال هیچ داده‌ای به بیرون.

### قابلیت‌ها

- **دو معیار همزمان** — بررسی ظرفیت جریان‌دهی و افت ولتاژ، همراه با اعلام اینکه کدام معیار تعیین‌کننده بوده است.
- **دمای محیط** از هر دو مسیر فیزیکی آن اعمال می‌شود: کاهش ظرفیت جریان‌دهی کابل، و افزایش مقاومت
  هادی که افت ولتاژ را بالا می‌برد.
- **روش نصب** — شش روش مرجع استاندارد (A1، A2، B1، B2، C، E/F).
- **ضریب تجمع** برای کابل‌های کنار هم در یک مسیر مشترک.
- هادی **مس و آلومینیوم**، عایق **PVC (۷۰ درجه)** و **XLPE/EPR (۹۰ درجه)**.
- تعریف بار بر اساس **توان (کیلووات)** با ضریب توان، یا مستقیماً بر اساس **جریان طراحی (آمپر)**.
- محاسبه افت ولتاژ با در نظر گرفتن **مقاومت و راکتانس**.
- **رابط دوزبانه** (فارسی / انگلیسی) با تغییر خودکار جهت صفحه، به همراه تم روشن و تاریک.
- کاملاً **واکنش‌گرا** و قابل چاپ.

### روش محاسبه

| مرحله | رابطه |
|---|---|
| جریان طراحی | `Ib = P / (V · cosφ)` تک‌فاز · `Ib = P / (√3 · V · cosφ)` سه‌فاز |
| ظرفیت تصحیح‌شده | `Iz = I_table × k_temp × k_group` — باید `Iz ≥ Ib` برقرار باشد |
| دمای کار هادی | `θ_op = θ_amb + (θ_max − θ_amb) · (Ib / Iz)²` |
| مقاومت ویژه | `ρ(θ) = ρ₂₀ · [1 + α · (θ − 20)]` |
| افت ولتاژ | `ΔV = m · L · Ib · (R'·cosφ + X'·sinφ)` که `m = 2` تک‌فاز و `√3` سه‌فاز است |

ظرفیت‌های پایه و ضرایب تصحیح بر اساس استاندارد **IEC 60364-5-52** (جداول B.52.4، B.52.5، B.52.14
و B.52.17) است. مقادیر بین دماهای جدول به صورت خطی درون‌یابی می‌شوند. بازه مقاطع استاندارد از
۱٫۵ تا ۳۰۰ میلی‌متر مربع است.

### فرض‌ها و محدودیت‌ها

- ظرفیت‌های مبنا برای هادی مسی جدول‌بندی شده‌اند؛ برای آلومینیوم ضریب تقریبی ۰٫۷۸ اعمال می‌شود.
- راکتانس برابر مقدار نوعی ۰٫۰۸ اهم بر کیلومتر برای کابل‌های چندرشته‌ای فشار ضعیف در نظر گرفته شده است.
- اثر هارمونیک‌ها، جریان راه‌اندازی موتور و کابل‌های دفنی در خاک مدل نشده است.
- هماهنگی با وسیله حفاظتی (`Ib ≤ In ≤ Iz`) و بررسی تحمل اتصال کوتاه باید جداگانه انجام شود.

> این ابزار برای برآورد مهندسی و مطالعات اولیه تهیه شده است. نتایج آن جایگزین محاسبات تفصیلی،
> مقررات ملی ساختمان و تأیید مهندس ناظر برق نیست.

### اجرای محلی

برنامه یک فایل HTML مستقل و بدون وابستگی است:

```bash
git clone https://github.com/m0000hamad/CableSizer.git
cd CableSizer
# فایل index.html را در هر مرورگر مدرنی باز کنید
```

</div>

---

## Version history / تاریخچه نسخه‌ها

The live app always reflects the latest release. Every previous version stays documented and
reachable — see the full **[CHANGELOG](CHANGELOG.md)** and the [tagged releases](https://github.com/m0000hamad/CableSizer/tags).
<br>
اپلیکیشن همیشه آخرین نسخه منتشرشده را نمایش می‌دهد. تمام نسخه‌های قبلی مستند و در دسترس باقی می‌مانند —
به **[CHANGELOG](CHANGELOG.md)** کامل و [نسخه‌های تگ‌شده](https://github.com/m0000hamad/CableSizer/tags) مراجعه کنید.

| Version | Date | Summary |
|---|---|---|
| [1.1.0](CHANGELOG.md#110--2026-08-27) | 2026-08-27 | IEC 60364-5-52 sizing (ampacity + voltage drop), ambient temperature, bilingual UI |
| [1.0.0](CHANGELOG.md#100--2025) | 2025 | Initial single-page voltage-drop calculator |

---

## License

Released under the MIT License — see [LICENSE](LICENSE).

## Author

**m0000hamad** — محمد نریموسایی
