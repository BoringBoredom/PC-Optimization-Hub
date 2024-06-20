# Polling rate

The computer's USB controller asks the mouse for new data at a <ins>**static**</ins> rate. This happens regardless of mouse motion. The lowest possible interval is 0.125 ms (USB 2 & 3 in High speed mode).

# Motion data report rate

This is the rate at which the mouse transmits motion data to the USB controller. Modern mice usually keep the polling rate at the maximum to reduce click latency while buffering motion data if you select lower report rates.

E.g.: report rate settings in Synapse

- 8000 Hz - motion data is transmitted every interval
- 4000 Hz - motion data is transmitted every 2nd interval
- 2000 Hz - motion data is transmitted every 4th interval
- 1000 Hz - motion data is transmitted every 8th interval

# [MouseTester](https://github.com/valleyofdoom/MouseTester)

Whenever MouseTester receives a raw input message, it gets timestamped and collected if it is a mouse event. You are not actually measuring the polling rate, but the rate at which MouseTester receives mouse events. This means that system load, lack of motion etc. will have an impact on the results.

### Usage tips

- Use 15k+ DPI for testing to ensure lack of sensor data doesn't skew the results.
- Exit all running applications.
- Right-click your Desktop, hover over `View` and uncheck `Show desktop icons`.
- Keep the MouseTester window focussed to avoid [this issue](#why-is-mousetester-stuck-at-8-ms--125-hz).
- Start quickly moving the mouse in circles before you start recording and don't stop until after you stop recording.
- Make sure to keep the cursor on the desktop and avoid hitting the taskbar or MouseTester window.

### Why does the `Frequency vs. Time` graph show very high peaks, way above the actual report rate?

Each data point represents the delta between the current and previous event timestamp. The `Frequency vs. Time` graph converts the values from interval (ms) to frequency (Hz = 1000 / ms).

Let's assume the polling and report rate are both 1000 Hz. An ideal data point array would look like this:

```
1         1         1         1         1         1     (ms)
1000      1000      1000      1000      1000      1000  (Hz)
```

What happens if an event gets delayed due to, for example, system load?

```
1         1               1.6 0.4       1         1     (ms)
1000      1000            625 2500      1000      1000  (Hz)
```

The 3rd event was delayed by 0.6 ms, so the next delta is 0.4 ms, since the message arrived on time.

If we were to instead display the difference between timestamp and expected ideal timestamp, it would look like this:

```
0         0               0.6 0         0         0     (ms)
```

#### TLDR: don't use `Frequency vs. Time`, use `Interval vs. Time` instead

### Why is MouseTester stuck at 8 ms / 125 Hz?

Windows 11 [updated](https://reddit.com/r/Windows11/comments/109ca82/call_to_action_can_you_see_if_fps_drops_in_games/) the raw input API:

> We capped the rate at which background recipients of raw mouse input could receive messages, so e.g. instead of seeing 1000 messages per second for a 1000Hz mouse, it may only see 125 (but each containing the combined payload of the coalesced messages).

To circumvent this issue, keep the MouseTester window focussed.
