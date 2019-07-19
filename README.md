# linux_env

# gpu服务器搭建手册

### 系统配置（用root账户配）
1. ipv4、ipv6网络配置
2. 检查开启ssh
3. 安装zsh（重启生效）, oh my zsh
4. 安装tmux（补gcc, libevent-devel, ncurses-devel），配置
5. 安装frp，配置

### 显卡驱动
1. 下载对应内核：http://rpm.pbone.net/
2. rpm -ivh kernel-headers-3.10.0-xxx.el7.x86_64.rpm, 
   rpm -ivh kernel-devel-3.10.0-xxx.el7.x86_64.rpm
3. etc/modprobe.d/blacklist.conf 
4. 重新建立initramfs image文件
5. multi-user
6. 重启安装驱动
7. 安装cuda
8. 安装cudnn
