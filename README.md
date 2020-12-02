# MSI-B450m-MORTAR-Hackintosh-BigSur



## 前言

1. 该EFI文件基于[dellusa](https://github.com/dellusa/Opencore-MSI-B450M-PRO-R5-3600)提供的EFI文件，并针对个人需求进行一定修改

2. 建议使用前先浏览[dellusa](https://github.com/dellusa/Opencore-MSI-B450M-PRO-R5-3600)提供的说明，以免出现问题



<br>

## 配置清单

| 类型 | 型号                  |
| ---- | --------------------- |
| 主板 | 微星 B450m 迫击炮 max |
| CPU  | AMD R5 3600           |
| 显卡 | 蓝宝石 RX 590         |



<br>

## 添加&删除的功能

**添加**针对intel ax200网卡的驱动，以及显卡优化radeonboost.kext

**删除**AppleALC.kext(由于我平时不用板载声卡，所以直接删除了声音驱动)



<br>

## 目前存在的问题

1. 由于innie.kext还没有适配bigsur，所以桌面会出现nvme磁盘标识

2. 【已解决】MacPro7,1机型每次开机都出现内存相关提示信息的问题

   **重要说明**：针对该问题我修改了config.plist中的内存信息，使用该EFI文件时，**一定要**先根据自己的内存容量进行修改（可参考：https://dortania.github.io/OpenCore-Post-Install/universal/memory.html）

![](https://i.loli.net/2020/12/03/D5c619Rjrpxdhby.png)