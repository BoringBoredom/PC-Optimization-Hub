-  Download [PresentMon](https://github.com/GameTechDev/PresentMon).
-  Rename it to **_presentmon.exe_**.
-  In its folder, create a folder called **_captures_** and a **_.bat_** file (not inside **_captures_**) with the following content:

```
@pushd %~dp0
@cd captures
@..\presentmon.exe -multi_csv -no_top -track_debug -hotkey "f9" -delay 1 -timed 120
```

-  Modify the [options](https://github.com/GameTechDev/PresentMon#command-line-options) according to your needs.
-  Run the **_.bat_** file as Administrator.
-  You can use [Frame Time Analysis](https://boringboredom.github.io/Frame-Time-Analysis/) to compare benchmarks.
