# Hachintosh
i5 10400+Asrock B460M ITX/ac
## 系统
MacOS Big sur+Win 10（单硬盘双系统）
![ ](images/1.png)
## 配置

|  配件  |型号              |
|:------:|:----------------:|
|  主板  |华擎B460M-ITX/ac  |
|  CPU   |i5 10400          |
|  内存  |镁光英睿达8G DDR4 2666  |
|  硬盘  |海康卫视C2000 pro |
|  显卡  |iGUP              |
|  电源  |全汉MS450         |
|  机箱  |ghost s1复刻版    |            
|无线网卡|DW1820A           |
|  风扇  |ID 40X            |
##### *注：本文只提供EFI的分享以及在安装过程中碰到的问题，系统还有很多不完善的地方，希望得到大家的帮助和指点*

## 引导概况（2021年4月1日更新）
 - Opencore版本：~0.6.5 release~ 更新为0.6.7 release
 - Mac 系统升级到11.2.2
 - 使用本EFI之前通过 GenSMBIOS 生成新的三码，在/EFI/OC/config.plist 文件中进行修改
```xml
<dict>
    <key>SystemSerialNumber</key>
    <string>W00000000001</string>
</dict>
```
```xml
<dict>
    <key>MLB</key>
    <string>M0000000000000001</string>
</dict>
```
```xml
<dict>
    <key>SystemUUID</key>
    <string>00000000-0000-0000-0000-000000000000</string>
</dict>
```
 - 安装MacOS之前，BIOS需要关闭WAN功能。当系统安装成功后。在`config.plist`的`NVRAM`-- `Add`--`7C436110-AB2A-4BBB-A880-FE41995C9F82`--`boot-args`中加入`brcmfx-drive=0`，然后重启进入`BIOS`开启`WAN`以实现蓝牙和wifi功能。（如果直接使用本EFI，尽量先去掉引导参数`brcmfx-drive=0`，等系统安装成功后再添加）
 ## 双系统启动
 将win10的EFI文件夹中的*Microsoft*文件夹直接拷贝到本EFI中，并将EFI文件夹放入ESP分区即可
 ![ ](images/2.png)

 
 ## 功能
 
 ### 正常
 - 随航、接力、夜览
 - wifi与蓝牙（原装intel网卡已更换为博通DW1820A）
 - 有线网卡
 - 休眠(休眠后可以正常唤醒）
 - USB定制
 - 声卡定制
 ### 不正常
 - ~`Hackintool`中显示为`coffee lake`平台（暂时并不影响使用）~
 - 显示器亮度调节
 - 启动皮肤无法显示
 
 ## 参考与感谢：
+ Dortania 制作的安装手册 https://dortania.github.io/OpenCore-Install-Guide/
+ 黑果小兵本人和他的博客https://blog.daliansky.net/
+ 司波图安装教程
  -https://www.bilibili.com/video/BV1uf4y1X7MT
+ 阿杜安装教程 https://www.bilibili.com/video/BV1854y1x7fj
+ 黑苹果屋 https://www.bilibili.com/video/BV1f541147Ag （评论区的大神帮忙解决了启动问题）
+ https://github.com/ansonliao/Asrock-B460m-ITX-AC-OC-EFI
+ https://github.com/chenfeicqq/ASRock-B460M-ITX-ac-Hackintosh

