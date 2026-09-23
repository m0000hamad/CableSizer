# Changelog / تاریخچه نسخه‌ها

All notable changes to CableSizer are documented in this file.
<br>
تمام تغییرات قابل توجه در CableSizer در این فایل ثبت می‌شود.

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

[1.2.0]: https://github.com/m0000hamad/CableSizer/compare/v1.1.0...v1.2.0
[1.1.0]: https://github.com/m0000hamad/CableSizer/compare/v1.0.0...v1.1.0
[1.0.0]: https://github.com/m0000hamad/CableSizer/releases/tag/v1.0.0
