# 0. Table of contents
  1. [Importance of low input lag](https://github.com/BoringBoredom/PC-Optimization-Hub/blob/main/README.md#1-importance-of-low-input-lag)
  2. [Physical setup](https://github.com/BoringBoredom/PC-Optimization-Hub/blob/main/README.md#2-physical-setup)
  3. [BIOS](https://github.com/BoringBoredom/PC-Optimization-Hub/blob/main/README.md#3-bios)
  4. [Hardware clocking](https://github.com/BoringBoredom/PC-Optimization-Hub/blob/main/README.md#4-hardware-clocking)
  5. [Windows](https://github.com/BoringBoredom/PC-Optimization-Hub/blob/main/README.md#5-windows)
  6. [Tools & resources](https://github.com/BoringBoredom/PC-Optimization-Hub/blob/main/README.md#6-tools--resources)
# 1. Importance of low input lag
  - ["While participants performed dragging and scribbling tasks, very low levels of latency could be discriminated, i.e., ~1 versus 2 milliseconds while dragging"](https://www.semanticscholar.org/paper/In-the-blink-of-an-eye%3A-investigating-latency-Ng-Annett/386a15fd85c162b8e4ebb6023acdce9df2bd43ee)
  - [visual demonstration of 10 vs 1 milliseconds](https://www.youtube.com/watch?v=vOvQCPLkPt4&feature=youtu.be&t=80)
# 2. Physical setup
  - Make sure your outlets are properly grounded.
  - If you don't have enough outlets, buy a proper power strip ( < power conditioner < voltage regulator) and connect all devices directly to it. Only connect your hardware (no phone chargers and other stuff).
  - Disconnect all things you don't use from your motherboard. E.g. front USB, front audio, RGB, hard drive activity LED, system power LED, reset button etc.
  - Move all devices that have electric or electromagnetic fields away from your PC and peripherals. E.g. router, power strip/conditioner, voltage regulator etc.
  - Make sure none of your cables are touching each other and untangle them. This applies to everything, including power and peripheral cables.
  - Connect your mouse to the USB port closest to your PCH (Intel) / CPU (AMD). It's usually the one closer to the motherboard next to the PS/2 port(s).
  - If your motherboard has multiple USB controllers, offload your other devices to them. Lower their polling rates to an acceptable level. E.g. your microphone doesn't need 1000hz
  - Test both HDMI and DP on each GPU port (don't Plug & Play these).
# 3. BIOS
  - Generally, follow the principle of "Don't use it? Disable it." E.g. disable unused USB/PCI/SATA ports, RGB that can't physically be disconnected, power saving etc.
  - [r0ach' BIOS guide](https://www.overclock.net/threads/gaming-and-mouse-response-bios-optimization-guide-for-modern-pc-hardware.1433882/)
  - [Fujitsu guide](https://sp.ts.fujitsu.com/dmsp/Publications/public/wp-bios-settings-primergy-ww-en.pdf)
  - [How to change hidden settings without flashing a modded BIOS](https://github.com/BoringBoredom/IFR-Formatter)
# 4. Hardware clocking
  - I called this category *clocking* rather than *overclocking* because in the end all you do is run your silicon at its safe capabilities (which may not always be *over*clocking due to temperatures, for example).
  - ## CPU
    - [Linpack Xtreme](https://www.techpowerup.com/download/linpack-xtreme/)
    - [Prime95](https://www.mersenne.org/download/)
  - ## RAM
    - [Importance of memory clocking](https://kingfaris.co.uk/ram)
    - [Integralfx' DDR4 guide](https://github.com/integralfx/MemTestHelper/blob/master/DDR4%20OC%20Guide.md)
  - ## GPU
    - [Cancerogeno's guide](https://docs.google.com/document/d/14ma-_Os3rNzio85yBemD-YSpF_1z75mZJz1UdzmW8GE/edit)
# 5. Windows
  - I highly recommend setting up a multi-boot environment to separate the gaming and the "can-be-bloated" operating system. Keeping your programs and files on a different partition is also convenient due to both operating systems having shared access to everything and the ease of reinstalling either of them.
  - [Calypto's guide](https://docs.google.com/document/d/1c2-lUJq74wuYK1WrA_bIvgb89dUN0sj8-hO3vqmrau4/edit)
  - [Timecard's guide](https://github.com/djdallmann/GamingPCSetup)
  - ## ISO creation
    - [Drivers & integration guide](https://www.win-raid.com/f25-General-Storage-Drivers-AHCI-RAID-NVMe-and-USB.html)
    - [Rufus](https://github.com/pbatard/rufus)
    - ### ISO sources
      - [Heidoc](https://www.heidoc.net/joomla/technology-science/microsoft/67-microsoft-windows-iso-download-tool)
      - [Techbench](https://tb.rg-adguard.net/public.php)
      - [The Eye](https://the-eye.eu/public/MSDN/)
      - [DigitalRiver (W7 only)](https://digitalrivermirror.com/)
      - [KichHoatBanQuyen's list](https://docs.google.com/spreadsheets/d/14-D4tIlFp9APP0OOvQBRXvfLOYC447UygywenX5LXfo/edit)
# 6. Tools & resources
  - ## Mouse
    - [Gearsearch mouse shape comparison](https://gearsearch.gg/shape.html)
    - [RTINGS mouse shape comparison](https://www.rtings.com/mouse/tools/3d-model-shape-compare/?orientation=3D)
  - ## Mousepad
    - [Hoya's comparison sheet](https://docs.google.com/spreadsheets/d/1RAnmZxDNduaGV8kB-GCvZ0MO6d9-0j9jmrU2f8dp0Ww/edit)
  - ## Monitor
    - ### Reviews
      - [RTINGS](https://www.rtings.com/monitor/reviews/best/by-usage/gaming#conclusion)
      - [TFT Central](https://www.tftcentral.co.uk/reviews_index.htm)
    - ### Tools
      - [Blur Busters' utilities](https://www.testufo.com/)
      - [EIZO monitor test](https://www.eizo.be/monitor-test/)
      - [Custom Resolution Utility](https://www.monitortests.com/forum/Thread-Custom-Resolution-Utility-CRU)
  - ## PSU
    - [Cybenetics](https://www.cybenetics.com/index.php?option=power-supplies)
    - [TechPowerUp](https://www.techpowerup.com/review/?category=Power+Supplies&manufacturer=&pp=25&order=date)
  - ## GPU
    - [Afterburner](https://www.msi.com/Landing/afterburner)
    - [NVIDIA NVFlash](https://www.techpowerup.com/download/nvidia-nvflash/)
    - [NVCleanstall](https://www.techpowerup.com/download/techpowerup-nvcleanstall/)
    - [NVSlimmer](https://forums.guru3d.com/threads/nvslimmer-nvidia-driver-slimming-utility.423072/)
    - [GPU-Z](https://www.techpowerup.com/gpuz/)
    - [Superposition](https://benchmark.unigine.com/superposition)
    - [NVIDIA Profile Inspector](https://github.com/Orbmu2k/nvidiaProfileInspector)
  - ## CPU
    - ### Documentation
      - [Intel resources](https://www.intel.com/content/www/us/en/products/docs/processors/core/core-technical-resources.html)
    - ### Tools
      - [CPU-Z](https://www.cpuid.com/softwares/cpu-z.html)
  - ## RAM
    - ### Documentation
      - [DDR4 basics](https://www.systemverilog.io/)
      - [DDR4 JEDEC paper](http://www.softnology.biz/pdf/JESD79-4B.pdf)
    - ### Tools
      - [ASRock Timing Configurator 4.0.4](https://download.asrock.com/Utility/Formula/TimingConfigurator(v4.0.4).zip)
      - [ASUS MemTweakIt 2.02.48](https://cdn.discordapp.com/attachments/653171331256549386/755097007240249416/MemTweakIt_V20248.zip)
      - [Intel Memory Latency Checker](https://software.intel.com/content/www/us/en/develop/articles/intelr-memory-latency-checker.html)
      - [AIDA](https://www.aida64.com/downloads/NzI2ODhjM2U=)
      - [HCI MemTest](https://hcidesign.com/memtest/)
      - [Karhu RAM Test](https://www.karhusoftware.com/ramtest/)
      - [TestMem5](https://testmem.tz.ru/testmem5.htm) + [anta777's config](https://bit.ly/2MUvl6n)
      - [OCCT](https://www.ocbase.com/)
  - ## Storage
    - ### Reviews
      - [TechPowerUp](https://www.techpowerup.com/review/?category=SSD&manufacturer=&pp=25&order=date)
    - ### Tools
      - [WinDirStat](https://sourceforge.net/projects/windirstat/)
      - [Total Commander](https://www.ghisler.com/)
  - ## BIOS
    - [Win-Raid modding section](https://www.win-raid.com/f16-BIOS-Modding-Guides-and-Problems.html)
    - [Cancerogeno's compendium](https://sites.google.com/view/cancerogenoslab/bios-mods-and-tools)
  - ## Windows
    - ### Documentation
      - [Windows Internals](https://docs.microsoft.com/en-us/sysinternals/resources/windows-internals)
    - ### Tools
      - [HWInfo](https://www.hwinfo.com/download/) + [LogViewer](https://www.hwinfo.com/forum/threads/logviewer-for-hwinfo-is-available.802/)
      - [CapFrameX](https://github.com/CXWorld/CapFrameX)
      - [Sysinternals](https://docs.microsoft.com/en-us/sysinternals/downloads/)  (huge compendium)
      - [Nirsoft's Tools](https://www.nirsoft.net/utils/index.html) (huge compendium)
      - [Windows Performance Analyzer](https://docs.microsoft.com/en-us/windows-hardware/test/wpt/windows-performance-analyzer)
      - [Process Lasso](https://bitsum.com/)
      - [Power Plan Settings Explorer](https://forums.guru3d.com/threads/windows-power-plan-settings-explorer-utility.416058/)
      - [Timer Resolution Service](https://forums.guru3d.com/threads/windows-timer-resolution-tool-in-form-of-system-service.376458/)
      - [NSudo](https://github.com/M2Team/NSudo)
      - [Intel VTune Profiler](https://software.intel.com/content/www/us/en/develop/tools/vtune-profiler.html)
      - [Compatibility Manager](https://github.com/Skymirrh/CompatibilityManager)
      - [Prio](https://www.prnwatch.com/prio/)
      - [Ripcord](https://cancel.fm/ripcord/)
      - [Foobar2000](https://www.foobar2000.org/)
      - [VC++ Redist. AIO (TPU)](https://www.techpowerup.com/download/visual-c-redistributable-runtime-package-all-in-one/)
      - [VC++ Redist. AIO (abbodi1406)](https://github.com/abbodi1406/vcredist)
      - [Quick CPU](https://coderbag.com/product/quickcpu)
      - [Mouse Tester](https://github.com/dobragab/MouseTester)
      - [MSI Utility](https://forums.guru3d.com/threads/windows-line-based-vs-message-signaled-based-interrupts-msi-tool.378044/)
      - [Microsoft Interrupt Affinity Policy Tool](http://download.microsoft.com/download/9/2/0/9200a84d-6c21-4226-9922-57ef1dae939e/interrupt_affinity_policy_tool.msi)
      - [Device Remover](https://www.majorgeeks.com/files/details/device_remover_543c.html)
      - [Latencymon](https://www.resplendence.com/latencymon)
      - [Liblava](https://github.com/liblava/liblava-demo)
  - ## Miscellaneous
    - [Geizhals database](https://geizhals.eu/) (useful for finding specific hardware due to the very extensive filtering functionality)
    - [Virustotal](https://www.virustotal.com/gui/home/upload)
    - [Hybrid Analysis](https://www.hybrid-analysis.com/)
