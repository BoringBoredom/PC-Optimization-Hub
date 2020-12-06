# CPU Clocking
  - Download the bootable version of [Linpack Xtreme](https://www.techpowerup.com/download/linpack-xtreme/) and mount it to a USB stick.
  - Set your VCORE, VCCIO and VCCSA to what you consider safe 24/7 voltages for your hardware and set your LLC to flat.
  - Set your All Core and Uncore (Cache) frequency to the *Processor Base Frequency* value displayed in the [Intel product database](https://ark.intel.com/content/www/us/en/ark.html). The reason for this is preventing your CPU from overheating by testing the waters first.
  - Boot into Linpack and stress test for a few minutes with a low problem size (high problem size involves more RAM).
  - Monitor your temperatures and make sure you are below 80°C (you most likely will on stock frequency, unless your cooling is very bad).
  - Continue raising both your All Core and Uncore and do quick stress tests. Eventually, you will either encounter instability or temperatures above 80°C.
  - If temperatures are too high, you can try lowering your VCORE (P = I x V).
  - If you encounter instability, lower your All Core and Uncore by 100 Mhz and start raising only one at a time from now on (All Core will most likely clock higher than Uncore).
  - Ultimately, stress test for 1-4h to maximize long-term stability.
