# Ubuntu平台开发环境搭建

## 零、下载Ubuntu系统iso镜像文件
1. 进入Ubuntu官网，[点击进入](url: https://www.ubuntu.com/download)
2. 选择个人喜好的Ubuntu版本(笔者使用的是Ubuntu 16.04), 下载到本地，保存在合适的位置，并记住该位置

## 一、安装Ubuntu
###     1. 裸机安装Ubuntu( 初学者以及Windows平台开发者不推荐)
>① 找一个容量至少为4G的U盘， 格式化 
> 
>②  A 找一台使用Windows系统的电脑， 下载并安装 **UltraISO** 下载安装好之后打开，插上准备好的U盘 找到上一步下载的Ubuntu镜像文件，双击打开， 然后选择 **工具** -> **制作硬盘镜像**， 选择刚插上的U盘，点击开始制作，等待制作完成即可

>   B 如果有MacBook 之类的macOS系统电脑，可以使用终端工具dd来制作，具体使用方法如下: 
    1. 打开终端
    2. 敲命令： df -h, 查看SD卡所在的分区， 如我的SD卡分区为/dev/disk5,具体根据个人情况而定，只需要自己能够找到对应分区即可
    3. 使用umount命令卸载分区, macOS下为”diskutil umount /dev/disk5s1”
    4. 使用cd命令进入到你下载的Ubuntu镜像所在目录，如我的下载目录在/home/oyoung/downloads,然后执行命令sudo dd bs=4m if=<你的镜像文件> of=<你的SD对应的块设备>，比如我上面提到的/dev/disk5,
    5. 然后等待一段时间，具体视你的SD卡写入速度而定，毕竟镜像文件超过1G
> 
>③ 将U盘拔下，插到需要安装Ubuntu的电脑上，然后开机，选择从U盘启动

###     2. 虚拟机安装Ubuntu
    1. 下载安装虚拟机软件(Windows平台有VMware VirtualBox， macOS平台有VirtualBox ParallesDesktop, 俗称PD，最佳选择，但是需要付费购买， 如果想使用免费的虚拟机软件， 推荐使用VirtualBox), 并安装
    2. 打开虚拟机软件，新建一个虚拟机， 如果有类型选择，请选择Linux Ubuntu（PD会自动检测), 并配置好虚拟机参数，建议内存选至少2G, 硬盘至少40G, CPU至少为1
    3. 打开虚拟机， 选择下载好的Ubuntu镜像，进行Ubuntu系统的安装，安装过程很小白，跟着一步一步点下一步就可以了

###     3. 大容量移动存储设备(U盘或者移动硬盘安装)
    准备工作和裸机安装差不多，只不过 在安装的时候不要选电脑的本地硬盘，而是选择一块移动硬盘或者大容量U盘(不是安装启动U盘)
    安装好之后，可能会修改系统引导，记得修改一下引导的默认启动项为本地的Windows，然后如果需要启动Ubuntu的话，需要插上外置存储设备才能启动，
## 二、熟悉Ubuntu基本操作
###     1. 传统视窗GUI操作，与window以及macOS的GUI界面操作类似，包括鼠标单击，双击，右击，拖拽等
###     2. 常用工具软件
    1. vim 命令行文本编辑器，使用相当方便
    2. terminal 命令行工具，所有的命令行操作都在此工具下进行
    3. wget 网络下载工具，可以下载http, ftp等协议下的文件， 可以使用curl工具代替
###     3. 常用快捷键及其作用
    1. 桌面环境下最常用的快捷键有以下几种: 
        Ctrl + Alt + T -> 启动terminal
        Alt + Tab -> 切换窗口
    2. terminal环境下的常用快捷键
        Ctrl + L -> 清屏， 相当于命令clear
        Ctrl + Z -> 暂停当前程序到后台
        Ctrl + C -> 停止当前正在运行的程序
        Ctrl + A -> 光标调到命令行的开头， 相当于Home按键
        Shift + Insert -> 粘贴
    3. vim 编辑文件环境下的常用快捷按键
        所有模式下:
            Esc -> 进入一般模式
        一般模式下:
            i -> 在当前光标位置进入插入模式(可以输入文本内容)
            a -> 在当前光标位置的下一个位置进入插入模式
            A -> 在当前行的末尾进入插入模式
            o -> 在当前行的下一行增加一行并进入插入模式
            O -> 在当前行的上一行增加一行并进入插入模式
            s -> 删除当前位置的一个字符并进入插入模式
            dd -> 删除当前行， dXd -> 删除包括当前行在内的多行，X为具体数字，表示行数， 如d100d表示从当前行开始删除100行
            dw -> 删除当前位置开始后的一个单词(包括空格), dXw表示删除多个单词， X表示单词个数
            d$ -> 删除当前位置到行尾的内容
            dG -> 删除当前位置到文件末尾的内容
            0 -> 光标调到行首
            yy -> 从当前行复制一行， yXy 复制多行， X代表行数
            p -> 粘贴使用dd, yy 等命令复制的内容
            ddp -> 交换当前行与下一行
            ddP -> 交换当前行与上一行
            yyp -> 复制当前行到下一行
            : -> 进入命令模式
            / -> 进入查找模式
        命令模式：
            set nu -> 显示行号
            set nonu -> 不显示行号
            set autoindent -> 打开自动缩进
            set noautoindent -> 关闭自动缩进


###     4. 终端工具介绍( 启动快捷键 Ctrl + Alt + T) 常用命令
    

## 三、学习Ubuntu命令行思维
###     1. 常用终端命令介绍
    文件操作:
        ls -> 列出当前目录下的非隐藏文件
        ls -la -> 列出当前目录下所有文件的详细信息
        touch file -> 新建或更新一个文件
        chmod -> 修改文件或目录权限， 如 chmod +x file 给文件可执行权限， chmod -R 777 dir 给目录完全控制权限
        chown user:group file ->  修改文件所有者和所有组
        chgrp group file -> 修改文件所有组
        rm file -> 删除文件，
        rm -r dir -> 删除目录， 
        rm -rf file_or_dir 强制递归删除目录或文件
        mkdir newDir -> 创建一个新目录， 目录已存在会报错
        mkdir -p newDir -> 递归创建单层或嵌套目录， 目录已存在则直接跳过
        ln -s 原文件或目录 新名字 -> 给原文件或目录建立一个软链接
        mv file dir -> 移动文件或目录到新位置，如果新位置所代表的目录不存在，则会重命名为该新位置的名字
        cp file dir -> 复制文件到新位置，如果新位置所代表的目录不存在，则会重命名为该新位置的名字
        cp -r dir newDir -> 复制目录到新位置，如果新位置所代表的目录不存在，则会重命名为该新位置的名字
        scp file remoteDir -> 通过ssh 与远程主机之间相互传输文件
        alias -> 给命令起别名， 如 alias ll='ls -la', 就表示敲ll 时执行的是ls -la
    进程管理:
        ps -> 列出已有进程
        top -> 以表格方式显示进程信息
###     2. 终端编辑器Vim介绍
    vim 是所有Linux终端都能使用的一款文本编辑器，本身很轻量，也支持插件扩展，支持很多语言的语法高亮，是Linux环境下的开发者的一款必不可少的神兵利器
## 四、学会使用apt-get 工具安装deb包
    1. 直接安装
        sudo apt-get install 包的名字
    2. 下载包
        sudo apt-get download 报名字
## 五、使用apt-get安装工具链
    sudo apt-get install build-essential vim git cmake

进过以上的步骤，你的Ubuntu平台C++开发环境已经搭建好了， 当然如果不想命令行写代码，也可以使用IDE, 常用的IDE有：
    Qt Clion Eclipse KDevelop CodeBlock 
具体使用那个取决于用户自己的喜好
