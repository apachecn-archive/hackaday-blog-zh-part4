# 一个黑客的战斗，以轻微改善虐待狂索尼耳机

> 原文：<https://hackaday.com/2022/12/27/one-hackers-battle-to-slightly-improve-a-sadistic-sony-headset/>

有一件事你不会在昂贵的索尼 WH 评论中读到——1000 xm3 耳机——如果你选择了它们，你会发现自己处于一种单方面的虐待关系中。按下按钮或低电量通知会让耳机对着你尖叫，忽略你当前正在听的实际音量。一旦它们被放电，它们会突然发出很大的噪音，告诉你电池电量如何不足，然后关机。哦，你不能在充电时使用它们——如果你的语音通话时间比预期的长，你可能会发现自己被大声喊叫，被迫摸索着电线，默默地请求通话参与者等待你换上不同的耳机。

决定挖掘一下，想办法至少解决一些缺点。自然，“使用时不充电”的限制看起来像是唾手可得的果实，也是一个巨大的可用性改进——另外，他怀疑切断充电是为了掩盖这些耳机上已经大量存在的噪音问题。一番痛苦的拆解之后，[他正在检查充电器 IC](https://twitter.com/MisterHW/status/1348591466160025602) ，MP2625，负责电源管理。它的信号通过过孔-in-pad 连接到 MCU，一些焊盘必须被切成两半以断开过孔。

然而，费力的焊盘切割和随后的小心焊接并没有取得成果。即使对输出抑制引脚进行外部控制，[关断仍会继续](https://twitter.com/MisterHW/status/1602008637148389376)–某些因素会影响电路，无论是 VBUS 检测、充电器上其他未被注意到的过孔连接引脚，还是 D+/D-上的检测。即将耗尽这个模块的生命力，[MisterHW]增加了一个 Qi 充电电路，为与 MP2625 并联的 TP4056 供电。被称为 HW-1000XM3 的 mod 使这些耳机更加可靠，不那么烦人——充电器和 MCU 都不知道。

现在，给这些耳机充电只需要在它们上面贴上一个磁性充电器线圈，它不会像尖叫和强制关机那样干扰语音通话。希望索尼最终学会通过让人们使用耳机来测试他们的耳机——毕竟，这远不是这一系列产品的唯一抱怨。我们也希望语音通知最终会被征服——今年夏天，我们已经看到一个黑客[固件修改了一个蓝牙扬声器](https://hackaday.com/2022/06/13/bluetooth-speaker-domesticated-through-firmware-mod/),使声音变得更加悦耳。如果你的耳机是基于一个相对受欢迎的模块，重新利用它们[可能会比这更容易！](https://hackaday.com/2017/01/30/reprogramming-bluetooth-headphones-for-great-justice/)

> 介绍 Sonγ HW-1000XM3！
> 
> –mag safe 充电器支持
> –在(！电话会议
> ——通常的 USB-C 充电关闭电话会议【https://t.co/eqc4xv6lk6T2[pic.twitter.com/U92b7T3LJO](https://t.co/U92b7T3LJO)
> 
> -本周末伍斯特(@ mish)[12 月 12 日，2022 年](https://twitter.com/MisterHW/status/1602110057516343296?ref_src=twsrc%5Etfw)