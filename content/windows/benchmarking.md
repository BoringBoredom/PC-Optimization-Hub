- Download [PresentMon](https://github.com/GameTechDev/PresentMon).
- Rename it to ***presentmon.exe***.
- In its folder, create a folder called ***captures*** and a ***.bat*** file (not inside ***captures***) with the following content:
```
@pushd %~dp0
@cd captures
@..\presentmon.exe -multi_csv -no_top -track_debug -hotkey f10 -delay 1 -timed 120
```
- Modify the options according to your needs.
- Run the ***.bat*** file as Administrator.
- You can use [Frame Time Analysis](https://boringboredom.github.io/Frame-Time-Analysis/) to compare benchmarks.

| Option | Description |
| --- | --- |
| -captureall | Record all processes (default). |
| -process_name name | Record only processes with the provided exe name. This argument can be repeated to capture multiple processes. |
| -exclude name | Don't record processes with the provided exe name. This argument can be repeated to exclude multiple processes. |
| -process_id id | Record only the process specified by ID. |
| -etl_file path | Consume events from an ETW log file instead of running processes. |
| -output_file path | Write CSV output to the provided path. |
| -output_stdout | Write CSV output to STDOUT. |
| -multi_csv | Create a separate CSV file for each captured process. |
| -no_csv | Do not create any output file. |
| -no_top | Don't display active swap chains in the console. |
| -qpc_time | Output present time as a performance counter value. |
| -qpc_time_s | Output present time as a performance counter value converted to seconds. |
| -hotkey key | Use provided key to start and stop recording, writing to a unique CSV file each time. 'key' is of the form MODIFIER+KEY, e.g., alt+shift+f11. |
| -delay seconds | Wait for provided time before starting to record. If using -hotkey, the delay occurs each time recording is started. |
| -timed seconds | Stop recording after the provided amount of time. |
| -exclude_dropped | Exclude dropped presents from the csv output. |
| -scroll_indicator | Enable scroll lock while recording. |
| -no_track_display | Disable tracking through GPU and display. |
| -track_debug | Adds additional data to output not relevant to normal usage. |
| -session_name name | Use the provided name to start a new realtime ETW session, instead of the default "PresentMon". This can be used to start multiple realtime captures at the same time (using distinct, case-insensitive names). A realtime PresentMon capture cannot start if there are any existing sessions with the same name. |
| -stop_existing_session | If a trace session with the same name is already running, stop the existing session (to allow this one to proceed). |
| -terminate_existing | Terminate any existing PresentMon realtime trace sessions, then exit. Use with -session_name to target particular sessions. |
| -restart_as_admin | If not running with elevated privilege, restart and request to be run as administrator. (See discussion above). |
| -terminate_on_proc_exit | Terminate PresentMon when all the target processes have exited. |
| -terminate_after_timed | When using -timed, terminate PresentMon after the timed capture completes. |