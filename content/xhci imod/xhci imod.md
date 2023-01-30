# How to persistently disable xHCI Interrupt Moderation

## This section is an extension of [Timecard's xHCI](https://github.com/djdallmann/GamingPCSetup/tree/master/CONTENT/RESEARCH/PERIPHERALS#q-can-you-define-the-interrupt-moderation-rate-for-usb-controllers-do-different-versions-of-windows-have-different-default-values) and [ucode's EHCI](https://www.overclock.net/threads/usb-polling-precision.1550666/page-61#post-28582024) guide and assumes having read those beforehand.

RWEverything has a CLI you can use to automate the whole process at Startup. Press **_Windows key + r_** and type **_shell:startup_**. Create a .bat file with the following content and replace **_PATH_** with the full path to RWEverything and **_ADDRESS_** with your address.

```
"PATH\Rw.exe" /Min /NoLogo /Stdout /Command="W16 0xADDRESS 0x0000"
```

---

You can find the exact address by observing changes while moving the mouse <sup>1</sup>. Click on the associated IMOD value <sup>2</sup>, [convert](https://www.calculator.net/hex-calculator.html) the decimal number in the top left <sup>3</sup> to HEX and add it to the address <sup>4</sup>. In this example, adding C0 (192 dec) results in 00000000DF1320E4.

![](https://raw.githubusercontent.com/BoringBoredom/PC-Optimization-Hub/main/content/xhci%20imod/rwe.png)

---

Sometimes the value of BAR2 is not 0x00000000 and requires a workaround.

- One method of getting the starting address is pressing **_Windows key + r_**, typing **_devmgmt.msc_**, right-clicking the xHCI controller, clicking **_Properties_** and navigating to **_Resources_**. The left value of **_Memory Range_** is your starting address.
- Another method is concatenating BAR2 and BAR1 and replacing the 4 at the end with 0. In this example BAR2 is 00000040 and BAR1 is 00100004, resulting in 0000004000100000.

![](https://github.com/BoringBoredom/PC-Optimization-Hub/raw/main/content/xhci%20imod/bar2.png)

---

If RWEverything is stuck on an address, delete the following registry key:

```
Computer\HKEY_CURRENT_USER\SOFTWARE\RW-Everything
```
