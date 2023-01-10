# 在苹果 A7、A8 和 A8X 设备上引导主线 Linux

> 原文：<https://hackaday.com/2022/06/12/boot-mainline-linux-on-apple-a7-a8-and-a8x-devices/>

[Konrad Dybcio]讲述了他的旅程[在 A7/8/8X 处理器上启动 Linux，](https://konradybcio.pl/linuxona7/)摆弄他放在抽屉里的旧 iPhone 5。这是一次为期两年的“时不时重访”之旅，动力来自于像[在 M1 苹果电脑上发布 Linux 这样的事情。](https://hackaday.com/2021/11/17/linux-coming-soon-to-m1-macbooks/)最后，我们在这里有一个在一些不太现代但仍然非常有用的 iPhones 上引导主线 Linux 的方法，以及一个关于实现这个方法的有趣故事。

[Konrad]的工作基于[沙堡项目研究，](https://hackaday.com/2020/03/27/this-week-in-security-0-days-pwn2own-ios-and-tesla/)但他不太清楚如何让他们的代码工作，必须在工作中理解它。在某个时候，他陷入了启用 MMU 的困境，这是一段时间内的主要障碍。另一名对苹果硬件感兴趣的开发人员也加入进来，他们一直在开发工具和巧妙的技巧，但都无济于事。有了可访问的帧缓冲区，并且看不到其他合适的调试方法，他讲述了他们写的一段代码，这段代码将寄存器值打印为有效的条形码

然后，更深入地研究已知的工作代码，他意识到[在加载 Linux 映像的方式上有一行差异](https://konradybcio.pl/linuxona7/#stage-6-wait-what-if)。为了解决这个问题，他们启用了 MMU！从这里开始，Linux 黑客部分接踵而至，并且仍在继续，其他人从各自的抽屉里拿出他们的旧设备，[也加入了进来。](https://twitter.com/ivoszbg/status/1532817254324240384)集成工作[正在进行，](https://github.com/konradybcio/linux-apple/commits/apple/v5.19-rc1)基本外围设备正在启动。一些外围设备可能不会很快工作，但是从现在开始，开发驱动程序并逐个征服这些设备应该会容易得多。

这项开发应该适用于 iPhone 5S、6 和 6 Plus、iPod touch 第 6 代以及 iPad Air 1/2 和 iPad Mini 2/3/4。您想在您拥有的这些设备上启动 Linux 吗？[Konrad] [分享了关于如何让你的设备从零到屏幕上的 Linux 引导日志的说明](https://konradybcio.pl/linuxona7/#stage-7-linux-time);[协助可用](https://twitter.com/quaack723/status/1533818585616982016)，但 Linux 的经验[是可取的！](https://twitter.com/konradybcio/status/1535732099906420736)如果你决定使用你自己的旧设备，你应该花一两分钟[在这个过程中帮助他](https://konradybcio.pl/linuxona7/#stage-8-can-i-help)——他正在从不同的设备中收集 ADT 文件，提供一个 ADT 文件的说明非常简单！

我们已经有一段时间没有在 iPhone 上看到 [Linux 了——大部分这样的黑客来自 2008 年左右，之后就销声匿迹了，只有一些很酷的东西，比如在 iPhone 7](https://hackaday.com/2008/11/28/iphone-linux/) 上出现的 [PostmarketOS。然而，我们希望这个](https://www.reddit.com/r/linux/comments/kux9xx/success_iphone_7_with_dead_nand_netbooting/)[能让我们的智能手机在实用性方面更接近我们的个人电脑](https://hackaday.com/2019/12/14/why-is-your-cellphone-not-a-more-useful-computer/)。

> 花了我们一年多的时间(时间太长了)，但是，在我意识到我们缺少一条线后，我让它工作了😎
> 
> A7-A8X。
> 
> 写上去儿子。[# Linux](https://twitter.com/hashtag/Linux?src=hash&ref_src=twsrc%5Etfw)[# AsahiLinux](https://twitter.com/hashtag/AsahiLinux?src=hash&ref_src=twsrc%5Etfw)[# check M8](https://twitter.com/hashtag/checkm8?src=hash&ref_src=twsrc%5Etfw)[pic.twitter.com/H5A9ZA8xyf](https://t.co/H5A9ZA8xyf)
> 
> —康拉德·戴比奥·✝️(@康拉德·戴比奥)[2022 年 6 月 1 日](https://twitter.com/konradybcio/status/1531963130934329344?ref_src=twsrc%5Etfw)