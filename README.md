# Importance of low input lag

- ["While participants performed dragging and scribbling tasks, very low levels of latency could be discriminated, i.e., ~1 versus 2 milliseconds while dragging"](https://doi.org/10.1145/2556288.2557037).
- [Visual demonstration of 1 vs. 10 milliseconds](https://youtu.be/vOvQCPLkPt4?t=80)
- ["The average difference in aiming task completion (the time it takes to acquire and shoot a target) between a 12ms and 20ms PCs was measured to be 182ms - that is about 22 times the system latency difference."](https://www.nvidia.com/en-us/geforce/news/reflex-low-latency-platform/#why-does-system-latency-matter)
- ["In all studies, the trend shows continued improvements all the way toward zero latency."](https://developer.nvidia.com/blog/aiming-faster-in-games-with-low-computer-system-latency/)
- ["In the first part, perceptual user experience under different jitter levels was examined using the ISO 4120:2004 triangle test protocol, and a jitter of over 0.3 ms could be perceived by sensitive subjects."](https://dl.acm.org/doi/10.1145/3472749.3474783)
- [Summary in the form of an infographic](content/importance%20of%20low%20input%20lag/latency.png)
- ["What Frame Rate is Needed to Simulate Reality?"](https://youtu.be/7zky-smR_ZY)

# Disclaimer

- Due to the sheer complexity of hardware and software and differences between various architectures, your mileage may vary. However, it is useful to be aware of things that can impact user experience and adjust them according to your needs.
- Create a personal document and keep track of everything you do. Adopt a systematic approach with proper testing methodologies, instead of just blindly changing many settings at once. Some settings are trade-offs between latency and frame time consistency / graphics quality. Some settings may not show a visible impact at first due to other bottlenecks.

# Data Collection

- [FrameView](https://www.nvidia.com/en-us/geforce/technologies/frameview/) and [PresentMon](https://github.com/GameTechDev/PresentMon) can measure both frame times and [PC Latency](content/data%20collection/nvidia-reflex-end-to-end-systeme-latency-pipline.png). You can upload the CSVs [here](https://boringboredom.github.io/Frame-Time-Analysis/) to visualize the frame time data, or [here](https://boringboredom.github.io/tools/latencygrapher) to visualize the PC Latency data. [FrameView's PC Latency metric is only available in supported games](https://www.nvidia.com/en-us/geforce/technologies/reflex/supported-products/).

# Physical setup

- [Do not daisy-chain power cables](content/physical%20setup/psu%20cables.png). Be careful not to short the loose ends if you have any.
- [Mount your AIO cooler properly.](https://youtu.be/BbGomv195sk)
- Keep your PC clean. Clogged heat sinks and dust filters will reduce airflow and consequently heat dissipation. Furthermore, ["dust may cause electrical leakage, shorting and opening of PCBs under different conditions"](https://www.circuitinsight.com/pdf/impact_of_dust_ipc.pdf).
- Check the USB layout of your system with [USB Device Tree Viewer](https://www.uwe-sieber.de/usbtreeview_e.html). Avoid ports that are connected to nested hubs. [Ryzen CPUs have a dedicated USB controller](https://images.anandtech.com/doci/14161/X570.png). Check your motherboard's manual or HWiNFO to find out which ports are routed directly to the CPU.
- If your motherboard has multiple USB controllers, [offload](https://forums.blurbusters.com/viewtopic.php?f=10&t=7618#p58449) your other devices to them. Lower the polling rate of low-priority devices to an acceptable level, if possible ([1](https://youtu.be/duGC4MCktV0)).
- Cable type and ports can potentially produce different results ([1](https://forums.blurbusters.com/viewtopic.php?t=5533#p42369) [2](https://forums.blurbusters.com/viewtopic.php?t=6919#p51775)) (don't Plug & Play these). [Don't cheap out on cables](https://www.youtube.com/watch?v=XFbJD6RE4EY). Both [HDMI](https://www.hdmi.org/spec/premiumcable) and [DisplayPort](https://www.displayport.org/product-category/cables-adaptors/) have certification programs.
- [Electromagnetic interference](https://en.wikipedia.org/wiki/Electromagnetic_interference) and issues with the electrical installation (e.g., [ground loops](<https://en.wikipedia.org/wiki/Ground_loop_(electricity)>)) can cause unintended behavior of electronic components, potentially increasing input lag ([1](https://forums.blurbusters.com/viewtopic.php?f=24&t=9133#p71950) [2](https://forums.blurbusters.com/viewtopic.php?f=10&t=7168&start=30#p62185)).  
  Here are some resources: [1](https://github.com/djdallmann/GamingPCSetup/blob/master/CONTENT/RESEARCH/ELECTRICAL/README.md#electrical) [2](https://github.com/djdallmann/GamingPCSetup/blob/master/CONTENT/TECHNICAL%20REFERENCES/README.md#electrical)
- ["EMC tests were developed to make them easier to perform, provide better repeatability from one lab to another, and reduce testing costs. But even though the EUT may pass its EMC tests, it still may fail when it's put into service. Laboratory tests performed in accordance with the standards are not adequate to guarantee that an EMC failure will not occur during actual operation because the tests do not represent the operational EME."](https://www.evaluationengineering.com/home/article/13003718/emc-failures-happen)  
  Here are some examples: [1](https://bit-tech.net/news/tech/motherboards_not_passing_emi_tests/1/) [2](https://www.theverge.com/circuitbreaker/2017/2/3/14496044/lg-ultrafine-5k-display-router-fix-redesign) [3](https://edition.cnn.com/2021/01/25/tech/iphone-12-medical-device-interference/index.html) [4](https://www.techpowerup.com/review/corsair-ax1600i/11.html#:~:text=The%20Corsair%20AX1600i%20failed%20here.%20We%20noticed%20increased%20EMI%20emissions%20with%20lower%20frequencies.) [5](https://www.techpowerup.com/review/evga-supernova-t2-1600/10.html#:~:text=As%20you%20can%20easily%20figure%20by%20looking%20at%20the%20graph%20above,%20EVGA's%20PSU%20failed%20to%20pass%20our%20EMC%20tests.) [6](https://www.techpowerup.com/review/be-quiet-dark-power-pro-1500-w/10.html#:~:text=There%20are%20some%20high%20EMI%20spikes,%20with%20the%20more%20severe%20one%20close%20to%201%20MHz.) [7](https://www.techpowerup.com/review/seasonic-connect-750w/11.html#:~:text=EMI%20noise%20is%20increased%20at%20frequencies%20below%201%20MHz.) [8](https://www.techpowerup.com/review/corsair-ax1000/5.html#:~:text=There%20are%20two%20high%20spurs%20that%20go%20over%20the%20limits.) [9](https://www.techpowerup.com/review/be-quiet-dark-power-pro-11-1000w/10.html#:~:text=EMI%20noise%20was%20higher%20than%20it%20should%20be%20at%20low%20frequencies,%20so%20this%20PSU%20didn't%20do%20too%20well%20in%20this%20test.) [10](https://www.techpowerup.com/review/chieftronic-powerplay-750-w/10.html#:~:text=Three%20spurs%20go%20over%20the%20limit%20with%20the%20QP%20detector.) [11](https://www.techpowerup.com/review/corsair-ax1000/5.html#:~:text=There%20are%20two%20high%20spurs%20that%20go%20over%20the%20limits.) [12](https://www.techpowerup.com/review/corsair-rm650i/11.html#:~:text=While%20performance%20at%20low%20frequencies%20could%20be%20better,%20EMI%20is%20kept%20at%20very%20low%20levels%20above%201%20MHz.) [13](https://www.tomshardware.com/reviews/phanteks-amp-series-650w-power-supply-review/4#:~:text=two%20spurs%20exceeding%20the%20corresponding%20limits)
- Make sure your home is properly grounded. TT systems are preferred due to low interference ([1](https://blog.phoenixcontact.com/marketing-sea/2019/01/grounding-system-types-according-to-ieee-standard/) [2](http://drchrisbarnes.co.uk/LV1.htm) [3](https://en.wikipedia.org/wiki/Earthing_system#TT_network)).
- Avoid unnecessarily long cables and prefer thick shielded ones.
- Disconnect everything you don't use from your motherboard to minimize the risk of [coupling](https://youtu.be/950XhSPanlA) and interference. E.g., front USB, front audio, (RGB) LEDs ([1](http://www.ledbenchmark.com/faq/LED-interference-issues.html) [2](https://www.igorslab.de/en/realtek-alc-4080-with-sound-cuts-and-noise-random-noise-also-on-analog-line-out-causes-and-a-first-workaround/#:~:text=initial%20testing%20showed%20that%20motherboards%20that%20offer%20complete%20disabling%20of%20RGB%20functionality%20in%20the%20BIOS%20no%20longer%20experienced%20the%20problem%20without%20RGB)), hard drive activity LED, system power LED, reset button etc.
- Move all devices that have electromagnetic fields away from your PC and peripherals. E.g., [router](content/physical%20setup/router.jpg), power strip/[conditioner](content/physical%20setup/conditioner.jpg), voltage regulator etc.  
  ["A typical PC can be upset with an electric field strength of 48 V/m, whereas an unshielded PC board requires about 9 V/m."](https://doi.org/10.1109/EMCSA.2009.5349776)
- Make sure there is enough space between your cables ([1](https://forums.blurbusters.com/viewtopic.php?f=10&t=7569&start=470#p64674) [2](https://www.phidgets.com/docs/Improving_Phidgets_Hardware_Reliability#Device_Resets_.28Due_to_Cable_to_Cable_Interference.29) [3](https://en.wikipedia.org/wiki/Electrical_cable#Cables_and_electromagnetic_fields) [4](content/physical%20setup/psu%20cable.jpg) [5](content/physical%20setup/keyboard%20cable.jpg)) and untangle them. This applies to everything, including power and [peripheral](content/physical%20setup/mouse%20cable.png) cables.

# Peripherals

- Turn off (RGB) LEDs since USB current output is very limited ([USB 2: 0.5 A, USB 3: 0.9 A](https://en.wikipedia.org/wiki/USB)). Moreover, ["running an RGB effect/animation can take a great toll on the MCU. It requires a lot of processing power and will delay other processes."](https://blog.wooting.nl/what-influences-keyboard-speed/) ([1](https://www.techpowerup.com/review/endgame-gear-xm1-rgb/5.html#:~:text=tracking%20quality%20takes%20a%20hit%20as%20soon%20as%20RGB%20is%20enabled) [2](https://www.techpowerup.com/review/roccat-kone-pro-air/5.html#:~:text=after%20having%20disabled%20all%20RGB%20lighting,%20these%20outliers%20disappeared%20entirely))
- ## Mouse
  - ### Wired vs. Wireless
    - The convenience of cordless mice is very appealing. However, there are significant drawbacks. Nowadays, [2.4 GHz](https://en.wikipedia.org/wiki/2.4_GHz_radio_use) is everywhere, causing a lot of interference. Additionally, the [inherent transmission overhead](content/peripherals/wireless%20overhead.png) and aggressive power saving mechanisms ([1](content/peripherals/hero%20power%20saving.PNG) [2](https://www.overclock.net/threads/8khz-wireless.1791955/#post-28824715)) affect both motion ([1](https://youtu.be/Zn7WjyIvAWA?t=176) [2](https://www.techpowerup.com/review/asus-rog-pugio-ii/5.html#:~:text=wireless%20delay%20is%20somewhere%20between%201.5%E2%80%932%20ms) [3](https://www.techpowerup.com/review/asus-rog-chakram-mouse/5.html#:~:text=wireless%20delay%20of%20roughly%201.5%20ms) [4](https://www.techpowerup.com/review/roccat-kain-200-aimo/5.html#:~:text=wireless%20delay%20of%201.5%E2%80%932%20ms) [5](https://www.techpowerup.com/review/razer-viper-ultimate/5.html#:~:text=wireless%20delay%20of%20around%201%20ms) [6](https://www.techpowerup.com/review/logitech-pro-wireless-mouse/5.html#:~:text=measured%200.5%E2%80%931%20ms) [7](https://www.techpowerup.com/review/dream-machines-dm6-holey-duo/5.html#:~:text=wireless%20delay%20of%20roughly%201%20ms) [8](https://www.techpowerup.com/review/asus-rog-keris-wireless/5.html#:~:text=wireless%20delay%20of%20roughly%201.5%20ms) [9](https://www.techpowerup.com/review/razer-deathadder-v2-pro/5.html#:~:text=wireless%20delay%20of%20at%20least%202%20ms) [10](https://www.techpowerup.com/review/steelseries-aerox-3-wireless/5.html#:~:text=wireless%20delay%20of%20roughly%201%20ms) [11](https://www.techpowerup.com/review/glorious-model-o-wireless/5.html#:~:text=wireless%20delay%20of%20roughly%201%E2%80%931.5%20ms)) and [click](https://twitter.com/CaIypto/status/1354186350665363457/photo/1) latency.
  - ### DPI
    - Depending on your mouse, preferred cm/360°, [mouse pad](content/peripherals/mousepad.png) and FOV in games, you may want to experiment with different DPI. Higher DPI reduces the latency between hand motion and the sensor acknowledging a change ([1](content/peripherals/dpi.PNG) [2](https://youtu.be/mwf_F2VboFQ?t=458) [3](https://youtu.be/6AoRfv9W110) [4](https://youtu.be/imYBTj2RXFs?t=275)) and improves [motion clarity](https://youtu.be/QrF_e5vKqPk) and accuracy ([1](https://i0.hdslb.com/bfs/article/watermark/ac7bdde084e67d365ecb435aa8fc3195992b5cbe.jpg@1256w_678h_!web-article-pic.avif) [2](https://www.bilibili.com/read/cv11545206) [3](https://i0.hdslb.com/bfs/article/watermark/97e28f38daae36aa3e0ec43f26936590c684799f.png@1256w_676h_!web-article-pic.avif) [4](https://www.bilibili.com/read/cv10950469)). Beware of smoothing and other jitter reduction technologies kicking in at various thresholds. To counteract the increased sensitivity on the Desktop and in game menus, you can adjust the [Windows sensitivity](https://liquipedia.net/counterstrike/Mouse_Settings#Windows_Sensitivity).
    - [Windows Sensitivity Calculator](https://boringboredom.github.io/tools/winsenscalculator)
    - Finding your individual approximate point of diminishing returns (taking 1000 Hz as example):
      - Run [MouseTester](https://github.com/valleyofdoom/MouseTester) and move your mouse unidirectionally at a velocity similar to your slowest realistic tracking speed.
      - Set the graph to **_Interval vs. Time_**.
      - Values greater than or equal to 2 ms indicate that the mouse hasn't reported motion data in the previous **_value - 1_** poll(s) (assuming other factors such as system or interference have been ruled out).
      - Raise your DPI until all polls contain motion data.
  - ### Polling rate
    - Higher polling rate [reduces latency](https://youtu.be/mwf_F2VboFQ?t=458) and improves motion clarity ([1](https://youtu.be/gOQNRvJbpmk?t=540) [2](https://forums.blurbusters.com/viewtopic.php?f=10&t=7569#p57804)).
    - [How to disable Interrupt Moderation](content/xhci%20imod/xhci%20imod.md#how-to-persistently-disable-xhci-interrupt-moderation)
  - ### Lens cleaning
    - A [balloon pump](https://www.magictricks.com/assets/images/trickspix/balloonpump-basic.jpg) will do the job without risking physical damage to the polycarbonate lens ([1](https://dtsheet.com/doc/1305617/lens-datasheet---pixart-imaging-inc.) [2](https://manualzz.com/doc/43036065/lens-datasheet---pixart-imaging-inc.) [3](https://youtu.be/XkUIePwhrc4?t=73)).
- ## Monitor
  - ### Capped FPS vs. VRR vs. uncapped FPS
    - There are a lot of variables involved: GPU workload, sustained frame rate, type of frame rate limiter (some limiters have large variation), OS, monitor's refresh rate, [NVIDIA Reflex](https://www.nvidia.com/en-us/geforce/technologies/reflex/supported-products/), [AMD Anti-Lag 2](https://www.amd.com/en/products/graphics/technologies/fidelityfx/supported-games.html#fsr4-item-2f4d78e11f-tab) etc.
    - [Input lag increases as GPU workload increases.](https://youtu.be/8ZRuFaFZh5M?t=817)
    - [VRR](https://youtu.be/dPMHEyz38TM?t=289) and [V-Sync](https://youtu.be/rs0PYCpBJjc?t=202) increase input lag.
    - #### Frame mistiming
      - ##### V-Sync off
        - This is called tearing.
        - [Visual demonstration](content/peripherals/mistiming/mistiming.md)
      - ##### V-Sync on
        - This is called judder ([1](https://www.youtube.com/watch?v=CuEZIJDEQyo) [2](https://www.howtogeek.com/753131/what-is-judder-and-why-do-tvs-have-this-problem/)).
        - ##### Visual demonstration
          - [Blur Busters' motion test with preconfigured settings](https://testufo.com/framerates-versus#photo=alien-invasion.png&pps=960&framepacingerror=0&direction=rtl&framerate=180&compare=0&showfps=1) (browser's hardware acceleration must be enabled)
          - Test 1: Set the frame rate to half of your monitor's refresh rate.
          - Test 2: Set the frame rate 5-10 FPS **_below_** half of your monitor's refresh rate.
          - Test 3: Set the frame rate 5-10 FPS **_above_** half of your monitor's refresh rate.
          - Test 2 & 3 will stutter, while Test 1 will be smooth.
      - [Further information](https://forums.blurbusters.com/viewtopic.php?t=4914&start=130#p51780)
      - To prevent mistiming, you can either use VRR or cap your FPS at various values depending on your monitor's refresh rate. Consider your [1% and 0.1% Lows](https://youtu.be/uXepIWi4SgM) when choosing a value. There are two formulae (X = monitor's refresh rate, Y = any positive integer):
        - X \* Y
        - X / Y if X %Y = 0
      - [FPS Cap Calculator](https://boringboredom.github.io/tools/fpscapcalculator)
  - ### Post processing
    - ["Any image processing done on your monitor increases latency. Even if base response time is 1ms, should the monitor then add refinements like HDR, dynamic brightness/contrast, edge sharpening, local dimming and so forth – well, latency increases. Remember the basic rule: image processing means lag."](https://www.benq.com/en-ap/knowledge-center/knowledge/gaming-monitor-input-lag-versus-response-time-whats-the-difference-and-why-should-i-care.html)

# BIOS

- Generally, follow the principle of "Don't use it? Disable it." E.g., disable all power saving features, unused network/audio/SATA controllers, unused USB/PCI/DIMM/SATA ports, (RGB) LEDs that can't physically be disconnected etc.
- [UEFI Editor](https://boringboredom.github.io/UEFI-Editor/)
- [How to change hidden settings without flashing a modded BIOS](https://github.com/BoringBoredom/UEFI-Editor/blob/master/README.md#how-to-change-hidden-settings-without-flashing-a-modded-bios)
- ## Optimization guides
  - [Fujitsu guide](https://sp.ts.fujitsu.com/dmsp/Publications/public/wp-bios-settings-primergy-ww-en.pdf)
  - [Congatec guide](https://www.congatec.com/fileadmin/user_upload/Documents/Application_Notes/AN40_BIOS_Optimization_For_Real-time_Applications.pdf)

# Hardware clocking

- I called this category _clocking_ rather than _overclocking_ because in the end all you do is run your components at their safe capabilities (which may not always be *over*clocking due to temperature, for example).
- A stable system should be able to run anything indefinitely. A single error is one too many.
- When raising clocks, always benchmark every change and verify that the performance scales positively and the variation is very low. Due to error correction, higher clocks may not cause errors in stress tests but can result in "identical" performance, worse performance or higher variation.
- Beware of degradation by high voltage, temperature and current.
- GPU and ambient temperature (e.g., summer vs. winter) will significantly impact memory temperature. Here are some things you can do while stress testing to simulate a more realistic scenario:
  - Run a GPU heat generator.
  - Mount a hair dryer to blow hot air on the memory.
  - Turn off case fans.
  - Turn up room heaters.
- Avoid monitoring programs (e.g., HWiNFO) while stress testing, since they have a large performance impact.
- CPU and RAM should be treated as one unit and adjusted and stress tested together.
- Resources: [1](https://skatterbencher.com/) [2](https://www.youtube.com/@ActuallyHardcoreOverclocking/videos) [3](https://github.com/integralfx/MemTestHelper/blob/oc-guide/DDR4%20OC%20Guide.md#table-of-contents)
- ## Stress testing
  - [StresKit](https://github.com/valleyofdoom/StresKit)
  - [Memory](https://github.com/integralfx/MemTestHelper/blob/oc-guide/DDR4%20OC%20Guide.md#recommended)
  - Test with a variety of programs/configs, since the algorithms differ. One may not fail at all, while another may fail within minutes.
- ## GPU (NVIDIA)
  - [Cancerogeno's guide](https://docs.google.com/document/d/14ma-_Os3rNzio85yBemD-YSpF_1z75mZJz1UdzmW8GE/edit)
- ## Temperature
  - [Impact on DDR5](https://www.techpowerup.com/review/ddr5-temperature-variable-analysis/3.html)
  - ["Charge leakage rate of DRAM cells approximately doubles for every 10°C increase in the temperature"](https://www.pdl.cmu.edu/PDL-FTP/NVM/chargecache_low-latency-dram_hpca16.pdf).
  - ["The load has increased the main board temperature by 5 deg. (centigrade scale) only, but the influence to the measured performance counter frequency is quite considerable."](http://www.windowstimestamp.com/description)
  - ["According to a report on reliability prediction of electronic equipment prepared by the U.S. Department of Defense, the failure factor, which is relative failure rate at any temperature over failure rate at 75 °C, increases exponentially with increasing the device temperature as demonstrated in Fig. 3. Pedram and Nazarian also reported that more than 50% of all integrated circuit (IC) failures are related to thermal issues. Thus a rule of thumb is that the failure rate of electronic components can be halved for each 10 °C reduction in their junction temperature and the cooler the devices operate, the more reliable they are."](https://doi.org/10.1016/j.rser.2017.04.112)
  - ["The operating leakage current of an aluminium electrolytic capacitor with non-solid electrolyte is extremely dependent on the temperature and voltage."](https://tadiranbatteries.de/pdf/applications/leakage-current-properties-of-modern-electrolytic-capacitors.pdf)
  - Conclusion: Maintaining near ambient temperature of components is desirable.
  - ### Controlling temperature
    - Manually set voltages and clocks of all components.
    - Use zip-ties to extend fans over VRMs, RAM and PCH. Avoid CPU air coolers due to incompatibility with dedicated VRM and RAM cooling.
    - Liquid cool all components (expensive).

# Windows

- The never-ending background bloat of Windows reduces performance significantly ([1](https://youtu.be/hwNAa_OdP1w) [2](https://youtu.be/yVNkMNVv4Y4) [3](https://youtu.be/NzAeAFudylI)).  
  Note: I am not advocating using pre-made ISOs; on the contrary, you should make your own.
- I highly recommend [setting up a multi-boot environment](content/multi-booting/multi-booting.md#how-to-multi-boot-windows-7-10-in-uefi-mode-on-a-single-drive) to separate the gaming and the "can-be-bloated" operating system. Keeping your programs and files on a different partition (separate from operating system partitions) is also convenient due to all operating systems having shared access to everything and the ease of reinstalling either of them without having to back up your data.
- As usual, disable everything you don't explicitly need and avoid installing unnecessary and bloated drivers (included in, e.g., Realtek audio or gaming peripheral software).
- A lot of the default system tools lack functionality. For example, the Task Manager is an inaccurate representation of system load since it only displays Core usage on a very superficial level. It doesn't account for things like [context switching](https://en.wikipedia.org/wiki/Context_switch), which can be very expensive.  
  Here are some supplements for various system tools ([Sysinternals](https://learn.microsoft.com/en-us/sysinternals/downloads/) and [Nirsoft](https://www.nirsoft.net/utils/index.html) have a lot more):
  - Task Manager: [Process Explorer](https://learn.microsoft.com/en-us/sysinternals/downloads/process-explorer) with [modified settings](content/windows/process%20explorer%20settings.reg)
  - Startup section of Task Manager: [Autoruns](https://learn.microsoft.com/en-us/sysinternals/downloads/autoruns)
  - Services: [Serviwin](https://www.nirsoft.net/utils/serviwin.html)
  - Device Manager: [DevManView](https://www.nirsoft.net/utils/device_manager_view.html)
- [NVIDIA Profile Inspector](https://www.pcgamingwiki.com/wiki/Nvidia_Profile_Inspector) exposes a lot of settings that are hidden from the control panel.
- Whenever possible, use portable versions of programs. Sometimes installers come with background services/drivers which may run even if the program is not running. [Scoop](https://github.com/ScoopInstaller/Scoop) can help you manage them.
- ## Optimization guides
  - [Calypto's guide](https://docs.google.com/document/d/1c2-lUJq74wuYK1WrA_bIvgb89dUN0sj8-hO3vqmrau4/edit)
  - [Timecard's guide](https://github.com/djdallmann/GamingPCSetup)
  - [PC-Tuning](https://github.com/valleyofdoom/PC-Tuning)
- ## ISO creation
  - [NTLite](https://www.ntlite.com/)
  - [Drivers](https://winraid.level1techs.com/c/important-drivers/6/all) (mostly relevant for W7) & [driver integration guide](https://winraid.level1techs.com/t/guide-integration-of-drivers-into-a-win7-11-image/30793)
  - [Rufus](https://github.com/pbatard/rufus) / [Ventoy](https://github.com/ventoy/Ventoy)
  - ### ISO sources
    - Always check the legitimacy of ISOs by comparing hashes ([1](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/get-filehash?view=powershell-5.1#example-2-compute-the-hash-value-for-an-iso-file) [2](https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/certutil#-hashfile)) to [Heidoc's](https://www.heidoc.net/php/myvsdump_directory.php?letter=W) or [Adguard's](https://files.rg-adguard.net/version/f0bd8307-d897-ef77-dbd6-216fefbe94c5) hash archive.
    - [Genuine Installation Media](https://massgrave.dev/genuine-installation-media.html)
    - [OS.click](https://os.click/en)
    - [Adguard](https://uup.rg-adguard.net/index.php)
    - [KichHoatBanQuyen's list](https://docs.google.com/spreadsheets/d/14-D4tIlFp9APP0OOvQBRXvfLOYC447UygywenX5LXfo/edit)
    - [Unknown list](https://docs.google.com/spreadsheets/d/1zTF5uRJKfZ3ziLxAZHh47kF85ja34_OFB5C5bVSPumk/edit)
    - [MSDN file server](https://files.dog/MSDN/)

# Tools & resources

- ## Mouse
  - ### Information
    - [FAQ](content/peripherals/mouse%20faq.md)
    - [Newbrict's page](https://sensor.fyi/info/)
    - [Click latency database](https://github.com/NVIDIA/Reflex-Latency-Analyzer-Mouse-Database/blob/main/NVIDIA%20RLA%20Mice%20Database%20-%20Github.csv)
  - ### Reviews
    - [TechPowerUp](https://www.techpowerup.com/review/?category=Mice&manufacturer=&pp=50&order=date)
  - ### Tools
    - [EloShapes shape comparison](https://www.eloshapes.com/)
    - [RTINGS shape comparison](https://www.rtings.com/mouse/tools/3d-model-shape-compare/?orientation=3D)
    - [Mouse Sensitivity Calculator](https://www.mouse-sensitivity.com/)
    - [Aiming.Pro Sensitivity Calculator](https://aiming.pro/mouse-sensitivity-calculator)
    - [Mouse Functionality Tester](https://boringboredom.github.io/Mouse-Functionality-Tester/)
- ## Mouse pad
  - [Hoya's sheet](https://docs.google.com/spreadsheets/d/1RAnmZxDNduaGV8kB-GCvZ0MO6d9-0j9jmrU2f8dp0Ww/edit)
  - [Viscose's sheet](https://docs.google.com/spreadsheets/d/1Ix0RN4WDgRIn9uSUMy2smG_vWR3FTnZHgNpumChfHM0/edit)
- ## Keyboard
  - ["What influences keyboard input speed"](https://wooting.io/post/what-influences-keyboard-speed)
- ## Controller
  - [Gamepadla tests](https://gamepadla.com/)
  - [Input lag sheet](https://docs.google.com/spreadsheets/d/1KlRObr3Be4zLch7Zyqg6qCJzGuhyGmXaOIUrpfncXIM/edit)
- ## Monitor
  - ### Information
    - [Computer Display Reference Guide](https://rentry.co/CDRG)
    - [Factors affecting PC Monitor responsiveness](https://pcmonitors.info/articles/factors-affecting-pc-monitor-responsiveness/)
    - [UFO Motion Test Database](https://docs.google.com/spreadsheets/d/180jSMtUKHsXVWBdG9LEYmTLWcBaTAEO9d7d4SUTgmTw/edit)
    - [Monitor Panel Part Database](https://tftcentral.co.uk/monitor_panel_parts)
  - ### Reviews
    - [RTINGS](https://www.rtings.com/monitor/tools/table)
    - [TFT Central](https://www.tftcentral.co.uk/reviews_index.htm)
    - [Hardware Unboxed](https://www.youtube.com/playlist?list=PL7m5C6_P_lnXb9cHwdo0Ct1TTZ7KUwm3e)
    - [Monitors Unboxed](https://www.youtube.com/@monitorsunboxed/videos)
    - [techless](https://www.youtube.com/@techlessYT/videos)
  - ### Tools
    - [Blur Busters' utilities](https://www.testufo.com/)
    - [ApertureGrille's utilities](https://www.aperturegrille.com/software/)
    - [Lagom monitor test](http://www.lagom.nl/lcd-test/all_tests.php)
    - [EIZO monitor test](https://www.eizo.be/monitor-test/)
    - [Custom Resolution Utility](https://www.monitortests.com/forum/Thread-Custom-Resolution-Utility-CRU)
    - [ControlMyMonitor](https://www.nirsoft.net/utils/control_my_monitor.html)
    - [Open Source Response Time Tool](https://www.osrtt.com/)
    - [piLagTester](https://alantechreview.blogspot.com/2020/08/pilagtester-pro-order-page.html) (input lag and response time tester)
    - [Screen Density Calculator](https://phrogz.net/tmp/ScreenDens2In.html)
    - [Video Timings Calculator](https://tomverbeure.github.io/video_timings_calculator)
    - [Video Bandwidth Calculator](https://trychen.com/feature/video-bandwidth)
- ## PSU
  - ### Information
    - When choosing a power supply, keep in mind that there are spikes that go well beyond the average power consumption ([1](https://www.igorslab.de/wp-content/uploads/2018/12/Peak-Load.png) [2](https://www.igorslab.de/wp-content/uploads/2020/09/04-Peak-Power-1.png) [3](https://www.igorslab.de/wp-content/uploads/2020/12/03-Peak-Power.png) [4](https://tpucdn.com/review/zotac-geforce-rtx-3090-amp-extreme-holo/images/power-spikes.png) [5](https://tpucdn.com/review/asrock-radeon-rx-6900-xt-oc-formula/images/power-spikes.png)).
    - ["Defining Power Supply Voltage Ripple & Its Real-World Impact"](https://www.gamersnexus.net/guides/2053-power-supply-voltage-ripple-and-relevance)
    - [Single vs. Multi Rail](https://youtu.be/PWtKSHT2od8)
  - ### Reviews
    - [LTT Labs](https://www.lttlabs.com/categories/power-supplies)
    - [Hardware Busters](https://hwbusters.com/psus/)
    - [TechPowerUp](https://www.techpowerup.com/review/?category=Power+Supplies&manufacturer=&pp=25&order=date)
    - [Tom's Hardware](https://www.tomshardware.com/topics/power-supplies/reviews)
    - [Cybenetics](https://www.cybenetics.com/index.php?option=psu-performance-database) (does not account for fire hazards)
- ## CPU
  - ### Information
    - [Intel resources](https://www.intel.com/content/www/us/en/products/docs/processors/core/core-technical-resources.html)
    - [VRM Load-Line visualization](https://elmorlabs.com/2019-09-05/vrm-load-line-visualized/)
  - ### Tools
    - [CPU-Z](https://www.cpuid.com/softwares/cpu-z.html)
  - ### Stress testing programs
    - [StresKit](https://github.com/valleyofdoom/StresKit)
    - [Linpack Extended](https://github.com/BoringBoredom/Linpack-Extended)
    - [Linpack Xtreme](https://www.ngohq.com/linpack-xtreme.html)
    - [OCCT](https://www.ocbase.com/)
    - [Prime95](https://www.mersenne.org/download/)
    - [y-cruncher](http://www.numberworld.org/y-cruncher/)
- ## RAM
  - ### Information
    - DDR4 basics: [text](https://www.systemverilog.io/) + [video](https://youtu.be/I-9XWtdW_Co?list=PLTd6ceoshpreE_xQfQ-akUMU1sEtthFdB)
    - [DDR4 JEDEC paper](http://www.softnology.biz/pdf/JESD79-4B.pdf)
    - [B-Die list](https://translate.google.com/translate?sl=auto&tl=en&u=https://www.hardwareluxx.de/community/threads/die-ultimative-hardwareluxx-samsung-8gb-b-die-liste-alle-hersteller-13-12-20.1161530/)
    - ["How to remove modern DDR5 Heat-spreaders"](https://youtu.be/w2LnlLGBUy8)
  - ### Tools
    - [ZenTimings](https://github.com/irusanov/ZenTimings)
    - New versions of ASRock's Timing Configurator can usually be found on OCF download pages, e.g., [Z890 Taichi OCF](https://www.asrock.com/mb/Intel/Z890%20Taichi%20OCF/Specification.asp#Download) or [Z590 OC Formula](https://www.asrock.com/mb/Intel/Z590%20OC%20Formula/Specification.asp#Download).
    - [Microbenchmarks](https://github.com/clamchowder/MicrobenchmarksGui)
    - [Intel Memory Latency Checker](https://software.intel.com/content/www/us/en/develop/articles/intelr-memory-latency-checker.html)
    - [AIDA](https://www.aida64.com/downloads)
  - ### Stress testing programs
    - [StresKit](https://github.com/valleyofdoom/StresKit)
    - [Integralfx's list](https://github.com/integralfx/MemTestHelper/blob/oc-guide/DDR4%20OC%20Guide.md#recommended)
- ## GPU
  - ### Information
    - [NVAPI Driver Settings](https://docs.nvidia.com/gameworks/content/gameworkslibrary/coresdk/nvapi/NvApiDriverSettings_8h.html)
  - ### Tools
    - [Afterburner](https://www.msi.com/Landing/afterburner)
    - [NVIDIA NVFlash](https://www.techpowerup.com/download/nvidia-nvflash/)
    - [NVCleanstall](https://www.techpowerup.com/download/techpowerup-nvcleanstall/)
    - [NVSlimmer](https://forums.guru3d.com/threads/nvslimmer-nvidia-driver-slimming-utility.423072/)
    - [GPU-Z](https://www.techpowerup.com/gpuz/)
    - [NVIDIA Profile Inspector](https://github.com/Orbmu2k/nvidiaProfileInspector)
    - [NVIDIA Nsight](https://developer.nvidia.com/nsight-graphics)
    - [NVIDIA FrameView](https://www.nvidia.com/en-us/geforce/technologies/frameview/)
  - ### Stress testing programs
    - [Geeks3D's tools](https://www.geeks3d.com/dlz/#gpu_benchmarks)
    - [Unigine's tools](https://benchmark.unigine.com/)
- ## Motherboard
  - ### Information
    - [eXtensible Host Controller Interface for Universal Serial Bus (xHCI)](https://www.intel.com/content/dam/www/public/us/en/documents/technical-specifications/extensible-host-controler-interface-usb-xhci.pdf)
    - [Message Signaled Interrupts](https://www.intel.com/content/dam/www/public/us/en/documents/white-papers/msg-signaled-interrupts-paper.pdf)
- ## Storage
  - ### Reviews
    - [TechPowerUp](https://www.techpowerup.com/review/?category=SSD&manufacturer=&pp=25&order=date)
    - [Tom's Hardware](https://www.tomshardware.com/topics/storage/reviews)
    - [AnandTech](https://www.anandtech.com/Bench/SSD21)
    - [TweakTown](https://www.tweaktown.com/cat/storage/index.html)
  - ### Profiling / Monitoring / Benchmarking
    - [CrystalDiskMark](https://crystalmark.info/en/)
    - [ATTO Disk Benchmark](https://www.techpowerup.com/download/atto-disk-benchmark/)
  - ### Tools
    - [WizTree](https://diskanalyzer.com/) / [TreeSize](https://www.jam-software.com/treesize_free) / [WinDirStat](https://sourceforge.net/projects/windirstat/) (disk usage analyzer)
    - [Ventoy](https://github.com/ventoy/Ventoy) (multi-boot USB drive)
    - [Rufus](https://github.com/pbatard/rufus) (ISO mounting)
- ## BIOS
  - ### Information
    - [Win-Raid modding section](https://winraid.level1techs.com/c/bios-uefi-modding/7/all)
    - [BIOS Mods](https://www.bios-mods.com/forum/)
  - ### Tools
    - [UEFI Editor](https://boringboredom.github.io/UEFI-Editor/)
    - [Cancerogeno's compendium](https://sites.google.com/view/cancerogenoslab/bios-mods-and-tools)
- ## Windows
  - ### Information
    - [Windows Internals](https://learn.microsoft.com/en-us/sysinternals/resources/windows-internals)
    - [Windows changelog](https://www.changewindows.org/platforms/pc)
    - [Group Policy Administrative Templates Catalog](https://admx.help/)
    - [Presentation Model](https://wiki.special-k.info/en/Presentation_Model)
  - ### Profiling / Monitoring / Benchmarking
    - [HWiNFO](https://www.hwinfo.com/download/) & [LogViewer](https://www.hwinfo.com/forum/threads/logviewer-for-hwinfo-is-available.802/) (hardware analysis, monitoring and reporting)
    - [Benchmarking FPS](https://boringboredom.github.io/Frame-Time-Analysis/)
    - [Windows Performance Toolkit](https://learn.microsoft.com/en-us/windows-hardware/test/wpt/) ([Windows 7](https://www.microsoft.com/en-us/download/details.aspx?id=8279))
    - [Process Monitor](https://learn.microsoft.com/en-us/sysinternals/downloads/procmon)
    - [API Monitor](http://www.rohitab.com/apimonitor)
    - [Intel VTune Profiler](https://software.intel.com/content/www/us/en/develop/articles/oneapi-standalone-components.html#vtune)
    - [Intel Graphics Performance Analyzers](https://www.intel.com/content/www/us/en/developer/tools/graphics-performance-analyzers/overview.html)
    - [Processor Counter Monitor](https://github.com/opcm/pcm)
    - [MouseTester](https://github.com/valleyofdoom/MouseTester)
    - [XTW](https://github.com/valleyofdoom/xtw)
    - [Latencymon](https://www.resplendence.com/latencymon)
    - [Liblava](https://github.com/liblava/liblava)
    - [PC Clock Timing](https://www.satsignal.eu/software/net.htm) (resolution of system time calls)
    - [Dependencies](https://github.com/lucasg/Dependencies) (dll load dependency checker)
  - ### Tools
    - [Scoop](https://github.com/ScoopInstaller/Scoop) (package manager)
    - [Sysinternals](https://learn.microsoft.com/en-us/sysinternals/downloads/) (huge compendium)
    - [Nirsoft's Tools](https://www.nirsoft.net/utils/index.html) (huge compendium)
    - [NTLite](https://www.ntlite.com/) (ISO creation)
    - [O&O ShutUp10++](https://www.oo-software.com/en/shutup10)
    - [MultiTool](https://github.com/BoringBoredom/Windows-MultiTool)
    - [ReservedCpuSets](https://github.com/valleyofdoom/ReservedCpuSets)
    - [Process Lasso](https://bitsum.com/) (priority and affinity saver)
    - [ProcessPluginFramework Service](https://forums.guru3d.com/threads/processpluginframework-in-the-form-of-windows-system-service.378450/)
    - [Quick CPU](https://coderbag.com/product/quickcpu)
    - [Power Plan Settings Explorer](https://forums.guru3d.com/threads/windows-power-plan-settings-explorer-utility.416058/)
    - [Timer Resolution](https://github.com/valleyofdoom/TimerResolution)
    - VC++ Redist. AIO: [TPU](https://www.techpowerup.com/download/visual-c-redistributable-runtime-package-all-in-one/) / [abbodi1406](https://github.com/abbodi1406/vcredist)
    - [MSI Utility](https://forums.guru3d.com/threads/windows-line-based-vs-message-signaled-based-interrupts-msi-tool.378044/) (interrupt mode and priority control)
    - [Microsoft Interrupt Affinity Policy Tool](http://download.microsoft.com/download/9/2/0/9200a84d-6c21-4226-9922-57ef1dae939e/interrupt_affinity_policy_tool.msi)
    - [GoInterruptPolicy](https://github.com/spddl/GoInterruptPolicy)
    - [USB Device Tree Viewer](https://www.uwe-sieber.de/usbtreeview_e.html)
    - [DeviceTree](https://www.osronline.com/article.cfm%5Earticle=97.htm)
    - [Special K](https://wiki.special-k.info/) (game modifying framework | DO NOT USE WITH ANTI-CHEATS)
    - [EasyBCD](https://neosmart.net/EasyBCD/)
    - [Winbindex](https://winbindex.m417z.com/) (index of Windows binaries)
- ## Audio
  - ### Tools
    - [LowAudioLatency](https://github.com/spddl/LowAudioLatency) / [REAL](https://github.com/miniant-git/REAL) (audio latency reduction)
    - [Round-trip audio latency tester](https://superpowered.com/webbrowserlatency)
- ## Alternatives to bloated programs
  - Epic Games: [Legendary](https://github.com/derrod/legendary)
  - Spotify: [Foobar2000](https://www.foobar2000.org/)
  - GHUB / LGS: [Logitech Onboard Memory Manager](https://support.logi.com/hc/en-us/articles/360059641133)
  - Antivirus software: [Virustotal](https://www.virustotal.com/gui/home/upload), [Hybrid Analysis](https://www.hybrid-analysis.com/) & [uBlock Origin](https://github.com/gorhill/uBlock)
  - Chrome: [Ungoogled Chromium](https://github.com/Eloston/ungoogled-chromium)
- ## Miscellaneous
  - [Geizhals database](https://geizhals.eu/) (useful for finding specific hardware due to the very extensive filtering functionality)
  - [NVIDIA article on lag reduction](https://www.nvidia.com/en-us/geforce/guides/system-latency-optimization-guide/)
  - [Digitec return & RMA rates](https://www.digitec.ch/en/page/refreshingly-honest-digitec-galaxus-now-displays-warranty-score-and-return-rate-25950)

# [My Twitter](https://twitter.com/Bra1nlet)

# Keywords for Google indexing (ignore this)

input lag latency optimization performance gaming overclock oc windows ping debloat milliseconds fps boost increase decrease guide mouse tweak tweaks bios uefi pc overclocking 7 8.1 8 10 11 w7 w8 w8.1 w10 w11 linux steamos game gamer optimizations frametime frametimes 0.1 1 1080p 720p reaction time vrt average avg minimum maximum min max tweaking fortnite overwatch apex call of duty cs:go csgo cs2 deadlock marvel rivals dota league of legends valorant rocket league rainbow six pubg super people warzone halo infinite tarkov rust starcraft destiny ow fn cod lol kovaak aim trainer krunker battlefield bf roblox super smash bros delay delayed bloat bloated debloated steam battle origin epic games quake counter strike battle royale br intel nvidia rtx dlss fsr xess amd ati ryzen r9 r7 r5 r3 radeon rdna core i9 i7 i5 i3 lake memory ram gpu ssd nvme psu power supply emi emf emc ef power electricity coupling interference dpc isr rla reflex latency analyzer
