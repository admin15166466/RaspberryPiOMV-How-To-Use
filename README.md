# RaspberryPiOMV-How-To-Use
# 1 安装树莓派系统
添加的wifi信息的文件是wpa_supplicant.conf
wifi的名字和密码（ssid和psk字段）换成自己的
```
country=CN
ctrl_interface=DIR=/var/run/wpa_supplicant
update_config=1
 
network={
ssid="YOUR_WIFI_NAME"
psk="YOUR_PASSWORD"
key_mgmt=WPA-PSK
}
```
# 2 安装OpenMediaVault
## 1 换源
  参考 https://mirror.tuna.tsinghua.edu.cn/help/raspbian/
  更新软件列表 
```
sudo apt update
sudo apt upgrade
```
## 2 改host文件
```
sudo nano /etc/hosts
```
添加 
```
199.232.68.133 raw.githubusercontent.com
```
## 3 给树莓派设置上网代理（能访问google的电脑）
```
sudo nano /etc/environment
```
添加(ip地址和端口换成你的电脑的ip)
```
export http_proxy="http://10.0.0.6:8080"
export https_proxy="http://10.0.0.6:8080"
export no_proxy="localhost, 127.0.0.1"
```
## 4 用脚本安装OpenMediaVault
```
wget -O - https://github.com/OpenMediaVault-Plugin-Developers/installScript/raw/master/install | sudo bash
```

# 3 配置共享文件夹
在浏览器里输入树莓派的IP地址，默认用户名admin，默认密码openmediavault进入。
插入硬盘。
卸载硬盘，切到磁盘菜单，如果没有要保存的数据，点击擦除。



--------------------------------------------------------------------等待完善------------------------------------------------------------------------------------
