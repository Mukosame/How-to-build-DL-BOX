ubuntu 安装时黑屏处理 


问题描述：ubuntu使用光盘/USB安装时，出现"install ubuntu/ try ubuntu without installation"选择，但是Enter安装时，显示器显示没有信息，进行休眠 


原因分析：由于ubuntu对于显卡支持有问题，需要手动添加显卡驱动选项 


解决办法： 


一、安装时，选择"install ubuntu"后，按"e"进入编辑模式，进入命令行模式, 然后去掉"--"后，依照不同显卡进行不同显卡驱动选项的添加 


1.Intel 82852/82855 或8系列显示晶片：i915.modeset=1或i915.modeset=0 


2.Nvidia：nomodeset 


3.其它厂牌(如ATI，技嘉)：xforcevesa或radeon.modeset=0 xforcevesa 


[DELL T3400显卡为Nvidia FX580，选择nomodeset] 


F10安装 

 
二、当安装结束后，启动系统出现黑画面 

1.开机，进入grub画面(如果硬碟没有别的OS,请开机时按住shift不放才会有grub画面) 

2.按'''e''' 进入编辑开机指令的模式, 同样找到'''quite splash''' 并在后面加上对应的字。 

3.按 ''F10''启动系统. 

4.进去系统之后编辑'''/etc/default/grub''' 这个档案(要管理者权限sudo)。 

Ubuntu>打开终端机，输入sudo vi /etc/default/grub 
 

5.找到这一行: 

GRUB_CMDLINE_LINUX_DEFAULT="quiet splash" 

修改为： 

GRUB_CMDLINE_LINUX_DEFAULT="quiet splash nomodeset" 

6. 更新GRUB： sudo update-grub 


7.存档，并重新开机。 
