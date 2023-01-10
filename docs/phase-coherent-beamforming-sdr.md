# 相位相干波束形成软件无线电

> 原文：<https://hackaday.com/2021/08/04/phase-coherent-beamforming-sdr/>

软件定义无线电技术是舶来品的日子已经一去不复返了，我们一点也不怀念它们。一个恰当的例子是:[laa kso Mikko]研究小组已经使用 21 个廉价的 RTL-SDR 加密狗创建了一个相位相干阵列，建造了一个[多通道接收器](https://aaltodoc.aalto.fi/handle/123456789/102361)。这对于从测向和被动雷达或波束形成的任何事情都是有用的。GitHub 上也有[代码](https://github.com/mlaaks/coherent-rtlsdr)。

相位一致性要求加密狗的调谐器可以关闭抖动。这意味着该代码仅适用于使用 R820T/2 的加密狗。该项目修改了加密狗，以使用一个公共时钟和一个可切换的参考噪声发生器。

一个耦合器可以容纳 7 个加密狗，成本约为 180 美元。该团队使用了多达 5 个这样的接收器来创建 35 个接收器的阵列。这个过程有点数学密集型，而且有些代码是用 Matlab 编写的。

此外，一些论文涉及提高接收器稀疏阵列的性能，以接近全填充阵列的性能。显然，即使价格如此之低，出于成本、空间和功率方面的考虑，也需要更少的接收器。

当然，并不是每个人都需要几十个相位相干接收通道，但如果你需要，最好知道一个便宜的方法。

RTL-SDR 使得许多用传统方式难以完成的项目变得简单。从医疗设备到[卫星](https://hackaday.com/2021/03/11/monitor-spacex-rocket-launches-with-software-defined-radio/)，似乎一个便宜的硬件就能搞定一切。