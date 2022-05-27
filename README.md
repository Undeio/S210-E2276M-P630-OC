# S210-2276M-P630-OC

## 更新说明

### New's - 2022.5.27

1. OC 版本：0.80 RELEASE；
2. 当前配置在 Catalina 10.15.6(19G2021) 上测试通过，如无意外，将长期停留在此版本，其他版本请自测，禁用系统更新请参考[禁用 macOS 更新的方法](https://undeio.com/posts/1266483541/)；
3. 已关闭啰嗦模式，初次安装，请执行以下操作：

   - 替换配置文件为 DEBUG 版（内含），包括但不限于 Kexts、Drivers；
   - 启用`Misc 设置`中`Debug`选项下的`AppleDebug`；
   - 请将`Misc 设置`中`Debug`选项下的`Target`设置为 67；
   - 请在`NVRAM 设置`中`Add`选项下`7C436110-AB2A-4BBB-A880-FE41995C9F82`条目的`boot-args`中添加`-v`参数；

4. OC 主题 AppleSilicon，来自 [heipg.cn](https://heipg.cn/)；

## 配置说明

### 机器配置

|    硬件    |      型号      |                                                                 备注                                                                 |
| :--------: | :------------: | :----------------------------------------------------------------------------------------------------------------------------------: |
|    机型    |      S210      |                                                               双影王族                                                               |
|    BIOS    |    AMI 5.17    |                                                              2021/03/12                                                              |
|   芯片组   |     CM246      | [移动式英特尔 ® CM246 芯片组](https://www.intel.cn/content/www/cn/zh/products/sku/135100/mobile-intel-cm246-chipset/compatible.html) |
|    CPU     |    E-2276M     |                                                      ES 版 （CPUZ 显示为 0000）                                                      |
|    内存    |    16G x 2     |                                                          光威悍将 DDR4 3200                                                          |
|   磁盘 1   |      512G      |                                                          西数 SN570 (macOS)                                                          |
|   磁盘 2   |      512G      |                                                            Team (Windows)                                                            |
|    显卡    |      P630      |                                                          与 UHD630 规格相同                                                          |
|    声卡    | Realtek ALC282 |                                                         VEN_10EC & DEV_0282                                                          |
| 有线网卡 1 |     i219v      |                                                                                                                                      |
| 有线网卡 2 |      i211      |                                                               靠近电源                                                               |
|  无线网卡  |  BCM 94360Z3   |                                                         VEN_14E4 & DEV_43A0                                                          |
|    蓝牙    |    同上 👆     |                                                             走 USB 通道                                                              |
|   显示器   |    Q2490PXQ    |                                                              DP & HDMI                                                               |

### BIOS 设置

请参考[Intel BIOS settings](https://dortania.github.io/OpenCore-Install-Guide/config.plist/coffee-lake.html#intel-bios-settings)

懒得看或打不开：

![懒得看或打不开](https://tva1.sinaimg.cn/large/e6c9d24ely1h2n4yncs1nj21aq0u0n1s.jpg)

### 工作状态

1. 显示输出正常：DP ｜ HDMI，双显示器，单显示器热拔插；
2. 音频输出正常（麦克风未测试）；
3. 双有线网卡正常；
4. 无线、蓝牙正常；
5. 随航、接力、隔空投送正常；
6. USB（3.0 | 2.0 | type-c）正常；
7. 开关机、睡眠唤醒正常；

### 已知问题

1. DP + HDMI 双显示器状态下，拔掉 HDMI 无法自动切换至 DP 单显示；
2. 接上 👆，再插上 HDMI 时 HDMI 会保持黑屏，需要拔插一次 DP 才能显示正常；

### 其他说明

由于使用的是 ES 版 CPU，关于本机中无法显示 CPU 信息，所以自定义了 CPU 的类型：

![ES 版CPU](https://tva1.sinaimg.cn/large/e6c9d24ely1h2n4srl05tj20xn0bwgn8.jpg)

如需自动获取 CPU 型号，请将值设为 0；

如需个性化 CPU 型号，请参考[PlatformInfo](https://dortania.github.io/OpenCore-Install-Guide/config.plist/coffee-lake.html#platforminfo)`Generic`中的说明：

![Generic](https://tva1.sinaimg.cn/large/e6c9d24ely1h2n5bl11x5j21es06idgm.jpg)

文中的[AppleSmBios.h](https://github.com/acidanthera/OpenCorePkg/blob/master/Include/Apple/IndustryStandard/AppleSmBios.h)
