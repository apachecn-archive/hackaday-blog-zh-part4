# 日产放弃根壳感谢黑客入侵的 USB 驱动器

> 原文：<https://hackaday.com/2021/01/30/nissan-gives-up-root-shell-thanks-to-hacked-usb-drive/>

对于那些可能从谷歌加入我们的不耐烦的日产车主，一个名叫 [[ea]的黑客已经找到了如何在他们的 2015 Xterra](https://github.com/ea/bosch_headunit_root) 的博世 LCN2kai 主机上获得根外壳的方法，看起来这个过程应该对日产家族的其他车辆如 Rogue，Sentra，Altima 和 Frontier 也是一样的。如果你想在家里一起玩，你所要做的就是把提供的图像写入 USB 闪存驱动器并插入。

现在，对于我们这些对整个过程如何工作更感兴趣的人来说，[ea]足以提供一个关于这个漏洞是如何被发现的非常详细的描述。从从崩溃的 Xterra 中取出一个备用的 Linux 驱动的主机进行实验开始，这篇文章带领读者经历了每次发现和权限提升，最终导致非侵入性攻击的开发，这种攻击不需要用户拆开整个仪表板来运行。

这个过程的早期阶段对任何搞嵌入式 Linux 黑客的人来说都很熟悉。第一步是找到电路板的串行端口，并将其连接到计算机。从那里，[ea]能够改变引导装载程序中的内核参数，以产生一个交互式 shell。为了使事情变得简单一点，启动脚本被修改，这样系统就可以启动一个可以通过 USB 以太网适配器访问的 SSH 服务器。有了对系统的完全访问权，就可以开始搜索漏洞了。

[![](img/e1dcde864cb1b010e00d1328f180a78f.png)](https://hackaday.com/wp-content/uploads/2021/01/nissanroot_detail1.png)

A simple script on the flash drive enables the SSH server.

经过一番探索后，[ea]发现设计用来挂载 USB 存储设备的脚本有一个潜在的缺陷。该脚本是以这样一种方式编写的，即设备的文件系统标签将用于创建挂载点，但是没有适当的检查来防止目录遍历攻击。通过制作一个标签，上面写着`../../usr/bin/`，并在驱动器上放置一个 Bash 脚本，就可以在主机上运行任意命令。提供的脚本将 SSHd 永久地添加到启动过程中，因此当系统重新启动时，您将能够登录并浏览。

那么[ea]想用这个新发现的漏洞做什么呢？看起来我们的目标是最终开发出一些定制程序来扩展嵌入式 Linux 系统的功能。由于这些“信息娱乐”系统似乎已经成为现代汽车不可避免的特征，我们当然很高兴看到旨在让它们处于消费者控制之下的项目。