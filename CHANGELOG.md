# Changelog / تاریخچه نسخه‌ها

All notable changes to CableSizer are documented in this file.
<br>
تمام تغییرات قابل توجه در CableSizer در این فایل ثبت می‌شود.

---

## [1.3.0] — 2026-09-23

**Buried cables (D1/D2) arrive, and the remaining vague inputs — ground surface, water crossings and adjacent circuits — are now explained.**
<br>
**کابل‌های دفنی (D1/D2) اضافه شد و سه نقطه گنگ باقی‌مانده — کابل روی سطح خاک، عبور از آب و مدارهای همراه — شفاف شد.**

### Added / افزوده شد
- Installation methods **D1** (cable in a buried duct) and **D2** (cable buried direct) with their own
  IEC 60364-5-52 ampacity tables (B.52.2–B.52.5, ground 20 °C, soil 2.5 K·m/W, 0.7 m depth).
  <br>روش‌های نصب **D1** (کابل در لوله/داکت دفنی) و **D2** (کابل مستقیم در خاک) با جداول ظرفیت مخصوص
  استاندارد (B.52.5–B.52.2، خاک ۲۰°C، مقاومت حرارتی ۲٫۵ K·m/W، عمق ۰٫۷ متر).
- The ambient field automatically becomes **ground temperature** (reference 20 °C) when a buried
  method is chosen, using Table B.52.15 correction factors, and buried grouping factors from the
  touching column of Tables B.52.18/19.
  <br>با انتخاب روش دفنی، فیلد دما خودکار به **دمای خاک** (مرجع ۲۰°C) تبدیل می‌شود و از ضرایب جدول
  B.52.15 برای دما و ستون کابل‌های چسبیده جداول B.52.18/19 برای تجمع استفاده می‌شود.
- Guide answers for the two frequently missed cases: cable lying on open ground (evaluate as C;
  if covered by soil use D2) and crossing water (no dedicated IEC method — D1 is a safe conservative
  proxy; the cable itself must be immersion-rated).
  <br>پاسخ راهنما برای دو مورد پرتکرارِ گم‌شده: کابل روی سطح خاک (با روش C حساب می‌شود؛ اگر خاک‌پوش شود D2)
  و عبور از آب (روش مرجع مستقلی در استاندارد نیست — D1 برآوردی امن است و خود کابل باید ضدآب باشد).
- Plain explanation of the grouping input: what counts as one circuit, that your own circuit is part
  of the count, and that neutral, earth, standby and spare lines are not counted — with examples.
  <br>توضیح روان ورودی تجمع: «مدار» چیست، خود مدار شما هم در شمارش است، و نول/ارت/مدار رزرو شمرده
  نمی‌شوند — همراه با مثال.

### Changed / تغییر یافت
- The adjacent-circuits field is now labelled «circuits sharing one route» with a counting hint.
  <br>فیلد «تعداد مدارهای مجاور» اکنون «تعداد مدارهای همراه در یک مسیر» نام دارد و راهنمای شمارش دارد.

---

## [1.2.0] — 2026-09-23

**Contextual help for the two vaguest choices: insulation type and installation method.**
<br>
**راهنمای محیطی برای دو انتخاب گنگ: نوع عایق و روش نصب.**

### Added / افزوده شد
- In-form guide inside the cable section: how to tell PVC from XLPE by the sheath marking
  (NYY, NYM, H07V-U building wire vs. N2XY or aerial bundled cable), and a plain-language table
  that maps each IEC reference method (A1…E/F) to everyday installation examples.
  <br>راهنمای درون‌فرمی در بخش کابل: تشخیص PVC از XLPE بر اساس چاپ روکش
  (کابل NYY و NYM و افشان ساختمانی در برابر N2XY و کابل هوایی خودنگهدار) و جدول روان که
  هر کد روش نصب (A1…E/F) را به یک مثال نصبِ روزمره پیوند می‌زند.
- Short hints under the insulation and installation-method fields pointing to that guide.
  <br>توضیح کوتاه زیر فیلدهای نوع عایق و روش نصب با ارجاع به همان راهنما.

### Changed / تغییر یافت
- Installation-method option labels now spell out the single-wire vs. multicore difference,
  so A1/A2 and B1/B2 are no longer lookalikes.
  <br>برچسب گزینه‌های روش نصب اکنون تفاوت سیم تکی و کابل چندرشته را صریح می‌گوید تا
  A1/A2 و B1/B2 دیگر شبیه هم دیده نشوند.

---

## [1.1.0] — 2026-08-27

**Complete rebuild as a standards-based, bilingual sizing tool.**
<br>
**بازسازی کامل به‌عنوان یک ابزار محاسبه استاندارد و دوزبانه.**

### Added / افزوده شد
- Sizing now checks **both** current-carrying capacity and voltage drop, and reports which one governed the result.
  <br>محاسبه اکنون **هم** ظرفیت جریان‌دهی و **هم** افت ولتاژ را بررسی می‌کند و اعلام می‌کند کدام‌یک تعیین‌کننده بوده است.
- **Ambient temperature** is applied along both of its physical paths: derating of the tabulated
  current-carrying capacity (IEC 60364-5-52, Table B.52.14), and the rise in conductor resistance
  that increases voltage drop, evaluated at the conductor's actual operating temperature.
  <br>**دمای محیط** از هر دو مسیر فیزیکی آن اعمال می‌شود: کاهش ظرفیت جریان‌دهی جدولی (جدول B.52.14 استاندارد
  IEC 60364-5-52) و افزایش مقاومت هادی در دمای کار واقعی که افت ولتاژ را بالا می‌برد.
- Installation method (A1, A2, B1, B2, C, E/F) and grouping factor for bunched circuits (Table B.52.17).
  <br>روش نصب (A1، A2، B1، B2، C، E/F) و ضریب تجمع برای کابل‌های مجاور (جدول B.52.17).
- PVC (70 °C) and XLPE/EPR (90 °C) insulation limits, each with its own temperature correction table.
  <br>محدودیت دمایی عایق PVC (۷۰°C) و XLPE/EPR (۹۰°C)، هرکدام با جدول تصحیح دمایی مخصوص خود.
- Reactance included in the voltage-drop calculation, alongside resistance.
  <br>راکتانس در کنار مقاومت در محاسبه افت ولتاژ لحاظ شد.
- Result is selected from the standard 1.5–300 mm² cross-section series, not a raw computed area.
  <br>خروجی از سری استاندارد مقاطع ۱٫۵ تا ۳۰۰ میلی‌متر مربع انتخاب می‌شود، نه یک عدد خام محاسبه‌شده.
- Load can be defined either by power and power factor, or directly by design current.
  <br>بار قابل تعریف با توان و ضریب توان، یا مستقیماً با جریان طراحی.
- Bilingual interface (Persian/English) with automatic RTL/LTR switching, plus light and dark themes.
  <br>رابط دوزبانه (فارسی/انگلیسی) با تغییر خودکار جهت صفحه، همراه با تم روشن و تاریک.
- In-page documentation of every formula, standard reference, and assumption used.
  <br>مستندسازی درون‌صفحه‌ای تمام روابط، مراجع استاندارد و فرض‌های به‌کاررفته.
- Strict input validation, accepting Persian and Arabic-Indic numerals.
  <br>اعتبارسنجی دقیق ورودی، با پذیرش اعداد فارسی و عربی.

### Changed / تغییر یافت
- Replaced the fixed 20 °C resistivity assumption with temperature-dependent resistivity.
  <br>جایگزینی فرض مقاومت ثابت در ۲۰°C با مقاومت وابسته به دما.

---

## [1.0.0] — 2025

**Initial release.**
<br>**نسخه اولیه.**

- Single-page calculator sizing a conductor from voltage drop alone.
  <br>محاسبه‌گر تک‌صفحه‌ای که سطح مقطع هادی را فقط بر اساس افت ولتاژ تعیین می‌کرد.
- Single/three-phase, copper/aluminum, fixed 5% voltage-drop limit.
  <br>تک‌فاز/سه‌فاز، مس/آلومینیوم، با حد افت ولتاژ ثابت ۵٪.
- No ambient temperature, installation method, or current-carrying capacity check.
  <br>بدون دمای محیط، روش نصب، یا بررسی ظرفیت جریان‌دهی.

[1.3.0]: https://github.com/m0000hamad/CableSizer/compare/v1.2.0...v1.3.0
[1.2.0]: https://github.com/m0000hamad/CableSizer/compare/v1.1.0...v1.2.0
[1.1.0]: https://github.com/m0000hamad/CableSizer/compare/v1.0.0...v1.1.0
[1.0.0]: https://github.com/m0000hamad/CableSizer/releases/tag/v1.0.0
