# 1.uboot下载
从u-boot官网下载最新u-boot文件
ftp://ftp.denx.de/pub/u-boot/ 
 
# 2.安装交叉编译工具
https://developer.arm.com/open-source/gnu-toolchain/gnu-rm/downloads

从ARM官网地址中下载对应的gcc-arm-none版本即可。

下载完成后拷贝到linux系统中进行解压安装。

# 3.添加工具链的环境变量

将虚拟机 home本地目录.bashrc文件的最后两行加上

export PATH=$PATH:~/gcc-arm-none-eabi-6-2017-q2-update/bin

export CROSS_COMPILE=arm-none-eabi-

添加命令完成后执行命令source .bashrc回车，执行arm-none-eabi-gcc -v回车，验证是否已成功添加。

# 4.生成config文件
将下载的u-boot解压到linux下面。解压完成后执行make xxxx_config生成对应板卡的.config文件。

# 5.编译uboot
执行make即可生成u-boot.bin文件。

# 6.最后
至此，整个u-boot的环境搭建和编译过程已全部OK。即可通过修改u-boot的内部文件和代码的方式进行相应的调试。
