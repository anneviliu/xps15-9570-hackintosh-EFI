# xps15-9570-hackintosh-EFI
自用xps15 9570 4k版 EFI, 10.15.2 Catalina 可用

## 配置详情
xps15 9570

CPU: i7-8750H

内存: 32GB

硬盘: 1T 东芝(TOSHIBA) SSD

独显：Nvidia Gefore 1050Ti（无解，已屏蔽）

核显：Intel UHD Graphics 630

显示器：原装4K 显示器

Wi-Fi/蓝牙：DW1707


## 未驱动
Nvidia Gefore 1050Ti

Goodix fingerpint reader 指纹驱动

Killer 1535 网卡 已更换DW1707


## 系统环境
Windows 10 + Macos Catalina 10.15.2 双系统


## 安装教程
参考 `黑果小兵` 博客 https://blog.daliansky.net/
简略安装过程: https://annevi.cn/post/hackintosh_catalina/

## Catalina 特殊功能
随航(SideCar) 正常使用

## 存在的问题
1.睡眠偶尔需要长按电源键唤醒

2.绿联雷电三扩展坞网卡无法热插拔(扩展坞其他功能正常热插拔)

3.FaceTime和iMessage 需要填入三码 参考 https://github.com/bavariancake/XPS9570-macOS


## 安装适配过程中遇到的问题（已解决）
1. 开机启动慢，进入系统后网卡加载大致需要2-3分钟，并且wifi无响应
解决方案：将`EFI/Clover/Kexts/`中的`BrcmBluetoothInjector.kext``BrcmFirmwareData.kext``BrcmPatchRAM2.kext`替换为对应可用的网卡驱动

2. 键盘打字后，触控板有0.5s左右无效
解决方案: 由于新版本的Catalina 加入了触控板防误触功能，因此解决该问题只需将`VoodooI2`驱动替换为旧版本的即可，
包括`VoodooPS2Controller.kext` `VoodooI2CHID.kext` `VoodooI2C.kext` `VoodooHDA.kext` 替换后重启解决

3. 键盘`CapsLock`键灯异常，看似无法控制。
解决方案：系统偏好设置--> 键盘-->输入法-->去除使用大写锁定键切换'ABC'输入模式框 即可解决


