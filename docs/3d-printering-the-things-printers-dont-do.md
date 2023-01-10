# 3D 打印:打印机(不)做的事情

> 原文：<https://hackaday.com/2020/11/16/3d-printering-the-things-printers-dont-do/>

3D 打印机是令人惊叹的东西，但如果一个人仅仅根据网上展示的成功来判断，它看起来似乎一切皆有可能。然而在许多方面，3D 打印机实际上相当有限。因为成功看起来很容易，没有人展示失败，人们最终会对现实产生片面的想法。这并不奇怪；在每一个推动技术边界的闪亮 3D 打印背后，都有印刷错误和测试样品堆积在看不见的地方。

![](img/b299a0764a6d7cf290ae0074f5d9d732.png)

如果你曾经考虑过进入 3D 打印，或者想知道什么样的期望是现实的，请继续阅读，因为我将解释物体来自哪里，以及如何识别某种东西是否适合 3D 打印。重要的是要了解打印机有局限性，并了解这些局限性是什么。结果将是更好地理解他们能做什么，以及他们能可靠地解决什么问题。

## 3D 打印机有局限性

我最近和一个想知道 3D 打印机是否能帮助解决他们遇到的问题的人聊了聊。当我听他们描述他们的需求时，我意识到我已经听过很多次了。

理论上，我的同事对打印机能做什么有一个相当好的想法。但是他们对打印机做什么不做什么知之甚少，这种脱节让他们在实际应用中有点不知所措。为了帮助解决这一差距，这里有一些技巧，可以让任何人对 3D 打印机做得*不好*的事情有一个工作理解。

## 他们不会毫不费力地创建对象

修理家庭用品是一个常见的用例，但 3D 打印机不像复印机一样处理物品，也不会神奇地替换丢失或损坏的东西。目前还没有实用的方法来拍摄一些损坏零件的照片并让人打印一张新的，也没有快速简单的方法来制作现有对象的副本。

理想情况下，如果有人需要更换零件来修理家用物品，这个过程将从通过制造商和型号在线查找零件开始。然后，用户可以下载丢失或损坏零件的 3D 模型，并按下按钮打印出替代品。我们还没到那一步。网上有大量的 3D 模型，但我们远没有可供用户使用的制造产品零件库可供下载和打印。

3D 打印机只能从 3D 模型中创建对象，而 3D 模型是由使用 CAD 程序的人制作的。首先需要创建 3D 模型，因为没有模型，3D 打印机就毫无用处。

## 制造一件东西意味着 CAD 工作

如果对象尚未作为 3D 模型存在，则必须创建一个。幸运的是，互联网上已经有了数量惊人的有用的小玩意、工具和小摆设的模型，可以从诸如 [Thingiverse](https://www.thingiverse.com/) 、 [PrusaPrinters](https://www.prusaprinters.org/) 、 [MyMiniFactory](https://www.myminifactory.com/) 等地方下载。这些模型已经存在，并且在很大程度上可以进行 3D 打印。

然而，如果一个人需要一个对象来与其他东西交互(例如，一个设备的替换部件)，那么该对象的 3D 模型很可能还不存在。它需要从头开始仔细设计，机械设计的逆向工程是一个除了 CAD 工作之外还需要大量仔细测量和测试的过程。可能需要接近正在修理的东西，以及正在更换的损坏部分。这项工作可能是一个下午的工作，也可能是几天的努力。

3D 扫描技术，如摄影测量，可能是有用的，但扫描只是一个工具，以协助其他设计工作；它还没有消除[选择 CAD 包并开始设计](https://hackaday.com/2019/01/11/ask-hackaday-help-me-pick-a-cad-package/)的需要。[很好地展示了 3D 扫描如何帮助设计过程的一个很好的例子，这个项目通过 3D 打印定制的控制面板来适应复杂的形状](https://hackaday.com/2019/12/26/custom-control-panels-with-photogrammetry/)。

## 有些东西 3D 打印不好

![](img/ac7cb0e3b5172a09de40e0c5fdd0e046.png)

为了可靠地打印，设计 3D 模型时必须考虑到 3D 打印机的优缺点。人们必须始终发挥工具的优势，3D 打印机也不例外。正如台锯不是切割曲线的合适工具一样，一些形状和零件几何形状也不容易 3D 打印。

爱好者最容易接触到的两种 3D 打印是基于细丝的(FDM)和基于树脂的(SLA)。两者都是从一个平坦的构建平台开始，一层一层地构建一个对象，每一层都建立在前一层的基础上。因此，有些东西比其他东西打印起来更容易、更可靠。

没有很多经验怎么知道一个物体会不会给 3D 打印带来麻烦？下面是潜在麻烦特性的简单清单。列表中匹配的项目越多，对象就越有可能遇到挑战。

*   对象是否缺少一个平面作为基础，或者相对于模型的其他部分，它的基础非常小？这种模型通常比那些稳定、平坦的模型打印起来更复杂。
*   这个物体是很大，还是很小？对象尺寸可能是个问题，可能取决于打印机和材料类型。
*   **模型是薄壁还是细节精细？**薄壁往往是薄弱点。
*   模型是否依赖于严格的公差和精确的尺寸？如果是这样的话，可能需要实验才能得到正确的结果。
*   是否有突出的特征没有很好地连接到模型的其余部分？伸出的零件越多，打印的难度就越大。

对于用手工作的人来说，这里有一个既直观又简单的评估方法:用湿沙建造物体是否容易，就像建造沙堡一样？如果是这样的话，那么它可能会很好地进行 3D 打印。

## 3D 打印机很棒，只要你遵守它们的规则

3D 打印机不是每次都能完美运行，也不是以万无一失的方式运行。操作和维护 3D 打印机并不难，但这是一种通过经验获得的技能。不小心使用打印机完全有可能损坏打印机。理想情况下，人们只需按下按钮，然后啜饮一口玛格丽塔酒，直到机器吐出一个完美完成的零件。不幸的是，这并不适用于 3D 打印机，也不适用于其他电动工具。

需要明确的是，3D 打印是过去十年来爱好者遇到的最好的事情之一，受益者不仅限于那些从头开始设计物品的人。例如，为桌面游戏打印微缩模型是一个利基市场，可能是它一手将 SLA 打印爱好者推向了今天的位置。结果，世界各地的黑客都从中获益，使得向工作台添加 SLA 打印机变得前所未有的容易。

成功是伟大的，但知道 3D 打印机擅长什么也很重要。有了对打印机做得不好的更好的了解，一个有思想的黑客不仅可以更好地决定购买 3D 打印机是否是一个好主意，而且还可以更好地知道友好打印的青睐可能值多少啤酒。