# 汽车防盗系统攻击了 300 万辆汽车

> 原文：<https://hackaday.com/2019/03/08/car-alarm-hacks-3-million-vehicles/>

钢笔测试不是评估墨水。它是渗透测试的缩写——有人通过试图闯入或攻击系统来确保系统的安全性。一家名为 Pen Test Partners 的公司上周制造了一条新闻，宣布由几家供应商制造的高端汽车报警系统有一个严重的安全缺陷，可能会使车辆不太安全。他们声称大约有 300 万辆汽车受到影响。

下面的视频展示了来自 Viper/Clifford 和 Pandora 的警报如何用简单的方法劫持应用程序。一旦他们有了权限，他们就可以实时找到汽车，控制门锁，启动或停止汽车引擎。他们推测黑客可能触发了附近一辆警车的警报。如果你的闹钟响了，你可能会靠边停车。然后他们会把你锁在车里，靠近你，然后强迫你下车。

显然，有些警报器甚至有麦克风，这样你就可以监听目标的车里发生了什么。启动引擎可以让你燃烧汽油，也可以让别人的车库充满一氧化碳。

是什么引发了这一切？该团队注意到潘多拉声称他们的警报是“无法破解的”当然，黑客很难忽视这一点。根据公告:

> 令人惊讶的是，这些漏洞是 API 中相对简单的不安全直接对象引用(IDORs)。
> 
> 只需通过篡改参数，就可以在未经身份验证的情况下更新注册到该帐户的电子邮件地址，向修改后的地址(即攻击者的地址)发送密码重置，并接管该帐户。

对于 Viper 警报，修改用户请求不会在服务器上进行验证，所以如果您形成了正确的 HTTP 请求，就可以修改任何用户的密码。Pandora 系统允许你把用户的电子邮件地址改成你自己的。然后你可以重设密码，就这样。在某些情况下，似乎对报警器的控制可以让你在 CAN 总线上发送命令，这可以让你对汽车进行大量的控制。

按照道德规范的要求，该组织通知了供应商，据说漏洞已经被堵住了。有时你会听说一个黑客需要一些非常奇特的工作，但这些都非常简单。目前还不知道是否有人曾经以不良的方式使用过这些黑客技术，但这确实是一种可能。

随着越来越多的事情可以通过网络控制，安全性变得越来越重要。丢失你的信息已经够糟了，但是[现实世界的黑客](https://hackaday.com/2015/10/15/hijacking-quadcopters-with-a-mavlink-exploit/)会威胁你的财产甚至你的生命。

 [https://www.youtube.com/embed/aZUQmJMuf8c?version=3&rel=1&showsearch=0&showinfo=1&iv_load_policy=1&fs=1&hl=en-US&autohide=2&wmode=transparent](https://www.youtube.com/embed/aZUQmJMuf8c?version=3&rel=1&showsearch=0&showinfo=1&iv_load_policy=1&fs=1&hl=en-US&autohide=2&wmode=transparent)
