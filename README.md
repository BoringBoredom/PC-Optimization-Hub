# Importance of low input lag

- ["While participants performed dragging and scribbling tasks, very low levels of latency could be discriminated, i.e., ~1 versus 2 milliseconds while dragging"](https://doi.org/10.1145/2556288.2557037).
- [Visual demonstration of 1 vs 10 milliseconds](https://youtu.be/vOvQCPLkPt4?t=80)
- ["The average difference in aiming task completion (the time it takes to acquire and shoot a target) between a 12ms and 20ms PCs was measured to be 182ms - that is about 22 times the system latency difference."](https://www.nvidia.com/en-us/geforce/news/reflex-low-latency-platform/#why-does-system-latency-matter)
- ["In all studies, the trend shows continued improvements all the way toward zero latency."](https://developer.nvidia.com/blog/aiming-faster-in-games-with-low-computer-system-latency/)
- [Summary in form of an infographic](https://raw.githubusercontent.com/BoringBoredom/PC-Optimization-Hub/main/content/importance%20of%20low%20input%20lag/latency.png)

# Disclaimer

- Due to the sheer complexity of hardware and software and differences between various architectures, your mileage may vary. However, it is useful to be aware of things that can impact user experience and adjust them according to your needs.
- Create a personal document and keep track of everything you do. Adopt a systematic approach with proper testing methodologies instead of just blindly changing many settings at once. Some settings are trade-offs between latency and frametime consistency / graphics quality. Some settings may not show a visible impact at first due to other bottlenecks.

# Data Collection

- [FrameView](https://www.nvidia.com/en-us/geforce/technologies/frameview/) can measure both frame times and [PC Latency](https://raw.githubusercontent.com/BoringBoredom/PC-Optimization-Hub/main/content/data%20collection/nvidia-reflex-end-to-end-systeme-latency-pipline.png). You can upload the CSVs [here](https://boringboredom.github.io/Frame-Time-Analysis/) to visualize the frame time data or [here](https://boringboredom.github.io/tools/#/RLA) to visualize the PC Latency data. [The PC Latency metric is only available in supported games](https://www.nvidia.com/en-us/geforce/technologies/reflex/supported-products/).

# Physical setup

- [Do not daisy chain power cables](https://raw.githubusercontent.com/BoringBoredom/PC-Optimization-Hub/main/content/physical%20setup/psu%20cables.png). Be careful not to short the loose ends if you have any.
- [Mount your AIO cooler properly.](https://youtu.be/BbGomv195sk)
- Keep your PC clean. Clogged heatsinks and dust filters will reduce airflow and consequently heat dissipation. Furthermore, ["dust may cause electrical leakage, shorting and opening of PCBs under different conditions"](https://www.circuitinsight.com/pdf/impact_of_dust_ipc.pdf).
- [Electromagnetic interference](https://en.wikipedia.org/wiki/Electromagnetic_interference) and issues with the electrical installation (e.g. [ground loops](<https://en.wikipedia.org/wiki/Ground_loop_(electricity)>)) can cause unintended behavior of electronic components, potentially increasing input lag ([1](https://forums.blurbusters.com/viewtopic.php?f=24&t=9133#p71950) [2](https://forums.blurbusters.com/viewtopic.php?f=10&t=7168&start=30#p62185)).  
  Here are some resources: [1](https://github.com/djdallmann/GamingPCSetup/blob/master/CONTENT/RESEARCH/ELECTRICAL/README.md#electrical) [2](https://github.com/djdallmann/GamingPCSetup/blob/master/CONTENT/TECHNICAL%20REFERENCES/README.md#electrical)
- ["EMC tests were developed to make them easier to perform, provide better repeatability from one lab to another, and reduce testing costs. But even though the EUT may pass its EMC tests, it still may fail when it's put into service. Laboratory tests performed in accordance with the standards are not adequate to guarantee that an EMC failure will not occur during actual operation because the tests do not represent the operational EME."](https://www.evaluationengineering.com/home/article/13003718/emc-failures-happen)  
  Here are some examples: [1](https://bit-tech.net/news/tech/motherboards_not_passing_emi_tests/1/) [2](https://www.theverge.com/circuitbreaker/2017/2/3/14496044/lg-ultrafine-5k-display-router-fix-redesign) [3](https://edition.cnn.com/2021/01/25/tech/iphone-12-medical-device-interference/index.html) [4](https://www.techpowerup.com/review/corsair-ax1600i/11.html#:~:text=The%20Corsair%20AX1600i%20failed%20here.%20We%20noticed%20increased%20EMI%20emissions%20with%20lower%20frequencies.) [5](https://www.techpowerup.com/review/evga-supernova-t2-1600/10.html#:~:text=As%20you%20can%20easily%20figure%20by%20looking%20at%20the%20graph%20above,%20EVGA's%20PSU%20failed%20to%20pass%20our%20EMC%20tests.) [6](https://www.techpowerup.com/review/be-quiet-dark-power-pro-1500-w/10.html#:~:text=There%20are%20some%20high%20EMI%20spikes,%20with%20the%20more%20severe%20one%20close%20to%201%20MHz.) [7](https://www.techpowerup.com/review/seasonic-connect-750w/11.html#:~:text=EMI%20noise%20is%20increased%20at%20frequencies%20below%201%20MHz.) [8](https://www.techpowerup.com/review/corsair-ax1000/5.html#:~:text=There%20are%20two%20high%20spurs%20that%20go%20over%20the%20limits.) [9](https://www.techpowerup.com/review/be-quiet-dark-power-pro-11-1000w/10.html#:~:text=EMI%20noise%20was%20higher%20than%20it%20should%20be%20at%20low%20frequencies,%20so%20this%20PSU%20didn't%20do%20too%20well%20in%20this%20test.) [10](https://www.techpowerup.com/review/chieftronic-powerplay-750-w/10.html#:~:text=Three%20spurs%20go%20over%20the%20limit%20with%20the%20QP%20detector.) [11](https://www.techpowerup.com/review/corsair-ax1000/5.html#:~:text=There%20are%20two%20high%20spurs%20that%20go%20over%20the%20limits.) [12](https://www.techpowerup.com/review/corsair-rm650i/11.html#:~:text=While%20performance%20at%20low%20frequencies%20could%20be%20better,%20EMI%20is%20kept%20at%20very%20low%20levels%20above%201%20MHz.) [13](https://www.tomshardware.com/reviews/phanteks-amp-series-650w-power-supply-review/4#:~:text=two%20spurs%20exceeding%20the%20corresponding%20limits)
- Make sure your home is properly grounded. TT systems are preferred due to low interference ([1](https://blog.phoenixcontact.com/marketing-sea/2019/01/grounding-system-types-according-to-ieee-standard/) [2](http://drchrisbarnes.co.uk/LV1.htm) [3](https://en.wikipedia.org/wiki/Earthing_system#TT_network)).
- Avoid unnecessarily long cables and prefer thick shielded ones.
- Disconnect everything you don't use from your motherboard to minimize risk of [coupling](https://youtu.be/950XhSPanlA) and interference. E.g. front USB, front audio, (RGB) LEDs ([1](http://www.ledbenchmark.com/faq/LED-interference-issues.html) [2](https://www.igorslab.de/en/realtek-alc-4080-with-sound-cuts-and-noise-random-noise-also-on-analog-line-out-causes-and-a-first-workaround/#:~:text=initial%20testing%20showed%20that%20motherboards%20that%20offer%20complete%20disabling%20of%20RGB%20functionality%20in%20the%20BIOS%20no%20longer%20experienced%20the%20problem%20without%20RGB)), hard drive activity LED, system power LED, reset button etc.
- Move all devices that have electromagnetic fields away from your PC and peripherals. E.g. [router](https://raw.githubusercontent.com/BoringBoredom/PC-Optimization-Hub/main/content/physical%20setup/router.jpg), power strip/[conditioner](https://raw.githubusercontent.com/BoringBoredom/PC-Optimization-Hub/main/content/physical%20setup/conditioner.jpg), voltage regulator etc.  
  ["A typical PC can be upset with an electric field strength of 48 V/m, whereas an unshielded PC board requires about 9 V/m."](https://doi.org/10.1109/EMCSA.2009.5349776)
- Make sure there is enough space between your cables ([1](https://forums.blurbusters.com/viewtopic.php?f=10&t=7569&start=470#p64674) [2](https://www.phidgets.com/docs/Improving_Phidgets_Hardware_Reliability#Device_Resets_.28Due_to_Cable_to_Cable_Interference.29) [3](https://en.wikipedia.org/wiki/Electrical_cable#Cables_and_electromagnetic_fields) [4](https://raw.githubusercontent.com/BoringBoredom/PC-Optimization-Hub/main/content/physical%20setup/psu%20cable.jpg) [5](https://raw.githubusercontent.com/BoringBoredom/PC-Optimization-Hub/main/content/physical%20setup/keyboard%20cable.jpg)) and untangle them. This applies to everything, including power and [peripheral](https://raw.githubusercontent.com/BoringBoredom/PC-Optimization-Hub/main/content/physical%20setup/mouse%20cable.png) cables.
- Check the USB layout of your system with [USB Device Tree Viewer](https://www.uwe-sieber.de/usbtreeview_e.html). Connect your mouse (or primary input device) to the first port of the first controller (usually [this port](https://i.imgur.com/QGKAVoA.png)). [Ryzen CPUs have a dedicated USB controller](https://images.anandtech.com/doci/14161/X570.png). Check your motherboard's manual to find out which ports are routed directly to the CPU.
- If your motherboard has multiple USB controllers, [offload](https://forums.blurbusters.com/viewtopic.php?f=10&t=7618#p58449) your other devices to them. Lower their polling rate to an acceptable level. E.g. your microphone doesn't need 1000 Hz
- Cable type and ports can potentially produce different results ([1](https://forums.blurbusters.com/viewtopic.php?t=5533#p42369) [2](https://forums.blurbusters.com/viewtopic.php?t=6919#p51775)) (don't Plug & Play these). [Don't cheap out on cables](https://www.youtube.com/watch?v=XFbJD6RE4EY). Both [HDMI](https://www.hdmi.org/spec/premiumcable) and [DisplayPort](https://www.displayport.org/product-category/cables-adaptors/) have certification programs.

# Peripherals

- Turn off (RGB) LEDs since USB current output is very limited ([USB 2: 0.5 A, USB 3: 0.9 A](https://en.wikipedia.org/wiki/USB)). Moreover, ["running an RGB effect/animation can take a great toll on the MCU. It requires a lot of processing power and will delay other processes."](https://blog.wooting.nl/what-influences-keyboard-speed/) ([1](https://www.techpowerup.com/review/endgame-gear-xm1-rgb/5.html#:~:text=tracking%20quality%20takes%20a%20hit%20as%20soon%20as%20RGB%20is%20enabled) [2](https://www.techpowerup.com/review/roccat-kone-pro-air/5.html#:~:text=after%20having%20disabled%20all%20RGB%20lighting,%20these%20outliers%20disappeared%20entirely))
- ## Mouse
  - ### Wired vs. Wireless
    - The convenience of cordless mice is very appealing. However, there are significant drawbacks. Nowadays, [2.4 GHz](https://en.wikipedia.org/wiki/2.4_GHz_radio_use) is everywhere, causing a lot of interference. Additionally, the [inherent transmission overhead](https://raw.githubusercontent.com/BoringBoredom/PC-Optimization-Hub/main/content/peripherals/wireless%20overhead.png) and aggressive power saving mechanisms ([1](https://raw.githubusercontent.com/BoringBoredom/PC-Optimization-Hub/main/content/peripherals/hero%20power%20saving.PNG) [2](https://www.overclock.net/threads/8khz-wireless.1791955/#post-28824715)) affect both sensor ([1](https://youtu.be/Zn7WjyIvAWA?t=176) [2](https://www.techpowerup.com/review/asus-rog-pugio-ii/5.html#:~:text=wireless%20delay%20is%20somewhere%20between%201.5%E2%80%932%20ms) [3](https://www.techpowerup.com/review/asus-rog-chakram-mouse/5.html#:~:text=wireless%20delay%20of%20roughly%201.5%20ms) [4](https://www.techpowerup.com/review/roccat-kain-200-aimo/5.html#:~:text=wireless%20delay%20of%201.5%E2%80%932%20ms) [5](https://www.techpowerup.com/review/razer-viper-ultimate/5.html#:~:text=wireless%20delay%20of%20around%201%20ms) [6](https://www.techpowerup.com/review/logitech-pro-wireless-mouse/5.html#:~:text=measured%200.5%E2%80%931%20ms) [7](https://www.techpowerup.com/review/dream-machines-dm6-holey-duo/5.html#:~:text=wireless%20delay%20of%20roughly%201%20ms) [8](https://www.techpowerup.com/review/asus-rog-keris-wireless/5.html#:~:text=wireless%20delay%20of%20roughly%201.5%20ms) [9](https://www.techpowerup.com/review/razer-deathadder-v2-pro/5.html#:~:text=wireless%20delay%20of%20at%20least%202%20ms) [10](https://www.techpowerup.com/review/steelseries-aerox-3-wireless/5.html#:~:text=wireless%20delay%20of%20roughly%201%20ms) [11](https://www.techpowerup.com/review/glorious-model-o-wireless/5.html#:~:text=wireless%20delay%20of%20roughly%201%E2%80%931.5%20ms)) and [click](https://twitter.com/CaIypto/status/1354186350665363457/photo/1) latency.
  - ### DPI
    - Depending on your sensor, preferred cm/360°, [mousepad](https://raw.githubusercontent.com/BoringBoredom/PC-Optimization-Hub/main/content/peripherals/mousepad.png) and FOV in games, you may want to experiment with different DPI. Higher DPI reduces latency ([1](https://raw.githubusercontent.com/BoringBoredom/PC-Optimization-Hub/main/content/peripherals/dpi.PNG) [2](https://youtu.be/mwf_F2VboFQ?t=458) [3](https://youtu.be/6AoRfv9W110) [4](https://youtu.be/imYBTj2RXFs?t=275)), [improves motion clarity](https://youtu.be/QrF_e5vKqPk) and improves sensor accuracy ([1](https://i0.hdslb.com/bfs/article/watermark/ac7bdde084e67d365ecb435aa8fc3195992b5cbe.jpg) [2](https://www.bilibili.com/read/cv11545206) [3](https://i0.hdslb.com/bfs/article/watermark/97e28f38daae36aa3e0ec43f26936590c684799f.png) [4](https://www.bilibili.com/read/cv10950469)). Most modern mice are able to handle around 1800 DPI without additional smoothing (PMW3360: <2100, PMW3389: <1900, with a few exceptions). Some companies disable it or allow you to disable it entirely. To counteract the increased sensitivity on the Desktop and in game menus you can adjust the [Windows sensitivity](https://liquipedia.net/counterstrike/Mouse_Settings#Windows_Sensitivity).
    - [Windows Sensitivity Calculator](https://boringboredom.github.io/tools/#/WinSens)
    - Finding your individual approximate point of diminishing returns (taking 1000 Hz as example):
      - Run [MouseTester](https://github.com/microe1/MouseTester) and move your mouse unidirectionally at a velocity similar to your slowest realistic tracking speed.
      - Set the graph to **_Interval vs. Time_**.
      - Values greater than or equal to 2 ms indicate that the mouse hasn't reported motion data in the previous **_value - 1_** poll(s) (assuming other factors such as system or interference have been ruled out).
      - Raise your DPI until all polls contain motion data.
    - Due to the increased precision of higher DPI, the sensor will pick up finer motion which can result in "shakiness". When using a higher level of monitor overdrive, this can heavily amplify the negative impact of coronas caused by the overdrive. I recommend lowering it when raising DPI and encountering this issue.
  - ### Polling rate
    - Higher polling rate [reduces latency](https://youtu.be/mwf_F2VboFQ?t=458) and improves motion clarity ([1](https://youtu.be/gOQNRvJbpmk?t=540) [2](https://forums.blurbusters.com/viewtopic.php?f=10&t=7569#p57804)).
    - [How to disable Interrupt Moderation](https://github.com/BoringBoredom/PC-Optimization-Hub/blob/main/content/xhci%20imod/xhci%20imod.md#how-to-persistently-disable-xhci-interrupt-moderation)
  - ### Lens cleaning
    - A [balloon pump](https://www.magictricks.com/assets/images/trickspix/balloonpump-basic.jpg) will do the job without risking physical damage to the polycarbonate lens ([1](https://dtsheet.com/doc/1305617/lens-datasheet---pixart-imaging-inc.) [2](https://manualzz.com/doc/43036065/lens-datasheet---pixart-imaging-inc.)).
- ## Monitor
  - ### Capped FPS vs. VRR vs. uncapped FPS
    - There are a lot of variables involved: GPU utilization, sustained frame rate, type of frame rate limiter (some limiters have large variation), OS, monitor's refresh rate, NVIDIA Reflex (only supported by NVIDIA GPUs in a few games at the moment) etc.
    - Input lag increases as GPU workload increases ([1](https://youtu.be/8ZRuFaFZh5M?t=817) [2](https://youtu.be/dPMHEyz38TM?t=1124)).
    - [VRR](https://youtu.be/dPMHEyz38TM?t=289) and [V-Sync](https://youtu.be/rs0PYCpBJjc?t=202) increase input lag.
    - #### Frame mistiming
      - ##### V-Sync off
        - This is called tearing.
        - [Visual demonstration](https://github.com/BoringBoredom/PC-Optimization-Hub/blob/main/content/peripherals/mistiming/mistiming.md)
      - ##### V-Sync on
        - This is called judder ([1](https://www.youtube.com/watch?v=CuEZIJDEQyo) [2](https://www.howtogeek.com/753131/what-is-judder-and-why-do-tvs-have-this-problem/)).
        - ##### Visual demonstration
          - [Blur Busters' motion test with preconfigured settings](https://testufo.com/framerates-versus#photo=alien-invasion.png&pps=960&framepacingerror=0&direction=rtl&framerate=180&compare=0&showfps=1) (browser's hardware acceleration must be enabled)
          - Test 1: Set the frame rate to half of your monitor's refresh rate.
          - Test 2: Set the frame rate to 5-10 FPS **_below_** half of your monitor's refresh rate.
          - Test 3: Set the frame rate to 5-10 FPS **_above_** half of your monitor's refresh rate.
          - Test 2 & 3 will stutter while Test 1 will be smooth.
      - [Further information](https://forums.blurbusters.com/viewtopic.php?t=4914&start=130#p51780)
      - To prevent mistiming you can either use VRR or cap your FPS at various values depending on your monitor's refresh rate. Consider your [1% and 0.1% Lows](https://youtu.be/uXepIWi4SgM) when choosing a value. There are two formulae (X = monitor's refresh rate, Y = any positive integer):
        - X \* Y
        - X / Y if X %Y = 0
      - [FPS Cap Calculator](https://boringboredom.github.io/tools/#/FPSCap)
  - ### Post processing
    - ["Any image processing done on your monitor increases latency. Even if base response time is 1ms, should the monitor then add refinements like HDR, dynamic brightness/contrast, edge sharpening, local dimming and so forth – well, latency increases. Remember the basic rule: image processing means lag."](https://www.benq.com/en-ap/knowledge-center/knowledge/gaming-monitor-input-lag-versus-response-time-whats-the-difference-and-why-should-i-care.html)

# BIOS

- Generally, follow the principle of "Don't use it? Disable it." E.g. disable all power saving features, unused network/audio/SATA controllers, unused USB/PCI/DIMM/SATA ports, (RGB) LEDs that can't physically be disconnected etc.
- [UEFI Editor](https://boringboredom.github.io/UEFI-Editor/)
- [How to change hidden settings without flashing a modded BIOS](https://github.com/BoringBoredom/UEFI-Editor/blob/master/README.md#how-to-change-hidden-settings-without-flashing-a-modded-bios)
- ## Optimization guides
  - [Fujitsu guide](https://sp.ts.fujitsu.com/dmsp/Publications/public/wp-bios-settings-primergy-ww-en.pdf)
  - [Congatec guide](https://www.congatec.com/fileadmin/user_upload/Documents/Application_Notes/AN40_BIOS_Optimization_For_Real-time_Applications.pdf)
  - [r0ach's guide](https://www.overclock.net/threads/gaming-and-mouse-response-bios-optimization-guide-for-modern-pc-hardware.1433882/)

# Hardware clocking

- I called this category _clocking_ rather than _overclocking_ because in the end all you do is run your components at their safe capabilities (which may not always be *over*clocking due to temperature, for example).
- A stable system should be able to run anything indefinitely. A single error is one too many.
- When raising clocks, always benchmark every change and verify that the performance scales positively and the variation is very low. Due to error correction, higher clocks may not cause errors in stress tests but can result in "identical" performance, worse performance or higher variation.
- ## Temperature
  - ["Charge leakage rate of DRAM cells approximately doubles for every 10°C increase in the temperature"](https://www.pdl.cmu.edu/PDL-FTP/NVM/chargecache_low-latency-dram_hpca16.pdf).
  - ["The load has increased the main board temperature by 5 deg. (centigrade scale) only, but the influence to the measured performance counter frequency is quite considerable."](http://www.windowstimestamp.com/description)
  - ["According to a report on reliability prediction of electronic equipment prepared by the U.S. Department of Defense, the failure factor, which is relative failure rate at any temperature over failure rate at 75 °C, increases exponentially with increasing the device temperature as demonstrated in Fig. 3. Pedram and Nazarian also reported that more than 50% of all integrated circuit (IC) failures are related to thermal issues. Thus a rule of thumb is that the failure rate of electronic components can be halved for each 10 °C reduction in their junction temperature and the cooler the devices operate, the more reliable they are."](https://doi.org/10.1016/j.rser.2017.04.112)
  - ["The operating leakage current of an aluminium electrolytic capacitor with non-solid electrolyte is extremely dependent on the temperature and voltage."](https://tadiranbatteries.de/pdf/applications/leakage-current-properties-of-modern-electrolytic-capacitors.pdf)
  - Conclusion: Maintaining near ambient temperature of components is desirable.
  - ### Controlling temperature
    - Manually set voltages and clocks of all components.
    - Use zip-ties to extend fans over VRMs, RAM and PCH. Avoid CPU air coolers due to incompatibility with dedicated VRM and RAM cooling.
    - Liquid cool all components (expensive).
- ## Intel Lake platform (6000-10000 series)
  - [Integralfx's DDR4 guide](https://github.com/integralfx/MemTestHelper/blob/oc-guide/DDR4%20OC%20Guide.md#table-of-contents)
  - [Voltages and their impact](https://youtu.be/WK5Md-90XHQ?t=370)
  - Beware of degradation by high voltage, temperature and current. Personally, I think the voltages and temperature mentioned in the previous video are too high.
  - [Core](https://youtu.be/WK5Md-90XHQ?t=851), [Uncore and RAM](https://youtu.be/WK5Md-90XHQ?t=1116) affect each other's stability. They should be treated as one unit and adjusted and stress tested together.
  - GPU and ambient temperature (e.g. summer vs. winter) will significantly impact memory temperature. Here are some things you can do while stress testing to simulate a more realistic scenario:
    - Run a GPU heat generator.
    - Mount a hair dryer to blow hot air on the memory.
    - Turn off case fans.
    - Turn up room heaters.
  - Avoid monitoring programs (e.g. HWiNFO) while stress testing since they have a large performance impact.
  - ### CPU stress testing
    - [Linpack Extended](https://github.com/BoringBoredom/Linpack-Extended)
    - Test with a variety of different problem sizes.
    - GFlop variation should be as low as possible.
    - [Prime95](https://www.mersenne.org/download/)
  - ### Memory stress testing
    - [Options](https://github.com/integralfx/MemTestHelper/blob/oc-guide/DDR4%20OC%20Guide.md#recommended)
    - Test with a variety of programs/configs since the algorithms differ. One may not fail at all, while another may fail within minutes.
- ## GPU (NVIDIA)
  - [Cancerogeno's guide](https://docs.google.com/document/d/14ma-_Os3rNzio85yBemD-YSpF_1z75mZJz1UdzmW8GE/edit)

# Windows

- The never-ending background bloat of Windows [reduces performance significantly](https://youtu.be/hwNAa_OdP1w).  
  Note: I am not advocating using pre-made ISOs; on the contrary, you should make your own.
- I highly recommend [setting up a multi-boot environment](https://github.com/BoringBoredom/PC-Optimization-Hub/blob/main/content/multi-booting/multi-booting.md#how-to-multi-boot-windows-7-10-in-uefi-mode-on-a-single-drive) to separate the gaming and the "can-be-bloated" operating system. Keeping your programs and files on a different partition (separate from operating system partitions) is also convenient due to all operating systems having shared access to everything and the ease of reinstalling either of them without having to back up your data.
- As usual, disable everything you don't explicitely need and avoid installing unnecessary and bloated drivers (included in e.g. Realtek audio or gaming peripheral software).
- A lot of the default system tools lack functionality. For example, the Task Manager is an inaccurate representation of system load since it only displays Core usage on a very superficial level. It doesn't account for things like [context switching](https://en.wikipedia.org/wiki/Context_switch) which can be very expensive.  
  Here are some supplements for various system tools ([Sysinternals](https://docs.microsoft.com/en-us/sysinternals/downloads/) and [Nirsoft](http://www.nirsoft.net/utils/index.html) have a lot more):
  - Task Manager: [Process Explorer](https://docs.microsoft.com/en-us/sysinternals/downloads/process-explorer) with [modified settings](https://raw.githubusercontent.com/BoringBoredom/PC-Optimization-Hub/main/content/windows/process%20explorer%20settings.reg)
  - Startup section of Task Manager: [Autoruns](https://docs.microsoft.com/en-us/sysinternals/downloads/autoruns)
  - Services: [Serviwin](https://www.nirsoft.net/utils/serviwin.html)
  - Device Manager: [DevManView](https://www.nirsoft.net/utils/device_manager_view.html)
- [NVIDIA Profile Inspector](https://www.pcgamingwiki.com/wiki/Nvidia_Profile_Inspector) exposes a lot of settings that are hidden from the control panel.
- Whenever possible, use portable versions of programs. Sometimes installers come with background services/drivers which may run even if the program is not running.
- ## Optimization guides
  - [Calypto's guide](https://docs.google.com/document/d/1c2-lUJq74wuYK1WrA_bIvgb89dUN0sj8-hO3vqmrau4/edit)
  - [Timecard's guide](https://github.com/djdallmann/GamingPCSetup)
- ## ISO creation
  - [USB and storage drivers](https://www.win-raid.com/f25-General-Storage-Drivers-AHCI-RAID-NVMe-and-USB.html) (mostly relevant for W7) & [driver integration guide](https://www.win-raid.com/t750f25-Guide-Integration-of-drivers-into-a-Win-image.html)
  - [Rufus](https://github.com/pbatard/rufus) / [Ventoy](https://github.com/ventoy/Ventoy)
  - ### ISO sources
    - Always check legitimacy of ISO by comparing [hashes](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/get-filehash?view=powershell-7.1) -> [Heidoc's hash archive](https://www.heidoc.net/php/myvsdump_directory.php?letter=W)
    - [Microsoft Software Download Listing](https://ave9858.github.io/msdl/)
    - [MVS Collection](https://isofiles.bd581e55.workers.dev/)
    - [KichHoatBanQuyen's list](https://docs.google.com/spreadsheets/d/14-D4tIlFp9APP0OOvQBRXvfLOYC447UygywenX5LXfo/edit)
    - [Unknown list](https://docs.google.com/spreadsheets/d/1zTF5uRJKfZ3ziLxAZHh47kF85ja34_OFB5C5bVSPumk/edit)
    - [MSDN file server](https://files.dog/MSDN/)

# Tools & resources

- ## Mouse
  - ### Information
    - [Newbrict's page](https://sensor.fyi/info/)
    - [Click latency database](https://github.com/NVIDIA/Reflex-Latency-Analyzer-Mouse-Database/blob/main/NVIDIA%20RLA%20Mice%20Database%20-%20Github.csv)
  - ### Tools
    - [EloShapes shape comparison](https://www.eloshapes.com/)
    - [RTINGS shape comparison](https://www.rtings.com/mouse/tools/3d-model-shape-compare/?orientation=3D)
    - [Mouse Sensitivity Calculator](https://www.mouse-sensitivity.com/)
    - [Aiming.Pro Sensitivity Calculator](https://aiming.pro/mouse-sensitivity-calculator)
    - [Mouse Functionality Tester](https://boringboredom.github.io/Mouse-Functionality-Tester/)
- ## Mousepad
  - [Hoya's sheet](https://docs.google.com/spreadsheets/d/1RAnmZxDNduaGV8kB-GCvZ0MO6d9-0j9jmrU2f8dp0Ww/edit)
- ## Keyboard
  - ["What influences keyboard speed?"](https://blog.wooting.nl/what-influences-keyboard-speed/)
- ## Controller
  - [Input lag sheet](https://docs.google.com/spreadsheets/d/1KlRObr3Be4zLch7Zyqg6qCJzGuhyGmXaOIUrpfncXIM/edit)
- ## Monitor
  - ### Information
    - [Factors affecting PC Monitor responsiveness](https://pcmonitors.info/articles/factors-affecting-pc-monitor-responsiveness/)
    - [UFO Motion Test Database](https://docs.google.com/spreadsheets/d/180jSMtUKHsXVWBdG9LEYmTLWcBaTAEO9d7d4SUTgmTw/edit)
  - ### Reviews
    - [RTINGS](https://www.rtings.com/monitor/tools/table)
    - [TFT Central](https://www.tftcentral.co.uk/reviews_index.htm)
    - [Hardware Unboxed](https://www.youtube.com/playlist?list=PL7m5C6_P_lnXb9cHwdo0Ct1TTZ7KUwm3e)
  - ### Tools
    - [Blur Busters' utilities](https://www.testufo.com/)
    - [ApertureGrille's utilities](https://www.aperturegrille.com/software/)
    - [Lagom monitor test](http://www.lagom.nl/lcd-test/all_tests.php)
    - [EIZO monitor test](https://www.eizo.be/monitor-test/)
    - [Custom Resolution Utility](https://www.monitortests.com/forum/Thread-Custom-Resolution-Utility-CRU)
    - [ControlMyMonitor](https://www.nirsoft.net/utils/control_my_monitor.html)
    - [Open Source Response Time Tool](https://www.osrtt.com/)
    - [piLagTester](https://alantechreview.blogspot.com/2020/08/pilagtester-pro-order-page.html) (input lag and response time tester)
- ## PSU
  - ### Information
    - When choosing a power supply, keep in mind that there are spikes that go well beyond the average power consumption. ([1](https://www.igorslab.de/wp-content/uploads/2018/12/Peak-Load.png) [2](https://www.igorslab.de/wp-content/uploads/2020/09/04-Peak-Power-1.png) [3](https://www.igorslab.de/wp-content/uploads/2020/12/03-Peak-Power.png) [4](https://tpucdn.com/review/zotac-geforce-rtx-3090-amp-extreme-holo/images/power-spikes.png) [5](https://tpucdn.com/review/asrock-radeon-rx-6900-xt-oc-formula/images/power-spikes.png))
    - ["Defining Power Supply Voltage Ripple & Its Real-World Impact"](https://www.gamersnexus.net/guides/2053-power-supply-voltage-ripple-and-relevance)
    - [Single vs. Multi Rail](https://youtu.be/PWtKSHT2od8)
  - ### Reviews
    - [Cybenetics](https://www.cybenetics.com/index.php?option=power-supplies)
    - [TechPowerUp](https://www.techpowerup.com/review/?category=Power+Supplies&manufacturer=&pp=25&order=date)
    - [Tom's Hardware](https://www.tomshardware.com/topics/power-supplies/reviews)
- ## CPU
  - ### Information
    - [Intel resources](https://www.intel.com/content/www/us/en/products/docs/processors/core/core-technical-resources.html)
    - [Silicon Lottery's binning statistics](https://siliconlottery.com/pages/statistics)
    - [VRM Load-Line visualization](https://elmorlabs.com/2019-09-05/vrm-load-line-visualized/)
  - ### Tools
    - [CPU-Z](https://www.cpuid.com/softwares/cpu-z.html)
  - ### Stress testing programs
    - [Linpack Extended](https://github.com/BoringBoredom/Linpack-Extended)
    - [LinX](https://hwtips-tistory-com.translate.goog/1611?category=377841&_x_tr_sl=auto&_x_tr_tl=en)
    - [Linpack Xtreme](https://www.ngohq.com/linpack-xtreme.html)
    - [OCCT](https://www.ocbase.com/)
    - [Prime95](https://www.mersenne.org/download/)
- ## RAM
  - ### Information
    - DDR4 basics: [text](https://www.systemverilog.io/) + [video](https://youtu.be/I-9XWtdW_Co?list=PLTd6ceoshpreE_xQfQ-akUMU1sEtthFdB)
    - [DDR4 JEDEC paper](http://www.softnology.biz/pdf/JESD79-4B.pdf)
    - [B-Die list](https://translate.google.com/translate?sl=auto&tl=en&u=https://www.hardwareluxx.de/community/threads/die-ultimative-hardwareluxx-samsung-8gb-b-die-liste-alle-hersteller-13-12-20.1161530/)
  - ### Tools
    - New versions of ASRock Timing Configurator, ASUS MemTweakIt and MSI Dragon Ball can usually be found [here](https://community.hwbot.org/forum/126-intel-cpu-overclocking/).
    - [Intel Memory Latency Checker](https://software.intel.com/content/www/us/en/develop/articles/intelr-memory-latency-checker.html)
    - [AIDA](https://www.aida64.com/downloads)
  - ### Stress testing programs
    - [Karhu RAM Test](https://www.karhusoftware.com/ramtest/) ([Enable _Caching_ on all operating systems and change the _RNG_ to _XORWOW_ if testing on Windows 7](https://www.karhusoftware.com/ramtest/README.txt))
    - [TestMem5](https://testmem.tz.ru/testmem5.htm) + [anta777's config](https://bit.ly/2MUvl6n) & [LMHz's config](https://drive.google.com/file/d/1fEPPG3sCqwtg7t1GQTwVrrixsyidwjL5/view) (links taken from [anta777's profile](https://forums.overclockers.ru/memberlist.php?mode=viewprofile&u=203320))
    - [OCCT](https://www.ocbase.com/)
    - [HCI MemTest](https://hcidesign.com/memtest/)
    - [GSAT](https://github.com/stressapptest/stressapptest)
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
  - ### Profiling / Monitoring / Benchmarking
    - [CrystalDiskMark](https://crystalmark.info/en/)
    - [ATTO Disk Benchmark](https://www.techpowerup.com/download/atto-disk-benchmark/)
  - ### Tools
    - [WinDirStat](https://sourceforge.net/projects/windirstat/) (disk usage analyzer)
    - [Total Commander](https://www.ghisler.com/) (file manager)
    - [Ventoy](https://github.com/ventoy/Ventoy) (multi-boot USB drive)
    - [Rufus](https://github.com/pbatard/rufus) (ISO mounting)
- ## BIOS
  - ### Information
    - [Win-Raid modding section](https://www.win-raid.com/f16-BIOS-Modding-Guides-and-Problems.html)
    - [BIOS Mods](https://www.bios-mods.com/forum/)
  - ### Tools
    - [UEFI Editor](https://boringboredom.github.io/UEFI-Editor/)
    - [Cancerogeno's compendium](https://sites.google.com/view/cancerogenoslab/bios-mods-and-tools)
- ## Windows
  - ### Information
    - [Windows Internals](https://docs.microsoft.com/en-us/sysinternals/resources/windows-internals)
    - [Group Policy Administrative Templates Catalog](https://admx.help/)
  - ### Profiling / Monitoring / Benchmarking
    - [HWiNFO](https://www.hwinfo.com/download/) & [LogViewer](https://www.hwinfo.com/forum/threads/logviewer-for-hwinfo-is-available.802/) (hardware analysis, monitoring and reporting)
    - [Benchmarking FPS](https://boringboredom.github.io/Frame-Time-Analysis/)
    - [Windows Performance Toolkit](https://docs.microsoft.com/en-us/windows-hardware/test/wpt/) ([Windows 7](https://www.microsoft.com/en-us/download/details.aspx?id=8279))
    - [Process Monitor](https://docs.microsoft.com/en-us/sysinternals/downloads/procmon)
    - [API Monitor](http://www.rohitab.com/apimonitor)
    - [Intel VTune Profiler](https://software.intel.com/content/www/us/en/develop/articles/oneapi-standalone-components.html#vtune)
    - [Intel Graphics Performance Analyzers](https://www.intel.com/content/www/us/en/developer/tools/graphics-performance-analyzers/overview.html)
    - [Processor Counter Monitor](https://github.com/opcm/pcm)
    - [MouseTester](https://github.com/microe1/MouseTester)
    - [Latencymon](https://www.resplendence.com/latencymon)
    - [Liblava](https://github.com/liblava/liblava-demo)
    - [PC Clock Timing](https://www.satsignal.eu/software/net.htm) (resolution of system time calls)
    - [Dependencies](https://github.com/lucasg/Dependencies) (dll load dependency checker)
  - ### Tools
    - [Sysinternals](https://docs.microsoft.com/en-us/sysinternals/downloads/) (huge compendium)
    - [Nirsoft's Tools](https://www.nirsoft.net/utils/index.html) (huge compendium)
    - [NTLite](https://www.ntlite.com/) (ISO creation)
    - [O&O ShutUp10++](https://www.oo-software.com/en/shutup10)
    - [Process Lasso](https://bitsum.com/) (priority and affinity saver)
    - [ProcessPluginFramework Service](https://forums.guru3d.com/threads/processpluginframework-in-the-form-of-windows-system-service.378450/)
    - [Power Plan Settings Explorer](https://forums.guru3d.com/threads/windows-power-plan-settings-explorer-utility.416058/)
    - [Timer Resolution Service](https://forums.guru3d.com/threads/windows-timer-resolution-tool-in-form-of-system-service.376458/)
    - [AdvancedRun](https://www.nirsoft.net/utils/advanced_run.html)
    - [Compatibility Manager](https://github.com/Skymirrh/CompatibilityManager) (compatibility settings editor)
    - [VC++ Redist. AIO](https://www.techpowerup.com/download/visual-c-redistributable-runtime-package-all-in-one/) (TPU)
    - [VC++ Redist. AIO](https://github.com/abbodi1406/vcredist) (abbodi1406)
    - [MSI Utility](https://forums.guru3d.com/threads/windows-line-based-vs-message-signaled-based-interrupts-msi-tool.378044/) (interrupt mode and priority control)
    - [Microsoft Interrupt Affinity Policy Tool](http://download.microsoft.com/download/9/2/0/9200a84d-6c21-4226-9922-57ef1dae939e/interrupt_affinity_policy_tool.msi)
    - [USB Device Tree Viewer](https://www.uwe-sieber.de/usbtreeview_e.html)
    - [DeviceTree](https://www.osronline.com/article.cfm%5Earticle=97.htm)
    - [Special K](https://wiki.special-k.info/) (game modifying framework | DO NOT USE WITH ANTI-CHEATS)
    - [EasyBCD](https://neosmart.net/EasyBCD/)
- ## Audio
  - ### Tools
    - [REAL](https://github.com/miniant-git/REAL) (W10 audio latency reduction)
- ## Alternatives to bloated programs
  - Epic Games: [Legendary](https://github.com/derrod/legendary)
  - Spotify: [Foobar2000](https://www.foobar2000.org/)
  - GHUB / LGS: [Logitech Onboard Memory Manager](https://support.logi.com/hc/en-us/articles/360059641133)
  - Antivirus software: [Virustotal](https://www.virustotal.com/gui/home/upload), [Hybrid Analysis](https://www.hybrid-analysis.com/) & [uBlock Origin](https://github.com/gorhill/uBlock)
  - Chrome: [Ungoogled Chromium](https://github.com/Eloston/ungoogled-chromium)
- ## Miscellaneous
  - [Geizhals database](https://geizhals.eu/) (useful for finding specific hardware due to the very extensive filtering functionality)
  - [NVIDIA article on lag reduction](https://www.nvidia.com/en-us/geforce/guides/system-latency-optimization-guide/)

# [My Twitter](https://twitter.com/Bra1nlet)

# Keywords for Google indexing (ignore this)

input lag latency optimization performance gaming overclock oc windows ping debloat milliseconds fps boost increase decrease guide mouse tweak tweaks bios uefi pc overclocking 7 8.1 8 10 11 w7 w8 w8.1 w10 w11 linux game gamer optimizations frametime frametimes 0.1 1 1080p 720p reaction time vrt average avg minimum maximum min max tweaking fortnite overwatch apex call of duty cs:go csgo dota league of legends valorant rocket league rainbow six pubg super people warzone halo infinite tarkov rust starcraft destiny ow fn cod lol kovaak aim trainer krunker battlefield bf roblox super smash bros delay delayed bloat bloated debloated steam battle origin epic games quake counter strike battle royale br intel nvidia pascal turing ampere reflex amd ati ryzen r9 r7 r5 r3 radeon rdna core i9 i7 i5 i3 memory ram gpu ssd nvme psu power supply emi emf emc ef power electricity coupling interference dpc isr rla reflex latency analyzer
