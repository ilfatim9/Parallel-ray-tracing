# How to Run the Code

## 1. Download the Project

1. Click **Code → Download ZIP**.
2. Extract the ZIP file.
3. In VS Code, select **File → Open Folder**.
4. Open the folder containing `main.cc`.

## 2. Check for a Compiler

In VS Code, click **Terminal → New Terminal** from the top menu.

A terminal will open at the bottom of the window. Copy the command for your system below, paste it into the terminal, and press **Enter**.

### Windows

```powershell
g++ --version
```

### Mac

```bash
clang++ --version
```

If a version number appears, go to **Step 4**.

If the command is not found, the compiler may be missing or its path may not be set.

### Windows: If MSYS2 Is Already Installed

In the same VS Code terminal, try:

```powershell
& "C:\msys64\ucrt64\bin\g++.exe" --version
```

If a version number appears, run:

```powershell
$env:Path = "C:\msys64\ucrt64\bin;" + $env:Path
```

Then go to **Step 4**. Run this path command again whenever you open a new terminal.

## 3. Install a Compiler

### Windows — Intel or AMD

1. Download the **x86_64 installer** from [MSYS2](https://www.msys2.org/).
2. Install it in `C:\msys64`.
3. Open **MSYS2 UCRT64** from the Windows Start menu.
4. Paste this command into the **MSYS2 window**, then press Enter:

```bash
pacman -S --needed base-devel mingw-w64-ucrt-x86_64-toolchain
```

5. Press **Enter** to select all packages, then **Y** to install.
6. After installation, return to the **PowerShell terminal in VS Code** and run:

```powershell
$env:Path = "C:\msys64\ucrt64\bin;" + $env:Path
```

Check the compiler:

```powershell
g++ --version
```

Run the path command again whenever you open a new terminal.

### Mac

In the **VS Code terminal**, run:

```bash
xcode-select --install
```

Follow the installation window. After installation, check:

```bash
clang++ --version
```

## 4. Compile and Run

Use the **terminal at the bottom of VS Code**.

Make sure the terminal is in the folder containing `main.cc`. If needed, type `cd `, followed by your project folder path in quotation marks, and press Enter.

Run each command separately and press **Enter** after it.

### Windows

Compile:

```powershell
g++ -std=c++17 -O3 main.cc -o raytracer.exe
```

Wait for compilation to finish without errors. Then run:

```powershell
cmd /c ".\raytracer.exe > image.ppm"
```

### Mac

Compile:

```bash
clang++ -std=c++17 -O3 main.cc -o raytracer
```

Wait for compilation to finish without errors. Then run:

```bash
./raytracer > image.ppm
```

## 5. Record the Time

- Wait for **Render time** and **Done** in the terminal.
- Record the time in seconds.
- Run the program **5 times in total**, one run at a time.
- Keep the code settings the same.
- Keep your laptop plugged in and close heavy applications.

The measured time includes calculating pixel colors and storing them in RAM. It does **not** include saving the image file.

The output image is saved as `image.ppm` in the same folder.

| Run 1 (s) | Run 2 (s) | Run 3 (s) | Run 4 (s) | Run 5 (s) | Average (s) |
|---|---|---|---|---|---|
| | | | | | |

Average = sum of the five times ÷ 5.

**After changing the code, save it and compile again. If the code has not changed, only repeat the run command.**
