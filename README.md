# V2RayS
一个V2Ray的Windows客户端

## 说明
本程序的目的是尽量简单的使用V2Ray，虽然在初期做了许多可以修改配置的功能，但是我后来决定将其禁用了。
因为一些朋友使用，又不太懂配置等等，所以太复杂的功能也去除，基本上是傻瓜式的。
本程序面向的使用场景主要为自己架设或购买了V2Ray服务端，平时主要为浏览网页、看视频、普通下载等，使用pac文件判断是否走代理，不涉及复杂路由等场景。
本程序有如下的重点说明：
### 只使用HTTP代理：
虽然可以通过修改配置文件实现使用socks代理等，但还是建议只使用HTTP代理。也不需要再添加socks转http的功能了，当然一些特定需要socks代理的场景，本程序也就不适合了。
### PAC服务：
自带PAC的服务器，读取本地pac文件。使用PAC的好处为不走代理的网站可以彻底直连，不需要经过本地V2Ray程序。
程序会自动设置Win系统的代理（即IE代理），可以设置为使用PAC文件以及全部使用代理，因此，请确保程序目录下有pac.txt文件，本程序自带了一个pac文件，也可以使用自己的。程序退出时会删除已设置的IE代理，但若程序崩溃或直接终止任务，可能会引起IE代理没有还原，请手动修改。
1.0.0.3: 增加了编辑PAC文件的功能，所以现在不能使用其他的pac文件了，除非你不使用编辑功能。
### config.json文件：
程序默认如下的使用场景：
客户端只使用Vmess协议，不涉及ss。当然，服务器端开启了ss功能不影响。
鉴于mkcp容易被封，因此不使用mkcp，其他传输方式很少涉及，因此只默认使用TCP协议，建议在服务器端开启BBR，效果与mKcp差不多。
鉴于一些情况下，开启Mux会断流，因此添加了Mux开关，平时建议开启。
因为已经使用pac文件做了是否使用代理的判断，因此删除了配置文件路由功能中关于大陆IP地址或网站判断的部分。
因为上述功能，直接使用V2Ray自带的配置文件可能引起程序出错，因此自带了config.json文件。
也可以手动修改配置文件实现socks，mkcp等功能，不过如果需要的话，建议使用另一个客户端V2RayN。本程序还是尽量精简。

### 使用方式：
目前直接解压运行即可，程序会修改注册表实现自动启动、修改IE代理设置等，若有警告请允许。程序退出时会删除已设置的IE代理，但若程序崩溃或直接终止任务，可能会引起IE代理没有还原，请手动修改。
V2Ray自带的服务器只作为示例，所以你需要自己有V2Ray的服务器。如何在VPS上安装V2Ray服务，请参考官方网站或其他教程
https://www.v2ray.com/chapter_00/install.html

## 本程序运行需要.NET Framework 4.6
