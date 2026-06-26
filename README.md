# Hippo — Installer

Distribution package for **Hippo**, a Windows desktop **Point-of-Sale (POS)** system
for restaurants. The interface is primarily **Arabic (RTL)** with optional English.

This repository hosts the ready-to-run installer and its prerequisites. Each
release contains the latest build of the application.

---

## 📦 Contents

| File / Folder | Purpose |
| --- | --- |
| `setup.exe` | Bootstrapper — installs Hippo and any missing prerequisites |
| `Hippo installer.msi` | The Hippo application installer (launched by `setup.exe`) |
| `SystemConfigurations.cmd` | Starts the SQL Server LocalDB instance Hippo uses |
| `DotNetFX451/` | .NET Framework 4.5.1 prerequisite (installed if missing) |
| `SqlLocalDB2014/` | SQL Server 2014 Express LocalDB prerequisite (installed if missing) |
| `How to install.txt` / `دليل تثبيت البرنامج.txt` | Short install guides (EN / AR) |

## ✅ Requirements

- Windows 10 / 11 (or Windows Server)
- Administrator rights (setup registers prerequisites and writes to *Program Files*)

The required runtimes — **.NET Framework 4.5.1** and **SQL Server 2014 Express
LocalDB** — are bundled here and installed automatically by `setup.exe` when they
are not already present.

## 🚀 Installation

1. Download the latest [release](https://github.com/mahmoudelwekel/Hippo-Installer/releases) (or clone this repository).
2. Run **`setup.exe`** and follow the prompts. It installs the prerequisites (if needed) and the Hippo application.
3. Run **`SystemConfigurations.cmd`** once to start the database engine
   (`SQLLocalDB start MSSQLLocalDB`).
4. Launch **Hippo** from the desktop shortcut.

### First login

```
Username: admin
Password: admin
```

> ⚠️ Change the default password after the first login.

## 🔄 Updating

Hippo is a standard MSI with in-place upgrade enabled. To update, download the
newer release and run its `setup.exe` / `Hippo installer.msi`.

- The new version **replaces** the previous one automatically.
- Your data is **preserved** — the database lives under `%APPDATA%` and is not
  touched during an upgrade.
- Installing an **older** build over a newer one is blocked (downgrade protection).

## 🏷️ Releases & versioning

Releases are published automatically by the CI pipeline in the
[Hippo source repository](https://github.com/mahmoudelwekel/Hippo). Versions use a
date-based `yy.mm.dd` scheme (e.g. `v26.06.27`), so a newer release always has a
higher version than an older one.

---

## 🇪🇬 دليل التثبيت (بالعربية)

برنامج **Hippo** هو نظام نقاط بيع (POS) للمطاعم يعمل على نظام Windows، وواجهته
بالعربية مع دعم اختياري للإنجليزية.

### المتطلبات
- نظام Windows 10 / 11
- صلاحيات المسؤول (Administrator)

تُثبَّت المتطلبات (.NET Framework 4.5.1 و SQL Server 2014 LocalDB) تلقائيًا
بواسطة `setup.exe` إذا لم تكن موجودة.

### خطوات التثبيت
1. شغّل الملف **`setup.exe`** واتبع التعليمات لتثبيت البرنامج والمتطلبات.
2. شغّل الملف **`SystemConfigurations.cmd`** مرة واحدة لتشغيل قاعدة البيانات.
3. افتح برنامج **Hippo** من اختصار سطح المكتب.

### تسجيل الدخول لأول مرة
- اسم المستخدم: `admin`
- كلمة المرور: `admin`

> ⚠️ يُنصح بتغيير كلمة المرور الافتراضية بعد أول تسجيل دخول.

### التحديث
لتحديث البرنامج، نزّل أحدث إصدار وشغّل `setup.exe`. سيحل الإصدار الجديد محل
الإصدار السابق تلقائيًا مع الحفاظ على بياناتك (قاعدة البيانات محفوظة في `%APPDATA%`).
