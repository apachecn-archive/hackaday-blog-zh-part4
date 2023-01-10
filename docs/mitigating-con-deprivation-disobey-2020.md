# 减轻剥夺囚犯:违反 2020

> 原文：<https://hackaday.com/2020/05/17/mitigating-con-deprivation-disobey-2020/>

虽然冠状病毒引发的封锁肯定会让我们当中那些社交焦虑和尴尬的人的生活变得更容易，但它也带走了一种提供归属感和家的感觉的东西:会议。幸运的是，网上有大量过去事件的视频，有助于绕过时间，直到我们再次融入志同道合的人中间。在清单上增加一个选项，一个你可能从未听说过的事件是[违反](https://disobey.fi/)，芬兰的年度安全会议今年早些时候在赫尔辛基举行了第五次，他们最近在他们的 [YouTube 频道](https://www.youtube.com/channel/UCOtuVFYdy-Bu0zQ0rRyhQzg)上发布了[今年会谈的播放列表](https://www.youtube.com/watch?v=OZv5OXN8e0k&list=PLLvAhAn5sGfiZKg9GTUzljNmuRupA8igX)。

今年有不到 1500 名黑客、制造商和一般好奇的人参加，不服从仍然是会议中较小的一方，但它提供了你所期望的一切:讲座、研讨会、CTF 挑战和充满谜题的徽章。它自称为“北欧安全活动”，其主要关注点确实是计算机和网络安全，大多数讲座都是由专业的安全研究人员(通常是红队队员)讲述他们在现实世界中的一些工作。

总的来说，每一个传授新知识、讨论重要问题或仅仅提供思考和新见解的演讲都值得一看，但我们也不想在这里放弃一切。如果你想提前查看更多信息，会议的计划页面提供了所有演讲的一些概要。但是，我们不能只提到一个随机的会议，而不给出至少一些例子，也不提供一些细节，让我们这样做吧。

## 安全和破坏东西

![](img/b81baf3d931a78d36f2fb94f67463740.png)如果你对安全研究人员的工作或这个领域本身不太熟悉，但仍然对它很好奇，或者只是想听听安全实践中混乱的故事，那么[*[Hetti]的*](https://www.youtube.com/watch?v=aw56pHrj4Jk)borkenland 的安全考察对你来说可能是一个很好的起点。对于后者，你应该看看[克里斯·库贝卡]的 [*而不是湍流*](https://www.youtube.com/watch?v=xLKQlAytnAw) ，她谈到了她对波音数字安全状况的研究——假设你还没有对飞行的想法感到不安。

现在，拥有打破事物的许可证，即成为 pentester /安全顾问/白帽黑客，肯定会在这样的会议上引发一些有趣的主题。例如在 [*中，我在你的办公室*](https://www.youtube.com/watch?v=jW5XebI1PMg) 中，安提·维尔塔宁展示了他能够绕过建筑物门禁的十几种不同方法。其中一些看起来非常老套，如果你在另一部电影中看到它们，你只会翻白眼，但事实证明这可能就像好莱坞希望我们相信的那样简单。

一个完全不同的主题是[Chris Hernandez]的 [*用 x86 ISA 特定恶意软件*](https://www.youtube.com/watch?v=mXRWpWzaON4) 破解检测，他的想法是使用不同的 x86 指令集架构版本来防止恶意软件检测。假设检查恶意软件的沙箱或隔离系统使用与目标系统不同的体系结构，使用检测系统不支持的操作码可能会阻止它正确分析恶意代码，并可能让攻击者在目标系统上成功执行它。是的，这里有很多假设，但请记住，这不仅是关于教育，也是关于打破东西的乐趣——也许非法指令崩溃比看起来更重要。

同样值得观看的是由 [PCILeech](https://github.com/ufrisk/pcileech) 和 [MemProcFS](https://github.com/ufrisk/MemProcFS) 的作者【Ulf Frisk】撰写的 [*活内存攻击和取证*](https://www.youtube.com/watch?v=mca3rLsHuTA) 。这些工具和演讲都是关于 DMA over PCIe 攻击的，[Ulf]演示了这种攻击，并且在其他事情中，当他从 Windows 内部破坏 Kali Linux 系统时，使用这种攻击来扭转局面，想想吧！

## 隐私和哲学

当然，没有谈论隐私的安全会议是不完整的。考虑不服从发生在新冠肺炎被宣布为疫情和[追踪应用程序以防止其传播](https://hackaday.com/2020/04/16/google-and-apple-reveal-their-corona-tracing-plans-we-kick-the-tires/)成为谈论的正常事情之前，【Anne Oikarinen】和【Tuisku Sarrala】讨论 [*基于数据生命周期*](https://www.youtube.com/watch?v=MnFez1p_iOA) 的隐私威胁建模似乎在今天更加相关。通过观察数据生命周期的不同方面和阶段，以及由此可能引起的隐私问题，他们的主要信息是针对那些可能没有完全意识到自己的数据观点可能会暴露或危及他人的开发人员。

[Antti Kurittu]在他的 [*范式转变*](https://www.youtube.com/watch?v=GZC7BI3ebmw) 演讲中指出了一个类似的认知偏差:开发人员经常看不到他们是理解计算机实际工作方式的一小撮精通技术的精英中的一员。另一方面，大多数人，也是今天的大多数用户，并不这么认为——他们也没有足够的兴趣。但是这种不匹配导致了臭名昭著的用户错误，并将用户本身变成了一个安全问题。正如[Antti]所说，“如果难以使用，就难以安全使用”，也许是时候我们认真反思用户界面了。

## 主题演讲

当然，指责用户很容易，但这不会解决任何问题，因为[Mikko hypp nen]，芬兰的安全老爹，以及其他许多事情，恶意软件博物馆的馆长，在[*周五的主题演讲*](https://www.youtube.com/watch?v=4YdopejYmck)中的讲话。他从互联网的总体状况开始，讲述了互联网如何像电力一样对社会至关重要，以及从安全角度来看这一发展将会带来的后果。他展示了过去一些高调的个人和场景，将机器学习纳入等式，并形成了他对恶意软件未来的预测。

[Jayson E. Street]周六的主题演讲 是一个完全不同的演讲，如果你必须从《不服从》中选择一个演讲，这应该是最能引起任何现在和未来的黑客以及任何与黑客社区互动的人的共鸣的一个。通过矩阵引用，他提醒我们成为一名黑客的意义，以及它与计算机无关，而是激情和挑战规范，这需要不断的好奇心驱动的学习，前面还有许多失败。

黑客社区是一个多元化的世界，每个人都应该有自己的想法和目标，没有人会对任何事情都有一个正确的答案——这样想实际上是与社区应该代表的完全相反。总之，[Jayson]解决了社区内所有守门人、评判和歧视的问题，并鼓励每个人停止成为自己最大的批评者，只做自己喜欢做的事情，不管其他人会怎么想。

“不服从”的主要组织者[Benjamin srkk]在会议的 [*开场白*](https://www.youtube.com/watch?v=OZv5OXN8e0k) 中传达了类似的信息，最后，这才是会议和他们所针对的社区真正应该做的事情:学习、分享知识、对你喜欢做的事情充满热情，并在一个你可能是第一次有归属感的环境中享受自己。