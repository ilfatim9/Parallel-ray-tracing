# تشغيل الكود

## تحميل المشروع

1. اضغطي **Code → Download ZIP** وفكّي الضغط.
2. افتحي المجلد الذي يحتوي على `main.cc` في VS Code.
3. اختاري **Terminal → New Terminal**.

## Windows

إذا المترجم غير مثبّت، ثبّتي [MSYS2](https://www.msys2.org/)، ثم افتحي **MSYS2 UCRT64** ونفّذي:

```bash
pacman -S --needed base-devel mingw-w64-ucrt-x86_64-toolchain
```

اضغطي Enter لاختيار جميع الحزم، ثم Y للتثبيت.

في تيرمنال PowerShell داخل VS Code، نفّذي بالترتيب:

```powershell
$env:Path = "C:\msys64\ucrt64\bin;" + $env:Path
```

```powershell
g++ -std=c++17 -O3 main.cc -o raytracer.exe
```

بعد انتهاء التجميع بدون أخطاء، شغّلي:

```powershell
cmd /c ".\raytracer.exe > image.ppm"
```

## Mac

إذا المترجم غير مثبّت، نفّذي وأكملي التثبيت:

```bash
xcode-select --install
```

في تيرمنال VS Code، جمّعي الكود:

```bash
clang++ -std=c++17 -O3 main.cc -o raytracer
```

ثم شغّليه:

```bash
./raytracer > image.ppm
```

## تسجيل الوقت

- انتظري ظهور **Render time** و**Done**.
- سجّلي الوقت بالثواني.
- كرّري أمر التشغيل **5 مرات** وسجّلي كل نتيجة.
- لا تغيّري إعدادات الكود بين التشغيلات.
- وقت حفظ الصورة مستبعد من القياس.
