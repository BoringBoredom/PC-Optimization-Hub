# Polling rate

The computer's USB controller asks the mouse for new data at a <ins>**static**</ins> rate. This happens regardless of mouse motion. The lowest possible interval is 0.125 ms (USB 2 & 3 in High speed mode).

# Motion data report rate

This is the rate at which the mouse transmits motion data to the USB controller. Modern mice usually keep the polling rate at the maximum to reduce click latency while buffering motion data if you select lower report rates.

E.g.: report rate settings in Synapse

- 8000 Hz - motion data is transmitted every interval
- 4000 Hz - motion data is transmitted every 2nd interval
- 2000 Hz - motion data is transmitted every 4th interval
- 1000 Hz - motion data is transmitted every 8th interval

# MouseTester

Whenever MouseTester receives a raw input message, it gets [timestamped](https://github.com/amitxv/MouseTester/blob/904db7bcaca57a9bef578d04c41d2d32abad9dc4/MouseTester/MouseTester/Form1.cs#L80) and [collected](https://github.com/amitxv/MouseTester/blob/904db7bcaca57a9bef578d04c41d2d32abad9dc4/MouseTester/MouseTester/Form1.cs#L90) if it is a mouse event. You are not actually measuring the polling rate, but the rate at which MouseTester receives mouse events. This means that system load, lack of motion etc. will have an impact on the results.

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

### TLDR: don't use `Frequency vs. Time`, use `Interval vs. Time` instead
