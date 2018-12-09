# 注意事项
### 1.本EFI适用于macOS High Sierra 10.13.6
### 2.-v时开机卡 *`MACH Reboot`* 错误
添加下列三个参数即可
![](/Images/MACH.png)

### 3.驱动声卡
声卡的 *`layout-id`* 填写1，因为我给AppleALC.kext打了补丁，注入的就是id就是1
![](/Images/声卡注入.png)

### 4.驱动N卡(A卡暂不介绍)
N卡一般用Webdrive驱动就可以了，7、9系列显卡大部分直接免驱，若用webdrive驱动的，别忘了在clover里勾选 *`NvidiaWeb`*
![](/Images/webdrive.png)

### 5.Clover分辨率
以下选项请勿勾选，1080P下勾不勾选无所谓，若分辨率超过1080P，请勿勾选，否则clover界面显示很扁，很难看。
![](/Images/resolution.png)

### 6.驱动USB
①.在 *`EFI-clover-kext-other`* 里放入 *`USBInjectAll.kext`* 和 *`GenericUSBXHCI.kext`* 驱动

②.在clover里添加端口映射补丁
![](/Images/USB端口映射补丁.png)

③.在打USB端口限制补丁即可驱动所有USB端口
![](/Images/USB端口限制补丁.png)

### 7.更改Windows的GUI
①.隐藏 *`Preboot`* 的盘符即可
![](/Images/Preboot.png)

②.记录引导Windows启动的EFI分区的 *`UUID`*
![](/Images/UUID.png)

③.在GUI选项中新增一个启动项，命名为 *`Windows10`* ，需要添加Windows启动的EFI分区的 *`UUID`* 和指定 *`Windows启动文件路径`* ，并且设置 *`不隐藏`*，类型为 *`Windows`*
![](/Images/Windows引导.png)
④.保存文件，重启即可看到效果

### 8.修改显示器识别
运行Tools文件夹里的MonitorFace软件之后，插拔显示器就OK了
![](/Images/MonitorFace.png)
> 这里非常感谢[lihaoyun6](https://github.com/lihaoyun6)大佬的开源项目 [macOS-Displays-icon](https://github.com/lihaoyun6/macOS-Displays-icon)

# 效果图
### 1.系统信息
![](/Images/系统信息.png)

### 2.显示器
![](/Images/显示器.png)
![](/Images/显示器2.png)

### 2.硬件
![](/Images/硬件.png)

### 3.USB总线(总线可能不正确，USB2.0设备无论插在2.0上还是3.0上和USB3.0设备插在2.0上都显示在3.0总线上)
![](/Images/USB总线.png)

### 4.以太网卡
![](/Images/以太网卡.png)

### 5.WIFI
![](/Images/WIFI.png)

### 6.显卡
![](/Images/显卡.png)

### 7.音频
![](/Images/音频.png)

### 8.音频输出设备
![](/Images/音频输出设备.png)

### 9.音频输入设备
![](/Images/音频输入设备.png)

### 10.蓝牙连接
![](/Images/蓝牙连接.png)

### 11.蓝牙信息
![](/Images/蓝牙信息.png)

### 12.SATA设备
![](/Images/SATA设备.png)