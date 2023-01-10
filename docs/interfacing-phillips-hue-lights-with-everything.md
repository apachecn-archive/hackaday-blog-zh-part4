# 将飞利浦色调灯与所有产品连接起来

> 原文：<https://hackaday.com/2018/12/10/interfacing-phillips-hue-lights-with-everything/>

物联网正在活生生地吞噬世界，我们再也买不到白炽灯泡了。这意味着互联网现在就在灯泡里，随之而来的是一些特殊的力量。你可以通过僵尸网络打开和关闭灯。你可以改变颜色。这是飞利浦 Hue 系统的想法，在喜欢把灯放在互联网上的人当中很受尊重。还有其他品牌——你可以制作自己的品牌——但是色调系统确实非常好用。

正是这一点让 Marius 发明了软件，将各种电子设备与色调系统连接起来。这是一个名为 [diyHue](https://github.com/diyhue/diyHue) 的项目，已经有一个充满活力的开发者社区在创造他们自己的智能灯，并将它们连接到互联网上。

这个项目的软件是用 Python 编写的，设计成在某些单板计算机上运行。这允许 SBC 连接到 Hue 桥，以便可以控制 Hue 灯泡，连接到 MiLight hub，以便可以控制 MiLight 灯泡，或者通过添加 ZigBee 无线电，可以控制所有这些 ZigBee 设备。现在唯一不能用的是 Google Home，因为它需要一个远程 API，Hue 应用程序的 Home & Away 功能(还是远程 API)，以及 Eneco Toon。

这款软件可以与很多设备配合使用，如果你正在构建联网的家庭照明解决方案，这是你需要检验的一款软件。感谢[cheesemarathon]让我们关注此事。他也非常喜欢它，现在正在为 GitHub 做贡献。非常酷。