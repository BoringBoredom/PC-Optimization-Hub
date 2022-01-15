- Download [PresentMon](https://github.com/GameTechDev/PresentMon)
- Rename it to ***presentmon.exe***
- Create a ***.bat*** file with the following content:
```
@pushd %~dp0
@echo Press F10 to start/stop recording.
@presentmon.exe -multi_csv -no_top -track_debug -hotkey f10
```
- Optionally, exclude processes with ***-exclude***
- Run the ***.bat*** file as Administrator