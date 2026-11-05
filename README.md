[README.md](https://github.com/user-attachments/files/34449298/README.md)[Uploa# F.A.T. — Vocal Channel Strip

**Tagline:** Find. Add. Transform.

This package contains the F.A.T. JUCE starter source, a resizable rotary-control UI, foundational DSP, 30 JSON reference presets, product icons, a PDF manual, an Inno Setup installer script, and a GitHub Actions Windows build workflow.

## Build a Windows installer

The actual `.exe` must be compiled on Windows. This package includes `.github/workflows/build-windows.yml` to automate that build using a Windows 2022 runner.

1. Create a GitHub repository and upload this project (the contents of this folder) to its `main` branch.
2. In GitHub, open **Actions** and select **Build F.A.T. for Windows**.
3. Choose **Run workflow**.
4. When the workflow completes, open its run and download the `F.A.T.-Windows-x64` artifact.
5. The artifact contains `FAT-Windows-Setup-x64.exe`, the VST3 bundle and standalone application.

The workflow fetches JUCE from its official GitHub repository at build time. Review JUCE's current licensing terms and choose the appropriate open-source or commercial JUCE license for your distribution plans.

## Local Windows build requirements

- Windows 10/11 64-bit
- Visual Studio 2022 with Desktop development with C++
- CMake 3.22+
- Inno Setup 6
- JUCE source checked out into `./JUCE`

Run:
```powershell
git clone --depth 1 https://github.com/juce-framework/JUCE.git JUCE
cmake -S . -B build -A x64
cmake --build build --config Release --parallel
```
Then compile `Installer/F.A.T.-Setup.iss` in Inno Setup 6.

## What is implemented

- Resizable JUCE editor with rotary controls
- Input trim, high-pass filter, compressor, saturation, wet/dry blend, reverb and output trim
- Host parameter automation and session state recall
- VST3 and standalone build targets
- Installer script with VST3 installation, standalone application, desktop shortcut, Start Menu shortcuts and uninstaller

## Known unfinished work

This is an early engineering starter, not a finished commercial product. Dedicated gate, full parametric EQ, de-esser, delay, exciter, limiter, meters, in-plugin preset browser/import, A/B compare, undo/redo, accessibility review, performance profiling and DAW compatibility testing remain to be implemented. The 30 JSON presets are reference settings and are not yet selectable in a built-in preset browser.

Physical vibration requires compatible haptic hardware; most desktop PCs do not expose a haptic output device. Visual feedback can be used universally.

## Product identity

F.A.T. is a proposed name. Check trademarks, company names, domains and plugin-store availability before commercial release. The design is independent and does not reproduce Universal Audio artwork, branding or proprietary code.
ding README.md…]()
