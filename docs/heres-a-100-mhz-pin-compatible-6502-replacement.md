# 这是一款 100 MHz 引脚兼容的 6502 替代产品

> 原文：<https://hackaday.com/2021/10/15/heres-a-100-mhz-pin-compatible-6502-replacement/>

MOS 技术 6502 CPU 在当时是一个受欢迎的部分。在各种修改版本中，它驱动了从 Commodore 64 到任天堂娱乐系统的所有东西，并出现在一百万个其他应用程序中。一个流行的版本是 65C02，而[Jürgen]决定开发一个引脚兼容的 FPGA 版本[,运行速度高达 100MHz。](http://www.e-basteln.de/computing/65f02/65f02/)

CPU 内核是由[阿莱特·奥滕斯]借用的，并由[埃德·斯皮特斯]和[大卫·班克斯]扩展了 65C02 的功能。[Jürgen]然后将该内核封装在 Spartan-6 FPGA 中，并将其放置在一个小型 PCB 上，该 PCB 的大小与原始 65C02 的 40 引脚双列直插封装相同。

FPGA 设置为以与主机时钟匹配的时序访问外部 CPU 总线。然而，在内部，CPU 内核以 100MHz 的速度运行。它将 RAM 和 ROM 从主机复制到它自己的内部 64kb RAM，减去主机用于内存映射 I/O 的区域。然后，CPU 以 100MHz 的全速运行，除非它需要与这些 I/O 地址通信。

它允许芯片在与无法以接近 100MHz 的速度运行的旧硬件一起使用时，加速大量任务而不会完全失控。pin 兼容设计已经在 Apple II 和 Commodore 8032 以及各种老式国际象棋计算机中成功测试。

我们以前也见过相反的情况，一个真正的 6502 与一个 FPGA [配对，充当计算机的其余部分](https://hackaday.com/2020/11/03/brain-in-a-vat-6502/)。如果你有任何自己的尖端 6502 黑客(不是印刷错误！)，[让我们知道吧！](http://hackaday.com/submit-a-tip)

[感谢大卫·帕默的提示]