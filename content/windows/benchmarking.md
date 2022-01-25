- Download [PresentMon](https://github.com/GameTechDev/PresentMon).
- Rename it to ***presentmon.exe***.
- In the same folder, create a ***.bat*** file with the following content:
```
@pushd %~dp0
@presentmon.exe -multi_csv -no_top -track_debug -hotkey f10 -delay 1 -timed 120
```
- Modify the options according to your needs. Here are the most relevant ones:

| Option | Description |
| --- | --- |
| -multi_csv | Create a separate CSV file for each captured process. |
| -no_top | Don't display active swap chains in the console. |
| -hotkey key | Use provided key to start and stop recording, writing to a unique CSV file each time. 'key' is of the form MODIFIER+KEY, e.g., alt+shift+f11. |
| -delay seconds | Wait for provided time before starting to record. If using -hotkey, the delay occurs each time recording is started. |
| -timed seconds | Stop recording after the provided amount of time. |
| -track_debug | Adds additional data to output. |

- Run the ***.bat*** file as Administrator.
- You can use [Frame Time Analysis](https://boringboredom.github.io/Frame-Time-Analysis/) to compare benchmarks.