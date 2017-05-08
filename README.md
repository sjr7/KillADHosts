## Hosts屏蔽常用广告

在国内的上网环境下浏览网页是各种广告，虽然有很多浏览器插件或者第三方软件可以屏蔽页面广告或者是软件内嵌广告，但是可以找到一个更加简洁的方法来达到我们的母的，那就是修改系统中的hosts文件，关于hosts文件请自行上网脑补

~~更改的hosts地址可能会影响对应域名的正常通信，修改前确定自己要有修改hosts能力，在发生跟指定域名通信出错的时候请及时删除对应的域名规则~~

---
简单地介绍下，Hosts是一个没有扩展名的系统文件，可以用记事本等软件进行修改，它的作用就是将一些常用的网址跟IP地址建立一种“**指引**”关系，当客户端访问网址时首先在本机的Hosts文件中寻找是否有对应的IP地址，如果有的话，系统会立即打开对应网页，否则就会将网址提交到DNS服务器进行IP地址的解析。

---

## 使用方法

- 建议对应自己需求选择性地复制想要屏蔽的域名，不推荐一次性把很多域名屏蔽
- 建议自行复制域名列表到自己系统的hosts文件中，以为不同的系统hosts换行方式本一样，直接下载目录中的文件进行替换可能会出错，本目录下所有的hosts文件均在**Windows**系统中中产生
- 直接下载目录下文件进行替换的请注意修改文件名为```Hosts```

##  各系统Hosts文件位置

**重要的事情说三遍**

- Hosts文件是没有扩展名的，文件名就是Hosts !
- Hosts文件是没有扩展名的，文件名就是Hosts !
- Hosts文件是没有扩展名的，文件名就是Hosts !


---

**Windows**系统

`C:\Windows\System32\drivers\etc\hosts`


**Android** 

`/system/etc/hosts`


**Mac**

`/etc/hosts`

**iPhone** 

`/etc/hosts`

**Linux** 

`/etc/hosts`

---
##  修改注意事项

你可以使用任意文本编辑软件编辑该文件，但是Hosts文件属于系统核心文件，需要获取管理员权限方可修改,Mac、iPhone、iPad也必须越狱才能修改。Windows系统跟苹果系统的hosts文件文本编码和换行符格式一样，而Android需要使用ANSI编码格式，务必注意，否则修改可能无效！

- Windows用户必须用管理员身份打开才能修改保存，如果遇到无法保存，请右键文件hosts并找到“属性” -> “安全”，然后选择你登陆的用户名，最后点击编辑，勾选“写入”即可。

> 如果右键没有获取管理员身份或者以管理员身份运行的话，请下载[tools](https://github.com/Sunybyjava/KillADHosts/tree/master/tools)文件夹中的获取管理员批处理文件进行获取，请对应自己的系统进行获取文件！下载后双击执行，如果弹出对话框的话点击同意，自行关闭360等杀毒软件！

- Android（安卓）必须Root才能修改，Root Explorer管理器或ES文件浏览器装载/system可写状态，找到/system/etc/hosts的文件，使用文本编辑器打开编辑后保存。

> 温馨提示：直接将别的系统hosts文件复制到Android手机中进行替换很大可能是不会生效的，因为Android上hosts文件的换行符必须是\n而不是windows的\r\n，你可以用notepad++打开hosts文件，点菜单中的view-show symbol-show all characters，看到行末是LF就正确，CR LF就错误。如果是后者，你需要替换所有的CR LF为LF（用它的replace中的扩展模式）。请在Android系统下进行修改hosts文件，或者在PC端替换好换行符后发送给手机进行替换

- Linux系统使用Root权限进行编辑，例如可以使用linux发行版都会自带的vi编辑进行编辑，或者可以使用vim之类的

---

##  修改hosts后生效的方法

**Windows**

开始 -> 运行 -> 输入cmd -> 在CMD窗口输入

`ipconfig /flushdns`

**Linux**

终端输入

`sudo rcnscd restart`

**Linux发行版**

`sudo systemctl restart NetworkManager`

**Mac OS X**

`sudo killall -HUP mDNSResponder`

**Android**

`开启飞行模式 -> 关闭飞行模式`

通用办法：

`拔网线(断网) -> 插网线(重新连接网络) 或者重启系统。`


