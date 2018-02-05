# macOS平台搭建开发环境

# 使用Xcode
## 下载安装Xcode
1. 打开AppStore, 搜索Xcode, 下载并安装
2. 打开LauchPad(启动台)，找到Xcode点击打开
(或者在桌面按下Command + Space, 输入Xcode并回车)

## 使用Xcode创建C++工程
3. 点击 **Create a new Xcode Project -> macOS -> Command Line Tools -> Next**
4. 输入 **Product Name**，并选择 **Language** 为 **C++** , 继续点击 **Next**
5. 选择项目要保存的目录， 然后点击 **Create** 即可成功创建 **C++** 项目
6. 点击Xcode为我们自动生成的 **main.cpp**, 这就是最基本的C++经典的 **Hello World** 程序
7. 按下 **Command + R** 快捷键 可以看到程序的运行结果，输出了一行Hello World并结束了

# 使用Clion

## 购买并下载CLion(可以先下载试用，再根据个人喜好选择要不要购买)
## 安装cmake, 可以通过以下常用的集中方式来安装(需要打开终端工具)
### 通过brew 安装cmake(前提是已经安装过homebrew)
```bash
YourHostName: YourWorkDir$ brew install cmake
```
### 通过官网直接下载cmake可执行文件 ([点击直接下载可执行文件包](url: https://cmake.org/files/v3.10/cmake-3.10.2-Darwin-x86_64.dmg))

1. 到官网下载cmake源码包, [下载链接](url: https://cmake.org/download/)
2. 找到 Platform -> Mac OS X 10.7 or later 后面的下载地址，将cmake源码包下载到本地
3. 使用tar 工具解压 cmake 源码包

### 通过源码安装cmake ([点击直接下载源码包](url: https://cmake.org/files/v3.10/cmake-3.10.2.tar.gz))
1. 到官网下载cmake源码包, [下载链接](url: https://cmake.org/download/)
2. 找到 Platform -> Unix/Linux Source (has \n line feeds) 后面的下载地址，将cmake源码包下载到本地
3. 使用tar 工具解压 cmake 源码包
```bash
YourHostName: YourWorkDir$ tar xzvf cmake-3.10.2.tar.gz
YourHostName: YourWorkDir$ cd cmake-3.10.2
YourHostName: YourWorkDir$ ./bootstrap --prefix=/usr/local
YourHostName: YourWorkDir$ make
YourHostName: YourWorkDir$ make install
```
其中的版本号可能不一样， 以及安装的目标路径也不同， 都是根据实际情况由调用者自己修改

