- Download [PresentMon](https://github.com/GameTechDev/PresentMon).
- Rename it to ***presentmon.exe***.
- In its folder, create a folder called ***captures*** and a ***.bat*** file (not inside ***captures***) with the following content:
```
@pushd %~dp0
@cd captures
@..\presentmon.exe -multi_csv -no_top -track_debug -hotkey "f10" -delay 1 -timed 120
```
- Modify the [options](https://github.com/GameTechDev/PresentMon#command-line-options) according to your needs.
- Run the ***.bat*** file as Administrator.
- You can use [Frame Time Analysis](https://boringboredom.github.io/Frame-Time-Analysis/) to compare benchmarks.