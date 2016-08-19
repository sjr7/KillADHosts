#Hosts屏蔽常用广告
---
Hosts是一个没有扩展名的系统文件，可以用记事本等软件进行修改，它的作用就是将一些常用的网址跟IP地址建立一种“**指引**”关系，当客户端访问网址时首先在本机的Hosts文件中寻找是否有对应的IP地址，如果有的话，系统会立即打开对应网页，否则就会将网址提交到DNS服务器进行IP地址的解析。
<hr>
##各系统Hosts文件位置
**重要要的事情说三遍**<br>
Hosts文件是没有扩展名的，文件名就是Hosts !<br>
Hosts文件是没有扩展名的，文件名就是Hosts !<br>
Hosts文件是没有扩展名的，文件名就是Hosts！<br>

**Windows**系统
<br>
`C:\Windows\System32\drivers\etc\hosts`
<br>
**Android**（安卓）系统
<br>
`/system/etc/hosts`
<br>
**Mac**（苹果电脑）系统
<br>
`/etc/hosts`
<br>
**iPhone**（iOS）系统
<br>
`/etc/hosts`
<br>
**Linux**系统hosts位于
<br>
`/etc/hosts`
<hr>
##修改注意事项

你可以使用任意文本编辑软件编辑该文件，但是Hosts文件属于系统核心文件，需要获取管理员权限方可修改,Mac、iPhone、iPad也必须越狱才能修改。Windows系统跟苹果系统的hosts文件文本编码和换行符格式一样，而Android需要使用ANSI编码格式，务必注意，否则修改可能无效！

Windows用户必须用管理员身份打开才能修改保存，如果遇到无法保存，请右键文件hosts并找到“属性” -> “安全”，然后选择你登陆的用户名，最后点击编辑，勾选“写入”即可。
<hr>
Android（安卓）必须Root才能修改，Root Explorer管理器或ES文件浏览器装载/system可写状态，找到/system/etc/hosts的文件，使用文本编辑器打开编辑后保存。
<hr>
Linux系统使用Root权限vi编辑


##修改hosts后生效的方法

**Windows**

开始 -> 运行 -> 输入cmd -> 在CMD窗口输入

`ipconfig /flushdns`
<hr>
**Linux**

终端输入

`sudo rcnscd restart`
<hr>
**Linux发行版**

`sudo systemctl restart NetworkManager`
<hr>
**Mac OS X**

`sudo killall -HUP mDNSResponder`
<hr>
**Android**

`开启飞行模式 -> 关闭飞行模式`
<hr>
通用办法：

`拔网线(断网) -> 插网线(重新连接网络) 或者重启系统。`
