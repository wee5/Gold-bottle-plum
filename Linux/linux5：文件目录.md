# linux5：文件目录



文件：可以用text形式打开的

文件夹：即目录，可以存放文件的地方



## linux一切皆文件

在windows的文件，在linux中也是文件

在windows不是文件的，在linux中也是以文件形式存储的



## 目录结构

bin：全称binary，即二进制。该目录中存放的都是一些二进制文件，文件都是可以被运行的

dev：该目录中主要存放外接设备，如u盘，光盘，移动硬盘。其中的外接设备不能直接被使用，需要挂载（类似windows中分配盘符）

etc：存放配置文件

home：表示除了root用户以外的用户的家目录，类似windows下的user/用户目录

proc：process，即进程。存放linux运行时的进程

root：root用户的家目录

sbin：全称super binary，存放可以被执行的二进制文件，必须是super权限的用户才能执行

tmp：template，即临时目录，当系统运行时产生的临时文件会存放在该目录

usr：用户自己安装的软件

var：存放程序或系统日志文件的目录

mnt：当外接设备需要挂载时，就会挂载到mnt目录下



## 路径

文件和文件夹有一个名称，**名称并不是唯一的**，即两个不同文件夹中可以有相同名称的文件和文件夹

路径指向一个**唯一的**文件或文件夹

路径表示方式为盘符 / 加文件夹名称（**绝对路径**）

也可以省略当前目录的路径（**相对路径**）

### 常用路径

/：绝对路径

./：当前目录路径

../：当前目录的上级目录



