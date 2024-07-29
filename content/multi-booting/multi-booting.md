# How to multi-boot Windows 7-10 in UEFI mode on a single drive

## Partitioning (you only have to do this once)

- I used Windows 1803 due to a [change in partitioning behavior in Windows 2004+](https://pureinfotech.com/windows-10-2004-fixes-recovery-partition-problem/). The side effect of this change is that a new unnecessary recovery partition will be created whenever you install an OS. 1803 will only be needed for partitioning. You don't have to install it. Installing any version above 1909 won't mess up your partition structure, as long as the drive was partitioned with an older version.
- Prepare a USB stick with [Ventoy](https://github.com/ventoy/Ventoy) (set to GPT) and transfer all your ISOs.
- In the BIOS, enable CSM and set Storage OpROM and PCI device ROM to UEFI. You have to partition the drive with CSM enabled, otherwise you won't be able to install Windows 7. CSM is only required for partitioning and installing Windows 7 (including GPU drivers). Installing W8-10 and regularly booting W7-10 doesn't require CSM anymore.
- Boot into the Windows 1803 installer and delete all existing partitions until the entire drive is just a chunk of unassigned space.
- Create a file partition, where you keep your files, games etc. Windows will also reserve some space to create a [Recovery, a System, and a Microsoft Reserved Partition](partitions.jpg). Then, create as many OS partitions as you want. The final order will look something like this: Recovery, System, MSR, Files, OS, OS, OS etc.
- You can now exit the installer and proceed with an ISO you want to install.

## Installing Windows

- Whenever you install a new OS, format one of the OS partitions and leave everything else untouched.
- You can unassign drive letters with Windows's Disk Management tool to "hide" other OS partitions from the current OS. Personally, I like to only have C for the current OS and D for the file partition.
- ### Installing Windows 7
  - Installing Windows 7 and GPU drivers requires having CSM enabled (set Storage OpROM and PCI device ROM to UEFI).
  - After installing GPU drivers, you can disable CSM.
- ### Installing Windows 8-10
  - Windows 8-10 can be installed without CSM.
