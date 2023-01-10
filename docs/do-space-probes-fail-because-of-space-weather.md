# 太空探测器会因为太空天气而失败吗？

> 原文：<https://hackaday.com/2018/09/11/do-space-probes-fail-because-of-space-weather/>

在过去的几十年里，无数被发送到太阳系偏远地区的太空探测器都陷入了沉寂。这些失败不是由于通讯问题，探测器飞入科学上难以置信的异常，或者小绿人抢夺我们发送到太阳系的机器人侦察兵。不，这些太空探测器失败了，仅仅是因为地球上的工程师们不能瞄准它们。如果你失去了姿态控制，你就失去了将发射器指向地球的能力。如果你正在管理一架太空望远镜，失去指向宇宙飞船的能力会让一件有价值的科学设备变成一堆毫无价值的旋转垃圾。

这些失败的原因很难确定，但现在有些人有了主意。开普勒、黎明、隼鸟和 FUSE 空间探测器的失败是由于航天器中反应轮的故障。这些失败，反过来，是由太空天气造成的。具体来说，来自太阳的日冕物质抛射。这项研究是如何产生的，它对未来的深空任务意味着什么？

## 什么是反作用轮？

反作用轮对任何太空任务都很重要:它是几乎所有太空探测器用来确定自身方位的主要方法。这是太空望远镜指向恒星的方式，也是火星着陆器在重返大气层前确保隔热罩指向大气层的方式。但是它是怎么做到的呢？

[![](img/9cb7832db51ace242a913aa908bb4333.png)](https://hackaday.com/wp-content/uploads/2018/09/reactionwheel.png)

A reaction wheel assembly. Inside, there’s a motor, a flywheel, and not much else.

反作用轮实际上只是一个飞轮——一个沉重的旋转圆盘——通常以每分钟几百到几千转的速度旋转。这个飞轮储存角动量，改变这个转速会在飞轮的轴周围产生一点点扭矩。可以把它想象成一个非常高级的版本[臭名昭著的物理实验简介](https://www.youtube.com/watch?v=WWp5NmL16Qc)，一名志愿者坐在一把旋转的椅子上，手里拿着一个旋转的自行车车轮。自行车车轮储存角动量，通过倾斜车轮，志愿者可以在他们的椅子上旋转。不，这不是反作用轮的完美代表，因为卫星中的飞轮不会倾斜，但想法是一样的:控制飞轮意味着你可以旋转。在微重力环境下在卫星上做，你可以旋转整个航天器。

当然，反作用轮并不是航天器自我定位的唯一方式。在低地球轨道飞行的卫星(或任何磁层，真的)，可以使用磁力矩器，或长电磁铁，在磁场中确定自己的方向。事实上，几所大学的立方体卫星使用磁力矩器来满足它们所有的姿态控制要求。但是磁力矩器不能在磁层之外工作，在深空中，空间探测器也将使用推进器和反作用轮。使用两种姿态控制方法对于任何深空任务都是必要的。不仅一种方法会失败，反作用轮也会变得“过饱和”，或者使飞轮在其轴承极限处旋转。如果发生这种情况，飞轮将需要自旋，这意味着推进器必须提供一个相反的扭矩，以防止航天器失去控制。

尽管有这些限制，反作用轮确实是定向小型航天器的最佳方式。它们只需要电力来维持运转，这要归功于太阳能电池板。使用推进器作为唯一的定向手段使用了宝贵的燃料，无论如何，这些燃料最好用在传感器和实验上。

## 反作用轮故障

几乎每个航天器上都有反作用轮，在过去的几十年里，出现了一些值得注意的故障。在 1997 年的一次维修任务挽救了哈勃太空望远镜之前，哈勃太空望远镜的多个反应轮都出现了故障。这是至关重要的，因为没有一整套反应轮，哈勃不能指向任何东西；一个令人印象深刻的失败的望远镜。在执行维修任务之前，[通过使用剩余的两个反作用轮和磁力矩器，问题在一定程度上得到解决。随着反应轮的更换，哈勃愉快地继续探索宇宙。](https://ntrs.nasa.gov/archive/nasa/casi.ntrs.nasa.gov/20080023343.pdf)

[![](img/0303183b1c49078555dd9ff933153653.png)](https://hackaday.com/wp-content/uploads/2018/09/dawn.jpg)

The Dawn mission to Vesta and Ceres suffered numerous failures of reaction wheels

在地球轨道之外，太空中的反作用轮已经出现过无数次故障。飞往灶神星和谷神星的黎明号任务仍在继续，但是当这个太空探测器在灶神星的轨道上时，它的反应轮发生了故障。失败的原因是轴承的过度摩擦，虽然工程师们设法让黎明号到达谷神星，但这并不容易。剩余的反应轮和离子引擎的组合确实让黎明号前往谷神星，但它甚至无法在主天线指向地球的情况下做到这一点。

2005 年夏天，隼鸟号宇宙飞船正在向一颗名为丝川的小行星巡航，这时控制其 X 轴的反作用轮发生了故障。由于隼鸟号有多余的反作用轮，飞行任务继续向小行星前进，直到 2005 年 9 月，它假定围绕其目标小行星的轨道为 7 公里。就在到达这个轨道几天后，第二个反作用轮失灵了，这次是控制 Y 轴。尽管如此，隼鸟号还是在丝川短暂着陆，收集了一个小样本，然后返回地球，发送了一个回收舱在澳大利亚沙漠着陆。

虽然没有发射到深空，但 FUSE 航天器——远紫外线光谱探测器——于 1999 年发射到轨道上，并被设计为光谱远紫外线部分的望远镜。这颗卫星被发射到绕地球 760 公里的轨道上(仍然足够近，以至于在设计中也使用了磁力矩器)。几年后，[四个反作用轮中的两个出现摩擦力突然增大](https://www.nasa.gov/pdf/456672main_PIF_1_miller_fuse_aim.pdf)并停止旋转。工程师们设法更新了软件，以使用剩余的两个轮子和磁力矩器，使任务继续进行了几年，但在 2007 年，最后两个轮子出现故障，结束了任务。

但是，反作用轮在太空中最大的失败可能是开普勒宇宙飞船。这个航天器被设计成位于深空中，观察宇宙中的一个小点，寻找从恒星前面经过的行星。如果有一项任务需要精确的指向和多余的反应轮，那就是开普勒。2009 年启动的行星发现任务最初预计持续到 2016 年。这在 2012 年夏天发生了变化，当时四个反应轮中有一个出现了故障。不到一年后，第二个反应轮出现故障，[导致主要任务](https://www.nasa.gov/feature/ames/kepler/nasa-ends-attempts-to-fully-recover-kepler-spacecraft-potential-new-missions-considered)取消。

虽然黎明号、隼鸟号、聚变号和开普勒号任务被*阿波罗 13-* 级工程英雄救美，但所有这些任务都有另一个共同点。反作用轮都是由伊萨克太空系统公司制造的。听起来像是根本原因分析的好机会，不是吗？

## 查找反作用轮的故障

仅仅是因为它们作为太空探测器的性质，我们可能永远也不会从黎明号或开普勒号上找回反应轮。隼鸟号的反应轮在消失之前是澳大利亚沙漠上空的一层薄雾。那么，我们如何弄清楚这些反应轮是如何失灵的呢？这正是一位研究人员所做的事情，而且证据非常有趣。

这些反作用飞轮的故障可以追溯到一个问题:轴承中的摩擦使这些飞轮每分钟旋转数千圈。当反作用轮内部的电机无法克服轴承的摩擦力时，反作用轮就出现了故障。但是在远离地球数百万英里的深空中，是什么导致了这种情况呢？

事实证明，反作用轮的故障，特别是 FUSE 和开普勒任务中的故障，与空间天气，特别是来自太阳的日冕物质抛射(CMEs)有关。这些 CME 在反作用轮的轴承和轴承座圈上感应出电压，经过测试，这些研究人员发现，从轴承到轴承座圈产生一个小电弧并不需要太多时间。这种电弧会导致一点点点蚀，随着时间的推移，会增加反作用轮上的摩擦力，最终导致其失效。

## 解决轴承摩擦故障

虽然研究人员提供的实验数据显示，轴承可能会由于轴承和座圈之间的电压而发生故障，但我们不太可能证明开普勒、保险丝或黎明因为太空天气而遭受反作用轮故障。为了回收这些太空探测器以检查轴承座圈，我们需要等待脉冲驱动器或太空海盗在打捞任务中的发展。

好消息是，这些反应轮的失败可能已经成为过去。Ithaco Space Systems 的反应轮已经从金属滚珠轴承改为陶瓷轴承，大大降低了轴承座圈产生电弧的可能性。虽然我们可能永远无法确定这些反应轮是否因太空天气而失效，但这个问题，至少在这些 Ithaco 反应轮中，已经解决了。