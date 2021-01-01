# MSI-B450m-MORTAR-Hackintosh-BigSur

<br>

### 配置清单

| 类型 | 型号                  |
| ---- | --------------------- |
| 主板 | 微星 B450m 迫击炮 max |
| CPU  | AMD R5 3600           |
| 显卡 | 蓝宝石 RX 590         |

<br>

## BigSur 11.1 （2021-1-1新增）

### 前言

这是我之前Star的[heyxiaobai提供的配置文件](https://github.com/heyxiaobai/MSI-B450m-MORTAR-Hackintosh)，在[Catalina](https://github.com/Whosydd/MSI-B450m-Hackintosh-Catalina)中用着很不错，这次发现更新了11.1版本，所以也就直接拿过来了。。。和之前一样，删除了AppleALC，添加了AX200的WiFi和蓝牙驱动，唯一的区别就是这个启动项没有图形界面。

<br>

## BigSur 11.1（2020-12-27新增）

### 前言

该版本EFI基于[Tyrone2333](https://github.com/Tyrone2333/r5-2600-b450m-bazooka-5700-hackintosh)，启动项有图形界面，使用的是iMacPro1,1机型，我目前正在使用中，可以正常使用接力、iMessage，暂未发现其他问题。

<br>

### 添加&删除的功能

**添加**针对intel ax200网卡的驱动

**删除**AppleALC.kext(由于我平时不用板载声卡，所以直接删除了声音驱动)

<br>

### nvme改内置（解决桌面出现橙色硬盘）

打开**hackintool**，切换到**PCI**标签页，查找“**Mass storage controller**”项，右键点击“**Copy Device Path**”，会获得类似于“*PciRoot(0x0)/Pci(0x1,0x1)/Pci(0x0,0x0)*”的字符串，然后打开**EFI**中的**config.plist**，搜索“**DeviceProperties**”，然后将"**add**"中的子项替换即可。

详细步骤可参考https://www.reddit.com/r/hackintosh/comments/f0cc4t/internal_drives_shown_as_external_opencore_amd/

<br>

<br>

## BigSur 11.0.1

### 前言

该版本EFI基于[dellusa](https://github.com/dellusa/Opencore-MSI-B450M-PRO-R5-3600)，使用的是MacPro7,1机型，实际使用中确实会存在一些问题，比如无法使用接力、iMessage等

<br>

### 添加&删除的功能

**添加**针对intel ax200网卡的驱动，以及显卡优化radeonboost.kext

**删除**AppleALC.kext(由于我平时不用板载声卡，所以直接删除了声音驱动)

<br>

### 目前存在的问题

1. 【已解决】由于innie.kext还没有适配bigsur，所以桌面会出现nvme磁盘标识

   **说明**：已通过修改config的方式解决该问题，详情可参考：https://www.reddit.com/r/hackintosh/comments/f0cc4t/internal_drives_shown_as_external_opencore_amd/

2. 【已解决】MacPro7,1机型每次开机都出现内存相关提示信息的问题

   **重要说明**：针对该问题我修改了config.plist中的内存信息，使用该EFI文件时，**一定要**先根据自己的内存信息进行修改，详情可参考：https://dortania.github.io/OpenCore-Post-Install/universal/memory.html

![](https://i.loli.net/2020/12/03/D5c619Rjrpxdhby.png)