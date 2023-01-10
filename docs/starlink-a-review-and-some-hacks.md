# Starlink:一篇评论和一些黑客攻击

> 原文：<https://hackaday.com/2021/05/24/starlink-a-review-and-some-hacks/>

我可能会被描述为一个 SpaceX 爱好者。我尽可能地关注他们的发射，并以极大的兴趣关注着星际飞船的发展。但是 SpaceX 的可重复使用发射系统的副作用是去太空变得便宜了很多。拥有过剩的发射能力意味着以前不可行的太空项目突然变得至少可行了。其中之一就是 Starlink。

Starlink 是 SpaceX 的卫星互联网服务。无线和蜂窝网络在一些地方有所帮助，但是如果你真的住在乡下，卫星网络是你唯一的选择。虽然卫星互联网并不是什么新鲜事物，但 Starlink 有点不同。另一家提供商 Hughesnet 在地球静止轨道上有几颗卫星，距离地球约 22，000 英里。用格蕾丝·赫柏的话来说，他拿着一根将近一英尺长的电线代表一纳秒，“在这里和卫星之间，有非常多的纳秒

SpaceX 选择做一些有点不同的事情。在当时看来，这似乎是一个疯狂的白日梦，他们计划发射一个由 12，000 只鸟组成的卫星星座，其中一些鸟的飞行高度低至 214 英里。飞得这么低的缺点是它们不会在轨道上停留太久，但 SpaceX 发射它们的速度明显快于它们降落的速度。迄今为止，近 1600 颗 Starlink 卫星在轨道上运行，在 342 英里(550 公里)的高空呈十字交叉状。

这一百倍的海拔差异至关重要。Hughesnet 连接的最小理论延迟为 480 毫秒，实际上接近 600 毫秒。Starlink 预测理论最小延迟不到 10 毫秒，尽管实际性能还没有那么低。在我使用这项服务的几周里，ping 时间从 60 多秒下降到了 20 多秒和 30 多秒。Starlink 目前的工作方式是，数据上传到最近的卫星，然后直接传回相连的地面站。长期计划是允许卫星通过激光链路直接相互通话，跳过地面站。由于光速在真空中比在光缆中更快，完全部署的系统甚至可能比光纤互联网具有更低的延迟，这取决于端点的位置和需要进行多少跳。

我有一个 Starlink 设置，并一直在尝试测试服务。这是我的经验，还有一个额外的奖励。

## 硬件

在盒子里，你可以得到一个路由器，一个 PoE 注射器，一个简单的三脚架，和“Dishy MC flat face”——[一个带有永久连接的 100 英尺以太网电缆的创新卫星碟形天线](https://hackaday.com/2021/01/11/starlink-satellite-dish-x-rayed-to-unlock-rf-magic-inside/)。路由器本身没什么意思，有一个初始设置页面配置 WiFi，没有进一步的配置。然而，令我非常感兴趣的是，路由器报告自己是一个 OpenWRT 设备。拆开箱子是相当痛苦的，因为接缝很紧，夹子有点凹进去。然而，一旦你进入，就有一个可能是串行端口的报头。

PoE 砖很有意思。它有两个输出。一个端口为路由器提供低功率，而另一个端口为圆盘式卫星电视天线提供 1.6 A x 2 的 56 V 电压。对于那些在家跟随的人来说，这比 Cat5e 电缆的功率低 180 瓦。我还没有发现任何其他 PoE 实现推动这么多的电力，所以似乎我们仅限于使用提供的电源进行 Dishy。

![](img/8fb7285519100011ac1922bb4f7662fd.png)

盘子本身是电动的和自动的。没有其他菜肴需要的复杂的手动指点。Dishy 确定它在启动时的位置和方向，并自动指向正确的方向。从那里，相控阵天线控制波束精确瞄准飞过的卫星。

最大的问题是避免障碍。迪希需要一个清晰的天空视野，使用中的 EHF 频率对物理障碍非常敏感。树叶足以完全阻挡信号。因为该系统与不断移动的卫星通信，所以需要清晰的天空窗口相当宽。最近添加了一些优化，以提高对障碍的容错能力，例如当首选端点不可用时，自动故障转移到辅助卫星。该系统最终可能足够强大，可以在有障碍物的情况下正常工作，但目前来说，障碍物仍然意味着服务中断，因此将碟形天线置于开放状态至关重要。

## 真实世界的表现

这不是千兆光纤，但我经常得到 200 Mbps 的下行和 15 Mbps 的上行。Ping 时间足够短，延迟不是一个明显的问题。

这并不是说没有任何问题。有三个主要的烦恼。首先是辍学者。根据内置的统计页面，卫星覆盖的间隙导致了过去 24 小时内 5 分钟的停机时间，另外还有两分钟的杂项停机时间:[两个 9](http://www.leib.be/sascha/2017/07/server-reliability-rule-of-nines/)。

听起来不多，但这些辍学是分散在这里和那里的几秒钟，这是令人恼火的。具有讽刺意味的是，第二个问题是更新。在测试期间，更新会自动安装，从而导致不可预知的连接中断。

最后要提到的是，IPv4 连接是使用电信级 NAT (CGNAT)提供的。我目前被分配了 100.82.35.212，这是专门为 CGNAT 留出的地址空间的一部分。重要的是它不是一个可路由的地址。我想知道 Starlink 是否会在这些地址之间路由，从一个 Starlink 连接到另一个，但在我的测试中，这些数据包被阻止。

> —google.com ping 统计—
> 发送 100 包，接收 100 包，0%丢包，时间 99130 ms
> RTT min/avg/max/mdev = 17.801/27.748/44.228/5.769 ms

尽管如此，随着更多卫星的发射，ping 时间越来越短，中断次数越来越少。一旦测试期结束，固件更新可能会更加可控。虽然 Starlink 不提供可路由的 IPv4，但它会分配一个 IPv6 前缀，如果您有支持它的路由器的话。他们还不支持分发静态 IPv4 地址或 IPv6 前缀，但听起来这是他们计划最终支持的功能。

说到最终支持，你应该知道 Starlink 是地理锁定的。他们把世界分成了大约 15 英里宽的细胞，并且一次一个细胞地开启支持。您在您的家庭地址注册 Starlink，您的 Dishy 被分配到相关的单元。你可以拿起手机并移动，但是如果你走出手机，你的连接将无法工作。目前，只需更改您的服务地址，就能让一切恢复正常。Elon 已经公开承诺要让它完全移动，包括在运动中保持联系。

> 是的，今年晚些时候应该可以完全移动，所以你可以把它移动到任何地方，或者在运动中的房车或卡车上使用。我们需要更多的卫星发射来实现完整的覆盖&一些关键的软件升级。
> 
> —埃隆·马斯克(@埃隆马斯克)[2021 年 4 月 15 日](https://twitter.com/elonmusk/status/1382842277719003136?ref_src=twsrc%5Etfw)