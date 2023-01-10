# 编写 Arduino 库，专家观点

> 原文：<https://hackaday.com/2020/02/27/writing-arduino-libraries-an-expert-view/>

Arduino IDE 有点人格分裂。一方面，这是一个简单的环境，你可以挑选几个库，写几行代码，做很多有趣的东西。另一方面，它也是一个生态系统，其中可以支持许多不同的板和库。编写一个每个人都可以轻松使用的伟大的库需要一点预先考虑。有一个官方的风格指南，但是 Sparkfun 的[Nate]最近的一篇文章指出了从编写比大多数人更多的库中学到的经验。

当然，正如你所料，这其中有些是见仁见智的问题，[内特]也承认这一点。例如，他们总是使用 115，200 波特的串行端口，但他们注意到 9，600 波特也很受欢迎。他们还建议让代码尽可能地可读，这通常是个好建议。在过去，编写简洁的代码可能会导致更高的效率，但是使用现代编译器，即使以非常冗长的方式做事，您也应该得到严格的最终结果。

然而，很多建议都很微妙却很重要。比如默认参数的使用和参数的顺序。如果你将他们的建议添加到官方的风格指南中，你将会在创建真正伟大的 Arduino 库的道路上一帆风顺。

当然，你还需要一个关于库的好主意或者一个还不存在的改进库。那可能是你最困难的任务。有时候，[在](https://hackaday.com/2012/10/22/giving-the-arduino-deques-vectors-and-streams-with-the-standard-template-library/)上移植一些东西比从头开始更有意义。