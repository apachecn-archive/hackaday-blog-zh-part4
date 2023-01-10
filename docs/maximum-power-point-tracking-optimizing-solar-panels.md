# 最大功率点跟踪:优化太阳能电池板

> 原文：<https://hackaday.com/2022/08/03/maximum-power-point-tracking-optimizing-solar-panels/>

当考虑将光伏太阳能电池板集成到一个项目中时，天真的假设是，你只需将电池板指向太阳所在的大致方向，就会产生大量清洁的 DC 电力，随时可以用于给电池充电。在某种程度上，这种假设是正确的，但将太阳能电池板的输出输入到常规的老式 PWM 降压或升压调节器中，不太可能接近电池板的全部规格。

这里的关键词是‘最大功率点’(MPP)，指的是太阳能电池板的 [I-V 曲线](https://en.wikipedia.org/wiki/Current%E2%80%93voltage_characteristic)上的最佳点。这一特性不仅对光伏发电很重要，对风力涡轮机和其他高度可变的能源也很重要。这种最大功率点的跟踪通常被称为“T2”MPPT“T3”，但在这个缩写词中涵盖了许多不同的算法，每种算法都有自己的优点和缺点。在这篇文章中，我们将看看这些 MPPT 算法是什么，当你想选择一个特定的。

## 强大的曲线

太阳能电池规格通常引用开路电压和短路电流。在这两个极端之间，太阳能电池能产生的电压取决于它能产生多少电流。随着电流的增加，它能产生的电压降低。

想象一下软管末端的喷嘴——水流越多，出口处产生的压力越小。如果你让它大开着，你会得到最大的流量，但它会溅到你的脚上。如果你把喷嘴关小一点，流出的水就会少一些，但是会飞得更远。

功率是电压和电流的乘积，P = I * V，这才是我们关心的。在规范中，I 或 V 中的一个为零，因此不产生功率。在这两种情况之间，对于给定的照明有一个最大功率。

[![PV solar panel I-V curves example.](img/7595c60430a780584d843f3415e203bb.png)](https://hackaday.com/wp-content/uploads/2022/07/Solar-Cell-IV-curve-with-MPP.png)

PV solar panel I-V curves example. The single vertical line tracks the MPP.

功率点跟踪器的目标是阻止电流流出太阳能电池，使其在中间电流和电压下运行，最大化其输出:打开阀门，使水尽可能快地推动水轮。

正是这种简单性也隐藏了 MPPT 的复杂性:在光伏太阳能电池板的情况下，由于经过的云层、太阳角度的变化和许多其他因素，它的 MPP 将随着太阳辐射的变化而不断变化。这意味着 MPP 必须不断更新，也就是说要确定欠冲或过冲最小的最佳电压。多年来，已经开发了许多不同的方法来解决这个问题。

虽然存在一些变体和自定义 MPPT 算法，但以下是最流行的算法。

## 恒定电压

[![A generic CN3722 constant voltage MPPT board.](img/39f0da8543412e3d288eb9e6585b5afc.png)](https://hackaday.com/wp-content/uploads/2022/07/cn3722_breakout.jpg)

A generic CN3722 constant voltage MPPT board.

恒压(CV)跟踪是最早也是最基本的 MPPT 算法之一，它通过改变输出电流来保持恒定的基准电压。这种方法使用一个设定的开路电压分数，通常在 80%左右，这意味着从技术上讲，它根本不跟踪 MPP。

由于其简单性，它仍然是一种有用的方法，但它的效率较低，并且在太阳能电池板位置不佳并且看不到充足阳光的情况下会受到影响。低要求使其成为低成本单芯片解决方案的理想目标，如 concerce-Elec 无处不在的 MPPT IC，如 [CN3722](http://www.consonance-elec.com/en/85.html) 和 [CN3791](http://www.consonance-elec.com/en/72.html) 。

一个基本的 5 A CV MPPT 板可以以各种各样的名义买到，价格通常不到 10 美元。这使得它们非常适合对效率不太重要的爱好和成本敏感的应用，大致近似的 MPP 就足够了。

## 扰乱和观察

这种 MPPT 算法是一种相当直接的真实跟踪算法。顾名思义，这种算法是基于 MPP 电流设定点的轻微微调，测量电流和电压，确定产生的功率是增加还是减少，并相应地重复微调。

虽然即使在这种基本形式下也非常有效，但扰动和观察算法的主要问题是它倾向于围绕 MPP 振荡，这将降低整体效率。

为了让该算法确定是否需要调整 MPP 设定点，它必须改变该设定点，以便它能够以输出功率的形式观察这种改变的效果。虽然这样会跟踪最优的 MPP，但是会不断的围绕它振荡。在这种情况下，使调整步长尽可能小似乎是一种合理的优化，但这会导致系统在快速变化时响应非常缓慢，例如云遮住了光伏电池板。

这种方法是简单的恒压方法和更好的方法之间的一个很好的中间解决方案。

## 增量电导

增量电导测量电流和电压的变化，利用系统的[电导](https://en.wikipedia.org/wiki/Electrical_resistance_and_conductance)(δI/δV)——功率曲线的斜率来预测电压变化的影响。扰动和观察采用固定大小的步长，并测试它们是否在正确的方向上，增量电导根据它与最佳值的距离来修改步长。这样做的效果是，当它已经处于 MPP 时，步长变为零，并简单地停留在那里。

计算斜率——电压和电流变化的比率——比测量电平本身对误差更敏感。因此，虽然增量电导使用了更好的优化策略，但它也有最严格的硬件要求，包括精密元件和可以不断执行所需计算的控制器。对于效率至上、可用预算足以支付额外费用的应用，这是一个不错的选择。

## 仅仅是开始

前面只是关于 MPPT 和三种最常见算法的初级介绍，而[魔鬼在细节中](https://www.hindawi.com/journals/ijp/2016/1728398/)。例如，在这两种优化方法中，如果一只鸟刚好在你扰动设定点或采取电压阶跃时飞过，会发生什么？你可能会错误地认为你所做的改变导致了能力的下降。温度和其他真实世界的条件也起了一定的作用，所以在纸上行得通的在实践中可能行不通——这有助于解释恒压法的持久性。

但是这些都不复杂，你不应该实现你自己的 MPPT 控制器。应用笔记 5324 ( [AN5324](https://www.st.com/resource/en/application_note/an5324-using-the-stm32f334-microcontroller-embedded-high-resolution-timer-to-implement-a-1mhz-llc-topology-digital-mppt-solar-converter-stmicroelectronics.pdf) )中的 STM32F334 微控制器就是一个这样的例子，它详细说明了使用高分辨率定时器和其它外设(如该 MCU 中的 ADC 和嵌入式运算放大器)来实现控制 LLC 开关模式转换器的扰动观察算法所需的软件和电路。

虽然现成的 MPPT 控制器可能是任何项目的最佳选择，但它们也是那些有趣的设备之一，既非常简单，又像你希望的那样复杂，使它们成为一个优秀的业余爱好项目创意。