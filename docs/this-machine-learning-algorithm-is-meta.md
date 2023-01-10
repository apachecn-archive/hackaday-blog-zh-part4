# 这个机器学习算法是元的

> 原文：<https://hackaday.com/2019/09/03/this-machine-learning-algorithm-is-meta/>

假设你运行一个网站，每天发布许多关于不同主题的文章，都遵循一个总的主题。假设你的网站允许评论区讨论这些话题。除非你是一个全新的互联网用户，否则你也会认为评论区至少需要一点节制来过滤掉垃圾邮件、跑题甚至是有害的评论。如果你不想雇用任何人来完成这项任务，[你可以尝试这个机器学习算法来代替](https://ladvien.com/deep-learning-natural-language-processing-toxic-comment-detector/)。

[Ladvien]概述了如何建立一个卷积神经网络(CNN ),它可以被编程来做许多事情,但这个可以抓取网页，收集数据，并根据数据做出决定。在这种情况下，任务是识别有毒的评论，但目标不是获得评论版主军械库中最锋利的剑，而是了解更多关于 CNN 如何工作的信息。

该过程用 Python 编写，概述了代码本身及其行为，建立了一个小型服务器来托管神经网络，并最终创建了 webservice。与任何机器学习一样，你需要一个可靠的数据集来用于训练，这个数据集来自维基百科上之前被人类标记的评论。当这个例子聚焦于公然的侮辱和粗俗时，细微的差别被抛到了一边。

虽然[Ladvien]指出他的指南并不全面，而是填补了他在其他指南中注意到的一些空白，但我们认为这是一个有趣的阅读。他还提到，从理论上讲，这个工具可以用来根据文章中的语言来预测一篇文章之后的评论数量。我们可能会暂时把它作为一个学术练习。