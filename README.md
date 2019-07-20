# linux_env

# gpu服务器搭建手册

### 系统配置（用root账户配）
1. ipv4、ipv6网络配置
3. 安装zsh（重启生效）、oh my zsh
4. 安装tmux，配置
5（选）. 安装frp，配置

### 显卡驱动
1. 下载对应内核：http://rpm.pbone.net/
2. `rpm -ivh kernel-headers-3.10.0-xxx.el7.x86_64.rpm`, 
   `rpm -ivh kernel-devel-3.10.0-xxx.el7.x86_64.rpm`
3. 设置etc/modprobe.d/blacklist.conf 
4. 重新建立initramfs image文件
5. multi-user
6. 安装gpu驱动
7. 安装cuda，PATH和LD_LIBRARY_PATH写在/etc/profile.d/cuda.sh里
8. 安装cudnn

### torch环境
1. anaconda3，PATH写在/etc/profile.d/里
2. 安装shadowsocks, proxychains，用于下载pytorch
3. 安装torch：`conda install pytorch torchvision cuda100 -c https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/pytorch/linux-64/`
4. `pip install opencv-python`
5. 配置jupyter notebook，开放端口：`firewall-cmd --zone=public --add-port=8888/tcp --permanent`
6. 升级gcc4.9以上，为了下面装apex
```
yum install centos-release-scl
yum install devtoolset-3-toolchain
scl enable devtoolset-3 bash
gcc --version
```
7. 把`source /opt/rh/devtoolset-3/enable`写到启动项里
8. 安装Nvidia/apex

### 其他安装项
1. shadowsocks-gui: https://github.com/Shadowsocks-Wiki/shadowsocks/blob/master/6-linux-setup-guide-cn.md#Shadowosocks-QT5
2. chrome及switchproxy插件
