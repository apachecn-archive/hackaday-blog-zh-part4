# 逆向工程你自己的蓝牙音频模块

> 原文：<https://hackaday.com/2022/03/26/reverse-engineering-your-own-bluetooth-audio-module/>

曾经有一段时间，我们会将集成电路和其他元件安装在条形板上或定制的 PCB 上，开始我们的电子项目。许多设备仍然是这种情况，但廉价的现成模块被当作一个组件来对待已经变得越来越普遍，而以前它本身就是一个项目。我们很高兴看到[ElectroBoy]的工作，他将两种方法结合起来，通过逆向工程将中国蓝牙音频芯片的引脚与最少的数据手册结合起来，并使[成为他自己的现成蓝牙音频模块](https://hackaday.io/project/184542-i-made-my-own-audio-bluetooth-module)。

JL AC 6939 b 采用 SOIC16 封装，所需元件数量最少。因此，PCB 是一个相对简单的命题，事实上，他在一侧安装了所有器件和走线，另一侧是铜接地层。不过，假设这就是这种电路板的全部功能是很危险的，因为许多工程师都曾试图设计 PCB 天线。我们大胆猜测，这里的天线只是一个波状 PCB 线，而不是一个已知阻抗和带宽的天线，至少它看起来比它复制的走线厚得多。

很可能不值得花那么多钱去做一个现成的模块，但是忽略它就是没有抓住重点。我们制造东西*是因为我们能够*，而不仅仅是*因为我们应该*。