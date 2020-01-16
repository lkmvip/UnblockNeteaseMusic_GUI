<div align=center><img width = '792' height ='290' src ="https://pic4.zhimg.com/v2-955997706de95754c0ad894f0c9e16d9_1200x500.jpg"/></div>

<img src="https://user-images.githubusercontent.com/26399680/47980314-0e3f1700-e102-11e8-8857-e3436ecc8beb.png" alt="logo" width="140" height="140" align="right">

# UnblockNeteaseMusic_GUI（转载自用/持续更新）

## 软件介绍

最近发现了一个可以解锁网易云音乐灰色歌曲的工具，但是使用起来不太方便，网上找的教程也都很写的复杂，于是干脆写个辅助软件好了~

该软件支持网易云音乐 Windows、UWP、Android、IOS(无法使用的可能原因) 客户端，并且支持下载最高 320kbps 音源！

主程序 Github 项目地址：https://github.com/nondanee/UnblockNeteaseMusic

你也可以手动更新主程序：https://github.com/nondanee/UnblockNeteaseMusic/archive/master.zip

原GUI作者开放地址：https://zhuanlan.zhihu.com/p/79631291

原GUI作者：[@西柚秀·知乎](https://www.zhihu.com/people/xiu2/activities)

原UnblockNeteaseMusic核心功能作者：[@Nzix](https://github.com/nondanee)

## 原理

创建一个针对网易云音乐域名的HTTP代理，经过该HTTP代理的网易云音乐变灰歌曲链接会被 QQ / 酷我 / 酷狗 / 百度 / 虾米 / 咕咪 / JOOX 音源替换，并且解锁海外限制(前提是你在海外)。

同时，因为是HTTP代理的原因，所以只支持HTTP流量，HTTPS需要导入证书，暂时不考虑，目前只有Linux、MacOS新版本客户端会强制HTTPS请求，其他的客户端在访问HTTPS失败后，就会降级访问HTTP，这样就会被替换变灰链接了。

也就是说，你可以在网易云音乐软件里听全网版权音乐(相对)，不仅如此，需要付费或者黑胶会员才能在线听及下载的音乐现在都可以免费听(下)了！~

## 当前版本 v3.0-v3

本软件仅为 UnblockNeteaseMusic 项目的 Windows GUI辅助工具。

本软件仅供学习使用，勿用于商业，请在下载后 24 小时之内删除。

## 文件说明：

UnblockNeteaseMusic-master - 主程序

node - 主程序的依赖

请不要删除以上文件！

> 本UnblockNeteaseMusic_GUI用外链方式直接链接主程序 Github 项目地址，直接更新即可

手机推荐使用：[Xposed 插件版](https://github.com/nining377/UnblockMusicPro_Xposed/releases) 。

Linux服务器部署推荐使用：[一键脚本](https://xiu2.github.io/SHELL/#/)。

哈勃检测：腾讯哈勃分析系统

注意：360之类的报毒正常，担心的请不要下载，免得地球爆炸。

注意：软件不支持 Windows XP 系统。

## 软件界面

![](https://pic3.zhimg.com/80/v2-32e32d95f6d03e702973a3fa2ac1ecc6_hd.jpg)

## 解锁灰色效果图

![](https://pic3.zhimg.com/80/v2-b0e7d26ff466b869dbebabd41ab6ecae_hd.jpg)

![](https://pic4.zhimg.com/80/v2-c1936e808da334dc95dde62172f3d463_hd.jpg)

![](https://pic2.zhimg.com/80/v2-8fd76f3ba41e8eba5032efb76e31d141_hd.jpg)

![](https://pic2.zhimg.com/80/v2-0e979750e52ad57579bf57f56d6c6701_hd.jpg)

---

## 使用说明

提示一下，点击软件右上角的 关闭按钮 [X] 就是托盘运行了

这个软件仅仅是辅助软件，还需要搭配 UnblockNeteaseMusic(主程序) 与 node(主程序依赖) 使用，不过我已经打包好了，下载解压后直接就能用了~

打开软件后，可以看到有三个使用模式，我在这里详细解释一下：

- **Hosts 模式：** 把网易云音乐的域名在hosts文件中指向 127.0.0.1，这样 Windows、UWP 客户端什么都不需要设置就能解锁灰色歌曲了。但是这同样会影响到网页版网易云音乐，所以请自行抉择。另外该模式时只能使用 80 代理端口。
- **UWP客户端 模式：** 通过修改系统代理设置的方式，使 UWP 客户端解锁灰色歌曲，网页版网易云音乐受影响，Windows 客户端不受影响。
- **Windows客户端 模式：** 什么都不修改，需要你手动前往 Windows 客户端设置HTTP代理为，服务器：127.0.0.1 端口：代理端口，其他 UWP 客户端、网页版网易云音乐不受影响。

以上三种模式，均支持 Android/IOS 客户端通过局域网连接（手机WIFI设置里有个代理设置，设置代理IP为你的电脑内网IP(下面有说)，端口为代理端口）！

首次点击 **[启动]** 按钮，防火墙提示说明：

打开软件首次点击 **[启用]** 按钮时，会提示如下图所示，点击 [允许访问] 即可。

![](https://pic2.zhimg.com/80/v2-842e536e7f6a69e08f732e71dc517005_hd.jpg)

## 网易云音乐 UWP 客户端(Windows10)使用前记得这样做

只有 Windows10 系统的 UWP版网易云音乐客户端才需要这样做，其他系统或其他版本的网易云音乐客户端请无视该步骤！

**请确保你的 Windows10 系统版本高于 170X**，否则执行下面代码后，因为系统版本低可能会出现影响系统稳定性的情况（仅限低版本系统）。

因为 Windows10 UWP 应用网络隔离，无法连接到 127.0.0.1，所以需要解锁一下网易云音乐UWP版的 loopback 权限才行。

1. 右键点击左下角的开始菜单 - Windows PowerShell(管理员) 选项，会提示如下图所示（如果你关了UAC则不会显示）。如果你找不到 Windows PowerShell(管理员) 选项 ，那么也可以 以管理员身份运行 CMD 去执行下面的操作，效果也是一样的。

![](https://pic2.zhimg.com/80/v2-64f7f712cf4be0526fa9bb4315bb2335_hd.jpg)

2. 然后运行这段代码

```
# 解锁UWP应用 loopback 权限(访问本机)
checknetisolation loopbackexempt -a -n="1F8B0F94.122165AE053F_j2p0p5q0044a6"

# 如果你取消解锁，即恢复原状，那么请执行：
checknetisolation loopbackexempt -d -n="1F8B0F94.122165AE053F_j2p0p5q0044a6"
```

![](https://pic1.zhimg.com/80/v2-d54fd51cc23710059967b3ad13bf2410_hd.jpg)

如上图所示提示，则代表成功。

## 网易云音乐 Windows 客户端设置代理教程

如下图所示设置即可（当然端口的话要根据你的代理端口来填写）。

![](https://pic2.zhimg.com/80/v2-d9abe8c6a436d79d3bd2f4661659d6dd_hd.jpg)

> 请不要点击 [测试] 按钮，因为网易云音乐测试代理是不会 HTTPS 降级 HTTP 的，所以会提示代理不可用，无需关心，不影响使用的。

> 如果设置正确却无法使用，那么请确认你的 Windows 客户端是最新版本，部分旧版本无法使用。

## 网易云音乐手机客户端使用简单说明

如果嫌手机使用麻烦的话，推荐使用安卓版：[Xposed 插件版](https://github.com/nining377/UnblockMusicPro_Xposed/releases)

网易云音乐 Android / IOS 客户端，可以通过在手机的 WIFI 代理设置中设置代理来解锁灰色歌曲。

如果要局域网内的网易云音乐手机客户端连接的话，请务必勾选 **[允许局域网连接]** ，否则手机是无法连接到的

![](https://pic3.zhimg.com/80/v2-aae55385a70a9db52f8da8cec9a66056_hd.jpg)

WIFI代理设置中的代理IP填写你的 PC 内网IP地址，软件下方写的有本机内网IP地址，内网IP地址查看方法，如果获取失败，请尝试手动获取：

Win+R 键 - cmd - 确定 - 输入 ipconfig，即可看到 IPv4 地址（内网IP大都是 192.168 开头）。因为各手机系统不一样，所以我也没办法截图，不过都是在 WIFI 设置里是肯定的（自行搜索 手机型号+WIFI代理设置）。

![](https://pic2.zhimg.com/80/v2-333eb9b10070503260316f257ec9bb61_hd.jpg)

![](https://pic3.zhimg.com/80/v2-008d76244c958813a43b2831c8af98a6_hd.jpg)

---

## 使用 hosts 模式并停止后，网易云音乐网页版及客户端均提示网络不可用解决办法

打开**C:\Windows\System32\drivers\etc\hosts**文件看看是不是还有这两行

```
127.0.0.1 music.163.com
127.0.0.1 interface.music.163.com
```
如果有就手动删除。

因为我测试是一切正常的，不清楚出现这个问题的电脑是什么原因，可能是安全软件在搞事吧。

## 可能无法使用的原因一：主程序有新版本

如果你使用姿势正常，但一直加载失败，那么可能是主程序过时该更新了。

在尝试修改音源排序无效的时候，请尝试更新主程序：点击下载主程序压缩包，下载后解压覆盖软件同目录下的 UnblockNeteaseMusic-master 文件夹。

## 可能无法使用的原因二：网易云音乐新版本客户端已修复该解锁方法

最新版本网易云音乐客户端似乎已修复该解锁方法（连万年不更新的 UWP 版都更新了），所以请使用旧版本网易云音乐客户端。



