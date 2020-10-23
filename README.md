# Ubuntu18.04-install


# 安裝顯卡驅動
# Step 1 禁用 nouveau

終端機輸入:
lsmod | grep nouveau
//如果有輸出則表示nouveau正在加載

sudo gedit /etc/modprobe.d/blacklist.conf

//在打開文本的最後面添加：
blacklist nouveau
options nouveau modeset=0
//Save

sudo update-initramfs -u
reboot

再一次查看是否有禁用nouveau成功
lsmod | grep nouveau

# Step 2 安裝NVIDIA顯示卡驅動
終端機輸入
ubuntu-drivers devices
//可查看目前可安裝的驅動版本
//nvidia-driver-410 - third-party free
//nvidia-driver-415 - third-party free
//nvidia-driver-450 - third-party free....
//選擇要安裝的版本，輸入指令 sudo apt-get install
//install 後面輸入出現的驅動名字


sudo apt-get install nvidia-driver-450


以上完成顯示卡驅動安裝!!!!!

# 安裝CUDA 10.0






