# NJUPT-AutoLogin

由于2023年暑假南邮更新了校园网认证系统，把原来的POST方式改成了GET，还引入了HTTPS，以前的登录脚本需要大改，于是有了这个项目。

【测试环境】
- OS: Windows10
- Python 3.8.10 (Anaconda3)
- httpx 0.24.1
- win10toast 0.9

【版本介绍】
- NJUPT-AutoLogin.py（源码原文件）：最基本的功能
- NAL-Toast.pyw（通知版）：经过一些设置后不会弹控制台的黑框

## ❤准备工作

本项目使用了Python第三方库`httpx`，用来支持HTTP/2的请求。使用以下控制台命令下载：

```
pip install httpx
```
```
pip install httpx[http2]
```

如果需要使用通知版，还需要额外下载`win10toast`库，命令如下：

```
pip install win10toast
```

注：`requests`库不支持HTTP/2，所以用的`httpx`，但是我看到其他人的项目用`requests`库也行？

## ➡修改代码

用记事本或其他文本编辑器打开源码，在`USERNAME`和`PASSWD`后面的双引号中间填写对应信息，并修改`SEL`后面的数字选择运营商，如下方代码块所示。
```python
#定义登录时需要用的变量
USERNAME = "BXXXXXXXX"      #用户名
PASSWD = "💅💅💅💅💅💅"    #密码
SEL = 1     #0-校园网；1-中国电信；2-中国移动
```

## 🧱cmd.exe，启动！

在与源码同一目录下，新建一个文本文档，将后缀改成`.bat`，复制下面的代码并保存，你也可以自行修改😘：

```
@ECHO OFF
chcp 65001
title NJUPT校园网登录
python ./NJUPT-AutoLogin.py
pause
EXIT
```

如果需要使用通知版，需要下载本项目的/ico/文件夹下的所有图片文件。

右键`NAL-Toast.pyw`点击创建快捷方式，在“目标路径”的最前面添加`pythonw.exe `，注意和后面的内容要有空格，而且要给Python设置环境变量。

最后把这个快捷方式放到桌面或者开始菜单，需要的时候双击即可。
