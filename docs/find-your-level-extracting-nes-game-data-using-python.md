# 找到你的水平——使用 Python 提取 NES 游戏数据

> 原文：<https://hackaday.com/2018/08/01/find-your-level-extracting-nes-game-data-using-python/>

就在今年夏天，任天堂娱乐系统迎来了它的第 35 个发布周年，即使在停产多年后，它仍然在黑客社区中表现强劲。证据一:[马修·厄尔]。在他即将到来的一个项目中，[Matthew]需要获得 NES 经典游戏《超级马里奥兄弟》的背景图像。他决定在提取原始游戏数据后，自己处理渲染，而不是仅仅获得一些现成的渲染图像并将其拼接在一起。

因为没有超级马里奥兄弟的官方源代码，所以[Matthew]使用了一个反汇编版本来开始寻找图像数据。为了避免阅读成千上万行汇编代码，也为了了解执行过程中实际发生了什么，他将游戏的 ROM 数据包装到 py65emu 中，这是一个模仿 6502 的 Python 库，6502 是驱动 nes 的 CPU。通过在模拟器的内存处理程序周围添加一个简单的包装器来跟踪对未初始化数据的读取，[Matthew]设法找到了他需要向解析器例程提供哪些参数来获取图像块数据。在参观了图片处理单元(PPU)及其内存安排后，[Matthew]拥有了创建 Python 脚本所需的一切，该脚本将直接从其 rom 数据中渲染游戏背景。

即使提取 NES 游戏数据不是你的事情，模拟器概念[马修]使用可能仍然值得一读。另一方面，如果你想更深入地了解 NES，你绝对应该看看在 NES 上模拟 SNES 游戏的[，在 NES 上展示。](https://hackaday.com/2018/05/31/reverse-emulating-nes-nintendception/)