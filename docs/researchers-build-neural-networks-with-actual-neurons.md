# 研究人员用真实的神经元构建神经网络

> 原文：<https://hackaday.com/2022/03/01/researchers-build-neural-networks-with-actual-neurons/>

在过去十年中，神经网络已经成为一个热门话题，被用于从识别图像内容到生成文本甚至玩视频游戏的工作中。然而，这些人工神经网络本质上只是计算机内的一堆数学，尽管它们有能力做大事，但该技术尚未显示出产生真正智能的能力。

位于澳大利亚墨尔本的 Cortical Labs 有一种不同的方法。他们的工作不是仅仅依靠硅，而是在电极阵列上培养真正的生物神经元，使它们能够与数字系统接口。根据一篇尚未通过同行评审的预印论文，他们的最新工作表明，这些真正的生物神经网络可以进行学习。


## 湿件

![](img/3c6bfa17d6548c83c0b6901881f2d0f8.png)

Scanning electron microscope pictures of neurons grown on a microelectrode array. Credit: Cortical Labs

这项工作的广泛目标是利用生物神经元的计算能力，试图创造“合成生物智能”。总的想法是，生物神经元比任何用软件模拟的神经网络具有更大的复杂性和能力。因此，如果一个人希望从零开始创造一个可行的智能，使用生物神经元比用人类创造的模拟更有意义。

该项目背后的团队研究了从小鼠和人类细胞中生长的神经网络。为此目的，从胚胎中收获小鼠皮质细胞，而在人类细胞的情况下，使用多能干细胞并分化成皮质神经元用于测试目的。这些细胞被接种到来自 [Maxwell Biosystems](https://www.mxwbio.com/technology/?gclid=CjwKCAiA9tyQBhAIEiwA6tdCrMFEK1awdS-XHiO1djSx4txonUvcfCWtkNulrhsGWfIswcX7qNtV-hoCtbcQAvD_BwE) 的高密度多电极阵列上。

一旦在实验室中存放和适当培养，细胞就会在电极阵列表面形成“密集互连的树突网络”。然后通过电极阵列对这些神经元进行电刺激，并依次读取神经元的反应。其结果是一个昵称为 *DishBrain* 的系统，因为它由本质上生活在培养皿中的神经物质组成。

DishBrain 在模拟游戏环境中接受测试，这让人想起了游戏 *Pong* 。生物神经网络(BNN)有一系列基于游戏状态进行刺激的电极，为细胞提供感官输入。然后其他电极被分配来控制游戏中球拍的上下运动。

然后使用各种反馈方法来看看神经网络是否可以被教会智能地控制游戏。最初的想法是基于自由能原理，其中生物系统的目标是采取行动，以维持一个与自身内部模型相匹配的世界状态。因此,“刺激”条件反馈回路被设计成当球拍错过球时提供不可预测的随机反馈，而当球拍正确击中球时提供可预测的反馈。然后将这种方法与无声模式和无反馈模式进行对比，在无声模式中，当球拍击球时刺激被完全切断，在无反馈模式中，相对于游戏状态不提供特殊刺激。休息模式也被用来获得无刺激时活动的基线读数。

![](img/ffcf47b0bdb315191fd61a4c1119ade7.png)

Analysis of data showing the performance of the neural network in various stimulus modes when interacting with a *Pong*-like environment. Credit: Cortical Labs

结果显示，最初，不同模式之间的游戏表现几乎没有差异，刺激条件表现稍差。然而，在最初的五分钟后，统计数据显示，在刺激条件下，神经网络保持了更长的反复击球的反弹，与无声和无反馈模式相比，更不容易错过最初的发球。事实上，刺激条件也是唯一一个随着时间的推移网络表现出改善的条件，这表明了学习效应的证据。相比之下，静音和无反馈模式在整个 20 分钟的测试中保持了相对平稳的性能水平。

这项尚待同行评审的研究在几个领域显示出很大的希望。这不仅证明了我们可以成功地生长神经元细胞并与之接触，还为更好地理解我们的大脑如何在概念和物理层面上工作提供了一个平台。如果结果被证实是有效的，这表明研究小组基本上成功地在缸中培养了一个非常简单的大脑，并训练它控制视频游戏。职业电竞选手要警惕了！(好吧，可能还没有。)

这篇论文有助于密集阅读，但它表明，生物神经元真的有潜力被训练成智能地完成与数字接口一致的任务。虽然现在还为时尚早，但几十年后，你可能会给你的自动驾驶汽车加满一小瓶神经元生长介质，以确保你可以安全地在公路旅行中穿越全国，而不会意外地融入交通。人类只是在学习如何与真正的生物大脑互动，也许在我们成功地从零开始创造自己的大脑之前，我们已经掌握了这一点！