# 在硬模式下构建 ESP8266 门铃

> 原文：<https://hackaday.com/2019/01/07/building-an-esp8266-doorbell-on-hard-mode/>

这当然看起来似乎是一个足够简单的项目；所有[米格尔·德·安德拉德]想要的是当有人按他的门铃时收到通知，并认为这将是一个很好的项目，让他在 ESP8266 黑客的精彩世界中体验一下。但正如命运安排的那样，并非一切都按计划进行。最终他解决了这个问题，但这是[一个有趣的视角，它展示了即使是“简单”的项目也能把小精灵从藏身处召唤出来。](http://daeconsulting.co.za/2018/12/17/theres-someone-at-the-door/)

可以说，问题始于[米格尔]从当地电子产品零售商那里购买 ESP-01 模块。虽然在实体店购买硬件的便利性不能被夸大，但这确实意味着与更常见的 ESP“开发板”相比，他只能获得稍微更简单的体验。用 Teensy 进行外部编程最终没有造成太大的障碍，但这确实意味着他只能用两个 GPIO 引脚。

无论如何，有了 ESP，下一步就是弄清楚现有的门铃和内部通话系统是如何工作的。不幸的是，经过一些实验后，[米格尔]发现那里发生的事情比他希望的要多一些。根据他的万用表，对讲机的一根线在打开时大约为 5 伏直流电，按下时下降到 2.5 伏直流电。如果这还不够糟糕的话，拿起听筒接听对讲机会将电压传送到一个微控制器，从而切断 12 伏直流电。更复杂的是，对讲机的电源线是 23 伏交流电，所以如果他想避免为 ESP 提供单独的电源，他需要以某种方式进行调整。

[![](img/7cf84e5ff496bf1ab877c80bccbe3b7f.png)](https://hackaday.com/wp-content/uploads/2019/01/espbell_detail.png) 为了将这种杂乱的电压转变为 ESP8266 的干净的 0-3.3V 信号，他想到了一种基于 LM358 比较器的电路，该电路利用 LM117 调节器同时为自身和 ESP 供电。一对二极管用于阻止交流分量引起故障，一个 A2N2222A 晶体管用作缓冲放大器来提升比较器的输出，因此它在 ESP 上记录为数字高电平。电路花了一点时间来整理，但最终[米格尔]说，它似乎完成了工作。

你可能会认为问题已经解决了，但这就是真正令人恼火的地方。这个系统会在一段时间内运行良好，然后莫名其妙地消失。在诊断问题时，他意识到他连接到 GPIO_0 的电路无意中将 ESP8266 置于编程模式，因为除非按下对讲机按钮，否则它会保持引脚为低电平。他认为他可以将电路转移到另一个 GPIO 引脚，但由于那个引脚上有电路板的 LED，这导致了自己的问题。到目前为止，[米格尔]还没有想出解决这个问题的办法，并且已经学会接受这样一个事实，即如果由于任何原因断电，系统将无法干净地恢复。

如果你正在寻找一个稍微更有品位的外观，而不是像口香糖一样粘在墙上的一块纸板，我们也看到了一些更华丽的门铃设置中使用的[esp 8266](https://hackaday.com/2016/10/24/internet-doorbell-gone-full-hipster/)。当然，如果你还没有完全理解联网按钮的事情，[你总是可以从更简单的东西开始。](https://hackaday.com/2018/12/30/pushbutton-%E2%86%92-push-notification/)