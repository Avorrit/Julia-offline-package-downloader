# Julia Offline Depot Builder
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

ابزاری برای دانلود پکیج‌های جولیا جهت استفادهٔ آفلاین با کمک گیت‌هاب اکشنز.

## 🚀 شروع سریع

۱. ریپو را **Fork** کنید (ترجیحاً **Private**).
۲. یک شاخه به نام `depot-build` در ریپوی خود بسازید.
۳. از **Settings > Archives and Git LFS**، گزینهٔ **Enable Git LFS** را فعال کنید.
۴. از **Settings > Actions > General**، گزینهٔ **Read and write permissions** را فعال کنید.
۵. از تب **Actions**، ورک‌فلو را اجرا کرده و نام پکیج (مثلاً `Plots`) و نسخهٔ جولیا (مثلاً `1.12.5`) را وارد کنید.
۶. پس از پایان کار، شاخهٔ `depot-build` را روی سیستم خود دریافت کنید:

- **دفعهٔ اول (کلون کامل):**
```bash
git clone -b depot-build https://github.com/USERNAME/REPO.git C:\Users\USER\.julia
cd C:\Users\USER\.julia
git lfs pull
```

- **دفعات بعد (فقط دریافت تغییرات جدید):**
```bash
cd C:\Users\USER\.julia
git pull origin depot-build
```

- **روش جایگزین (دانلود ZIP):**
  به شاخهٔ `depot-build` بروید، روی **Code > Download ZIP** کلیک کنید و محتوای فایل را در مسیر `.julia` جایگزین نمایید.

۷. جولیا را در حالت آفلاین اجرا کنید:

```cmd
set JULIA_PKG_OFFLINE=true
julia
```

## 📦 افزودن پکیج جدید

۱. ورک‌فلو را دوباره با نام پکیج جدید اجرا کنید.

۲. پوشه .julia را به صورت زیر به گیت متصل کنید:
```cmd
cd C:\Users\USER\.julia
git init
git config core.longpaths true
git remote add origin https://github.com/USERNAME/REPO.git
git fetch origin depot-build
git checkout -f -b depot-build origin/depot-build
```

## ⚠️ نکات

- پهنای باند رایگان Git LFS ماهانه ۱ گیگابایت است.
- ورک‌فلو روی ویندوز اجرا می‌شود و فایل‌ها با سیستم‌عامل ویندوز سازگار هستند.

