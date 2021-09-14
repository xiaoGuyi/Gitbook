# ubuntu命令及相关配置

<!-- toc -->

## 软件配置

### 打开typora
> **命令：**typora --no-sandbox
>
> **修改内容：**在ubuntu的root用户下安装后并不能直接使用，需要将命令Exec=typora %U 改为typora --no-sandbox才能打开
>
> **注：**如果勾选权限中的允许作为程序执行文件，将无法在所有应用中看到typora

### 微信

#### 微信安装

> 链接：[参考教程](https://zhuanlan.zhihu.com/p/336593807)

#### 解决微信字体太小问题

> 1. 进入~/.deepinwine/Deepin-WeChat
> 2. 执行WINEPREFIX=~/.deepinwine/Deepin-WeChat deepin-wine winecfg
> 3. 调整DPI

### gitbook

#### 安装方式

##### 安装nodejs

> 1. curl -sL https://deb.nodesource.com/setup_4.x | sudo -E bash -
> 2. sudo apt-get install -y nodejs
> 3. sudo apt-get install -y build-essential
> 4. sudo apt install npm

##### 安装gitbook

> 1. npm install -g gitbook-cli
> 2. gitbook -V #查看是否安装成功

##### 安装gitbook到处pdf工具

> 1. apt-get install calibre

#### 设置每页目录

> 1. 创建book.json，添加以下内容

```json
{ "plugins": ["page-treeview"] } 
```

> 2. 执行gitbook install
>
> 3. 在需要目录的地方加上 

```html
<!--toc-->
```

#### 生成方法

> 1. 进入工作目录
> 2. 执行gitbook init
> 3. 执行gitbook serve

#### 自动生成SUMMY.md

> [参考教程](https://www.shangmayuan.com/a/2d60bfa909274121a27682d1.html)
>
> 1. 进入书籍路径（有README.md）
> 2. 执行book sm

## 操作命令

### 杀进程
> ps -e  # 查看所有进程情况
> kill + 进程号

### 快捷键

> super + h  # 隐藏当前窗口
>
> super + F10  # 进入应用程序菜单
>
> super + m  # 日历
>
> super + shift + s  #截图（自定义的）
>
> crtl + Q  #退出应用程序
>
> Ctrl+u  # 删除此处至开始的所有内容
>
> Shift+Ctrl+T  # 打开新的标签页
>
> ctrl + u  # 删除在该字符前的所有字符
>
> ctrl + d  # 删除当前字符
>
> ctrl + h  # 删除后面一个字符

### 后台执行（不占用终端）

> 在程序后面加上&

### 文件的快速预览

> [参考教程](https://zhuanlan.zhihu.com/p/100041036)，采用Sushi实现

### 删除命令

|命令|备注|
| :----------: | :--------------------------------------: |
| -f、--force  | 强力删除，不要求确认                     |
| -i           | 每删除一个文件或进入一个子目录都要求确认 |
| -I           | 在删除超过三个文件或者递归删除前要求确认 |
| -r、-R       | 递归删除子目录                           |
| -d、-dir     | 删除空目录                               |
| -v、-verbose | 显示删除结果                             |

### 文件查找

|         命令         |                             备注                             |
| :------------------: | :----------------------------------------------------------: |
| find / -name +文件名 |                    在指定的目录下遍历查找                    |
|    locate+文件名     |           效率比find会高很多，比较推荐使用这种方法           |
|  which+可执行文件名  | which的作用是在PATH变量指定的路径中，搜索某个系统命令的位置，并且返回第一个搜索结果 |
|    whereis 文件名    | 快速,但是是模糊查找,例如 找 #whereis mysql 它会把mysql,mysql.ini,mysql.*所在的目录都找出来. |

### 命令行打开文件夹

> 命令：nautilus &

### 卸载软件

> 1. dpkg --list  # 查看所有已安装的包（如果看不清楚可以使用 dpkg --list | more）
> 2. 找到要删除的包，执行sudo apt-get --purge remove 包名（–purge是可选项，写上这个属性是将软件及其配置文件一并删除，如不需要删除配置文件，可执行sudo apt-get remove 包名）
> 3. dpkg --search <filename_pattern>  # 筛选出包含指定文件（模式）的软件包

### 死机处理方法

> 1. ctrl + alt + F1切换用户
>
> 2. ps -t tty2  # 查看用户2中正在运行的进程
> 3. 找到Xorg锦城南对应的PID号（Xorg是界面上的进程）
> 4. kill xxx
> 5. 切换回去登录（搞定）

### 更新软件

> 1. sudo apt update
> 2. sudo apt upgrade

###  将文件夹加入侧边栏

> [参考教程](https://blog.csdn.net/Hao_jiu/article/details/108921816)

