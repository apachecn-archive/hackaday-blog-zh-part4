# 实用的分立器件 386

> 原文：<https://hackaday.com/2022/11/27/a-practical-discrete-386/>

有一些芯片，无论行业如何远离他们，仍然存在，在他们曾经坐在旁边的范围已经离开大楼几十年后施加控制。这样的芯片是 386，而不是你期待的 80386 微处理器，而是 LM386，一种像方舟一样古老的小型 8 引脚 DIP 音频放大器。386 仍然可以在小型扬声器需要电池供电的地方找到。SolderSmoke listener [Dave]用 LM386 进行了一次有趣的练习，[用分立元件](http://soldersmoke.blogspot.com/2022/11/a-homebrew-lm386-does-anyone-want-to.html)复制它。如果你想要的话，这是一个方便的小型分立音频放大器，但即使你不是每天都与模拟电路打交道，这也是一个理解模拟电路的有趣练习。

LM386 数据手册 (PDF)中可以找到一个基本电路，但像这类事情一样，它包含一些简化。分立电路在偏置配置方面有一些不同，特别是当用晶体管代替一对二极管时，并且为了弥补不在同一芯片上，要求偏置晶体管必须热耦合。这种电路配置曾经很常见，但首先被 LM386 等线性 IC 取代，最近又被基于 IC 的开关放大器取代。因此，看一看它并获得一些理解是有益的。如果你想了解更多，[这是一个我们已经详细介绍过的芯片](https://hackaday.com/2016/12/07/you-can-have-my-lm386s-when-you-pry-them-from-my-cold-dead-hands/)。