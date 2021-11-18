---
slug: 散装的学习笔记
title: 散装的学习笔记
description: 散装的关于所有无关代码层面的学习笔记以及收录
keywords: vscode,wsl,window,ubuntu,nvm,软件
category: 散装的学习笔记
tags: [vscode,wsl,window,ubuntu,nvm,软件]
author: liming
date: 25-September-2020
cover: https://i0.hippopx.com/photos/457/88/1021/microphone-boy-studio-screaming-preview.jpg
---

# 备忘录

fe-interview-code

工作时间，平时福利待遇，节假日，电脑，5险一金，年终奖，出差，加班（），技术栈,

**uniapp**

tab选项卡，滑动切换

页面跳转动画

**react**

css-in-js

postcss

**css**

history.pushState()和history.replaceState()

**vue**

Vue 中使用`lib-flexible`和`postcss-pxtorem`将`px`单位转化为`rem`单位

left，d3，openlayers，gis

**data100**

月报，周报，日报

打卡

**关于测试、Bug处理、代码检查要求**

git流程，功能迭代流程

**关于TAPD的使用规则**


# vscode

按F1或ctrl+shift+P键入`Live Sass: Watch Sass`以开始实时编译，或者按键入`Live Sass: Stop Watching Sass`以停止实时编译。

# window

## 命令

### 环境变量

window+r —> sysdm.cpl —> 高级 —>环境变量

### 任务进程

查看任务进程：tasklist
删除任务pid ：taskkill /f /pid
taskkill /f /im 程序名 杀掉对应程序名称的所有进程
netstat -ano | find "3306"查看3306端口的任务进程

## 软件

### Windows 字体 

https://sspai.com/post/35133

### 桌面

https://www.zhihu.com/question/45120814

软媒桌面

TranslucentTB

### 录屏工具

LICEcap

### 截屏

snipaste

### 终端

#### babun

```js
vscode配置babun
"terminal.integrated.shell.windows": "C:\\Users\\YOURUSERNAME\\.babun\\cygwin\\bin\\zsh.exe",
```

- WARNING: UNPROTECTED PRIVATE KEY FILE!   

  tips:chmod 700 ~/.ssh/id_rsa  更改权限

#### wsl

##### terminal

https://blog.csdn.net/weixin_42595232/article/details/106012575?spm=1001.2014.3001.5506

- 创建命令行数据文件夹

  ```
  mkdir "%USERPROFILE%\AppData\Local\terminal"
  对应我自己电脑的文件目录就是：
  C:\Users\niefajun\AppData\Local\terminal
  ```

- 下载（https://github.com/microsoft/terminal/tree/master/res）terminal.ico， 存储到刚才创建的目录当中 

- 编写注册表文件

  ```
  Windows Registry Editor Version 5.00
  
  [HKEY_CLASSES_ROOT\Directory\Background\shell\wt]
  @="Windows terminal here"
  "Icon"="C:\\Users\\niefajun\\AppData\\Local\\terminal\\terminal.ico"
  
  [HKEY_CLASSES_ROOT\Directory\Background\shell\wt\command]
  @="C:\\Users\\niefajun\\AppData\\Local\\Microsoft\\WindowsApps\\wt.exe"
  
  ```

  然后另存文件为：`wt.reg`，要保证格式正确。
  程序说明：

  1. 第一部分，说明是windows注册表
  2. 第二部分，是说明鼠标右键显示菜单缩略图的存储位置
  3. 第三部分，说明`Windows Terminate`的实际命令的存储位置

- 运行生效注册表文件

- 修改配置文件

  ```
  添加如下内容：
  "startingDirectory": "."
  ```

  ![01-10](https://img-blog.csdnimg.cn/20200509095325779.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MjU5NTIzMg==,size_16,color_FFFFFF,t_70) 

##### ubuntu

https://blog.csdn.net/lmz_lmz/article/details/88341807

- 管理员权限运行powershell并运行下面的命令：

  ```
  Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux
  ```

- 重启电脑

- 打开应用商城搜索“WSL”，可根据自己需求选择安装一个或多个Linux系统：ubuntu

- 安装完成后可在开始菜单里找到快捷方式并启动，第一次运行需要等待安装并设置用户名、密码。

- 访问WSL的根目录:

  C:\Users\EDZ\AppData\Local\Packages\CanonicalGroupLimited.UbuntuonWindows_79rhkp1fndgsc\LocalState\rootfs

##### zsh

安装zsh

```
sudo apt install zsh
```

安装oh-my-zsh

https://www.jianshu.com/p/30388763cf63

```
sh -c "$(curl -fsSL https://gitee.com/shmhlsy/oh-my-zsh-install.sh/raw/master/install.sh)"
```

设置默认 shell 为 zsh

```
chsh -s $(which zsh)
```

设置完成后使用下列命令检查是否设置成功

```
echo $SHELL
```

##### tip

然后在 .zshrc 中增加：

export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm
[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # This loads nvm bash_completion
1
2
3

————————————————
版权声明：本文为CSDN博主「亮子介」的原创文章，遵循CC 4.0 BY-SA版权协议，转载请附上原文出处链接及本声明。
原文链接：https://blog.csdn.net/henryhu712/article/details/85217165

- 插件权限

  ```
  chmod 755  /root/.oh-my-zsh/custom/plugins/zsh-syntax-highlighting
  ```

- vscode

  ```
  "terminal.integrated.shell.windows": "C:\\WINDOWS\\System32\\wsl.exe",
  ```

# ubuntu

## 命令

### **删除**

**1.非常有用的清理命令：                                                                                                                                      **

sudo apt-get autoclean        清理旧版本的软件缓存
sudo apt-get clean          清理所有软件缓存
sudo apt-get autoremove       删除系统不再使用的孤立软件
这三个命令主要清理升级缓存以及无用包的。

**2.清理opera firefox的缓存文件：**
ls ~/.opera/cache4
ls ~/.mozilla/firefox/*.default/Cache

**3.删除文件：**

```
sudo rm -rf  + 要删除的文件   进行删除
-r 表示向下递归
-f 表示强制删除，不作任何提示

rm -rf generated/*
```

### **权限**

```
$ sudo chmod +x /usr/local/bin/docker-compose
```

ls -al查看文件读写权限

### **ps进程指令**

linux上进程有5种状态:

1. 运行(正在运行或在运行队列中等待)

2. 中断(休眠中, 受阻, 在等待某个条件的形成或接受到信号)

3. 不可中断(收到信号不唤醒和不可运行, 进程必须等待直到有中断发生)

4. 僵死(进程已终止, 但进程描述符存在, 直到父进程调用wait4()系统调用后释放)

5. 停止(进程收到SIGSTOP, SIGSTP, SIGTIN, SIGTOU信号后停止运行运行)

1）ps a      显示现行终端机下的所有程序，包括其他用户的程序。

2）ps -A    显示所有程序。

3）ps u     以用户为主的格式来显示程序状况。

4）ps x 　 显示所有程序，不以终端机来区分。

```
ps aux
//查看username下的进程
ps  -u username
//查看程序的PID
pgrep 程序名
//结束进程
kill -9 PID # PID是进程号,查看进程时会显示
//结束某个程序
pkill  程序名
```

Ubuntu中找到并杀死僵尸进程:

```
//status
D 无法中断的休眠状态（通常 IO 的进程）；
R 正在运行可中在队列中可过行的；
S 处于休眠状态；
T 停止或被追踪；
W 进入内存交换 （从内核2.6开始无效）；
X 死掉的进程  （基本很少見）；
Z 僵尸进程；

ps aux | grep 'Z' 来找到僵尸进程
//pstree树状显示进程信息
pstree -p -s PID来寻找编号为PID进程也就是僵尸进程的父级进程。
```

### **删除多余内核**

**1，首先要使用这个命令查看当前Ubuntu系统使用的内核**

```
uname -a
```

**2，再查看所有内核**

```
dpkg --get-selections|grep linux 
```

**3，最后小心翼翼地删除吧**

```
sudo apt-get remove linux-image-2.6.32-22-generic
```

###  文件

``` 
创建目录mkdir
创建文件touch
查询绝对路径pwd
将文件1复制到文件2或者某个路径中       cp 文件1 	文件2/路径 
移动文件  mv 
重命名   mv 文件1	文件2

删除 rm -rf generated/*
```

```
ls     
ll(文件详细信息)
```

```
 du -sh *  	查看文件列表和大小
--------
217M	@tarojs
5.0M	autocannon
 58M	cnpm
 53M	commitizen
  0B	cw-tool
 65M	elasticdump
```

### vim

```
vim 文件

1.插入模式：i

2.正常模式:esc
复制一行/N行			yy /Nyy
粘贴			p
剪切一行/N行			dd/Ndd
撤销		u

3.命令模式：shift+：
```

## **软件**

### 安装指令

输入`dpkg --list` ,按下Enter键，终端输出以下内容，显示的是你电脑上安装的所有软件。 

```
//安装软件包
sudo dpkg -i  
//安装软件
 sudo apt-get install
 //安装源码包
 ./configure
make
sudo make install
//安装出错，修复依赖
sudo apt-get install -f

//卸载
sudo dpkg -r linuxqq 
sudo apt-get remove  linuxqq 
1）移除式卸载：apt-get remove softname1 softname2 …;（移除软件包，当包尾部有+时，意为安装）
2）清除式卸载 ：apt-get –purge remove softname1 softname2…;(同时清除配置)

//更新软件信息数据库
sudo apt-get update——更新源
sudo apt-get dist-upgrade 
apt-get upgrade ——更新已安装的包
//进行系统升级
apt-get dist-upgrade # ———升级系统

apt-get check #——-检查是否有损坏的依赖
```

### 截图软件flameshot

```
sudo apt-get install flameshot
```

**快捷键设置：**

设置——设备——键盘，拉到最下面，添加快捷键，“命令”输入“flameshot gui”



![在这里插入图片描述](https://img-blog.csdnimg.cn/20190710114019202.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dhbmd5dWFua2wxMjM=,size_16,color_FFFFFF,t_70)

### zsh（终端）

windows下好用的终端: consolez, [babun](https://github.com/babun/babun) +cmder,wsl

1.安装zsh
2.在根目录下的.zshrc文件中可以添加插件

- z 是跳转目录，他会记得你进入过的目录
  先`cd /usr/share/fonts/`
  下一次直接`z fonts`即可

- web-search
  这个插件允许你直接从终端打开浏览器进行搜索
  比如`baidu 随意随缘`

- extract
  万能解压，不管什么压缩文件包括zip,rar,tar
  输入`x 文件名`即可调用正确工具进行解压（前提是已经安装好工具）

- git-open

  [git-open](https://github.com/paulirish/git-open)插件可以在你git项目下打开远程仓库浏览项目。

  ```
  git open
  ```

```
plugins=(
	git
	z
	git-open
	zsh-autosuggestions
	zsh-syntax-highlighting
	web-search
	extract
)
```

终端执行 source .zshrc，加载扩展。

```
//以下是当source .zshrc执行时，一些扩展没有添加，从而命令行执行
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting

git clone git://github.com/zsh-users/zsh-autosuggestions $ZSH_CUSTOM/plugins/zsh-autosuggestions

git clone https://github.com/paulirish/git-open.git $ZSH_CUSTOM/plugins/git-open
```

```
//切换zsh终端
chsh -s /bin/zsh

echo $SHELL
```

```
//安装zsh后nvm、npm失效
安装zsh后原来安装的nvm及npm都失效了
查看原来的配置nvm的信息还在

解决方法：
在 ~/.zshrc 中再次添加原nvm在 ~/.bashrc 中的配置(搜索export可找到nvm配置)，并 source ~/.zshrc 即可
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm
[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # This loads nvm bash_completion
```

3.将命令行翻墙脚本放在.zshrc文件中

```
alias proxy="export all_proxy=socks5://127.0.0.1:1089"
alias unproxy="unset all_proxy"
```

### dingding

- https://github.com/nashaofu/dingtalk

### 压缩和解压

**rar**

压缩功能

```shell
sudo apt-get install rar
```

解压功能

```shell
sudo apt-get install unrar
```

使用

1. 可以直接在UI界面使用了
2. `rar x test.rar`

**.tar**

解包：tar xvf FileName.tar

打包：tar cvf FileName.tar DirName

**.gz**

解压1：gunzip FileName.gz

解压2：gzip -d FileName.gz

压缩：gzip FileName

**.tar.gz 和 .tgz**

解压：tar zxvf FileName.tar.gz

压缩：tar zcvf FileName.tar.gz DirName

**.zip**

解压：unzip FileName.zip

压缩：zip FileName.zip DirName

### snap

https://snapcraft.io/install/qv2ray/ubuntu#install

### Synaptic Package Manager 

是基于APT的图形化包管理工具，它不仅能列出ubuntu系统中所有已经安装的程序，还可以用于安装、卸载、升级软件。系统默认没有此工具，因此需要先通过命令行来安装它。
1、运行命令行
2、sudo apt update
3、sudo apt install synaptic
4、运行Synaptic

# nvm

https://blog.csdn.net/henryhu712/article/details/85217165

https://blog.csdn.net/geol200709/article/details/82117103

cd ~/ - -切到主目录
git clone https://github.com/creationix/nvm.git .nvm - -克隆代码到文件夹 .nvm
cd ~/.nvm - -进入nvm代码目录
git checkout v0.33.11 - -切换到v0.33.11版本

设置国内镜像

```
export NVM_NODEJS_ORG_MIRROR=https://npm.taobao.org/mirrors/node
```

查看可供安装的版本

```
nvm ls-remote
```

安装一个nodejs版本

```
nvm install v12.16.1
```

查看本地安装的版本

```
nvm ls
```

- 在.zshrc中添加

  ```
  export NVM_DIR="$HOME/.nvm"
  [ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm
  [ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # This loads nvm bash_completion
  ```

# Typora

Ctr+L 选中当前句子
Ctr+D 选中当前词
Ctr+J  跳转到光标
Ctr+数字 标题
Ctr+Shift +K 代码块
Ctr+Shift +` 代码

## 文件

| 功能                 | 热键（Windows / Linux） | 热键（macOS）        |
| :------------------- | :---------------------- | :------------------- |
| 新                   | Ctrl + N.               | Command + N.         |
| 新窗户               | Ctrl + Shift + N.       | Command + Shift + N. |
| 新标签               | *（不支持）*            | Command + T.         |
| 打开                 | Ctrl + O.               | Command + O.         |
| 快速打开             | Ctrl + P.               | Command + Shift + O. |
| 重新打开已关闭的文件 | Ctrl + Shift + T.       | Command + Shift + T. |
| 保存                 | Ctrl + S.               | Command + S.         |
| 另存为/重复          | Ctrl + Shift + S.       | Command + Shift + S. |
| 偏爱                 | Ctrl +，                | Command +，          |
| 关                   | Ctrl + W                | Command + W          |

## 编辑

| 功能                                | 热键（Windows / Linux）    | 热键（macOS）                       |
| :---------------------------------- | :------------------------- | :---------------------------------- |
| 新段落                              | 输入                       | 输入                                |
| 新队                                | Shift + Enter              | Shift + Enter                       |
| 切                                  | Ctrl + X.                  | Command + X.                        |
| 复制                                | Ctrl + C.                  | Command + C.                        |
| 糊                                  | Ctrl + V.                  | Command + V.                        |
| 复制为Markdown                      | Ctrl + Shift + C.          | Command + Shift + C.                |
| 粘贴为纯文本                        | Ctrl + Shift + V.          | Command + Shift + V.                |
| 全选                                | Ctrl + A.                  | Command + A.                        |
| 选择行/句子 选择行（在表格中）      | Ctrl + L.                  | Command + L.                        |
| 删除行（在表中）                    | Ctrl + Shift + Backspace   | Command + Shift + Backspace         |
| 选择样式范围 选择单元格（在表格中） | Ctrl + E.                  | Command + E.                        |
| 选择Word                            | Ctrl + D.                  | Command + D.                        |
| 删除Word                            | Ctrl + Shift + D.          | Command + Shift + D.                |
| 跳到顶部                            | Ctrl + Home                | Command +↑                          |
| 跳转到选择                          | Ctrl + J                   | Command + J                         |
| 跳到Buttom                          | Ctrl + End                 | Command +↓                          |
| 找                                  | Ctrl + F.                  | Command + F.                        |
| 找下一个                            | F3 /回车                   | Command + G / Enter                 |
| 找到上一个                          | Shift + F3 / Shift + Enter | Command + Shift + G / Shift + Enter |
| 更换                                | Ctrl + H.                  | Command + H.                        |

## 段

| 功能         | 热键（Windows / Linux） | 热键（macOS）            |
| :----------- | :---------------------- | :----------------------- |
| 标题1到6     | Ctrl + 1/2/3/4/5/6      | Command + 1/2/3/4/5/6    |
| 段           | Ctrl + 0                | 命令+ 0                  |
| 提高标题级别 | Ctrl + =                | 命令+ =                  |
| 降低标题级别 | Ctrl + -                | 命令+ -                  |
| 表           | Ctrl + T.               | Command + Option + T.    |
| 代码围栏     | Ctrl + Shift + K.       | Command + Option + C.    |
| 数学块       | Ctrl + Shift + M.       | Command + Option + B.    |
| 引用         | Ctrl + Shift + Q.       | Command + Option + Q.    |
| 订购清单     | Ctrl + Shift + [        | Command + Option + O.    |
| 无序列表     | Ctrl + Shift +]         | Command + Option + U.    |
| 缩进         | Ctrl + [/ Tab           | Command + [/ Tab         |
| 减少缩进     | Ctrl +] / Shift + Tab   | Command +] / Shift + Tab |

## 格式

| 功能     | 热键（Windows / Linux）             | 热键（macOS）         |
| :------- | :---------------------------------- | :-------------------- |
| 强大     | Ctrl + B.                           | Command + B.          |
| 重点     | Ctrl + I                            | 命令+我               |
| 强调     | Ctrl + U.                           | Command + U.          |
| 码       | Ctrl + Shift +`| Command + Shift +` |                       |
| 罢工     | Alt + Shift + 5                     | Control + Shift +`    |
| 超链接   | Ctrl + K.                           | Command + K.          |
| 图片     | Ctrl + Shift + I                    | Command + Control + I |
| 清除格式 | Ctrl + \                            | 命令+                 |

## 视图

| 功能                      | 热键（Windows / Linux） | 热键（macOS）         |
| :------------------------ | :---------------------- | :-------------------- |
| 切换补充工具栏            | Ctrl + Shift + L.       | Command + Shift + L.  |
| 大纲                      | Ctrl + Shift + 1        | Command + Control + 1 |
| 用品                      | Ctrl + Shift + 2        | Command + Control + 2 |
| 文件树                    | Ctrl + Shift + 3        | Command + Control + 3 |
| 源代码模式                | Ctrl + /                | 命令+ /               |
| Fouus模式                 | F8                      | F8                    |
| 打字机模式                | F9                      | F9                    |
| Toggler全屏               | F11                     | Command + Option + F. |
| 真实大小                  | Ctrl + Shift + 0        | *（不支持）*          |
| 放大                      | Ctrl + Shift + =        | *（不支持）*          |
| 缩小                      | Ctrl + Shift + -        | *（不支持）*          |
| 在打开的Documnets之间切换 | Ctrl + Tab              | 命令+`                |
| 切换DevTools              | Ctrl + Shift + I        | -                     |

# cmdr

Tab       自动路径补全
Ctrl+T    建立新页签
Ctrl+W    关闭页签
Ctrl+Tab  切换页签
Alt+F4    关闭所有页签
Alt+Shift+1 开启cmd.exe
Alt+Shift+2 开启powershell.exe
Alt+Shift+3 开启powershell.exe (系统管理员权限)
Ctrl+1      快速切换到第1个页签
Ctrl+n      快速切换到第n个页签( n值无上限)
Alt + enter 切换到全屏状态
Ctr+r       历史命令搜索
Win+Alt+P   开启工具选项视窗