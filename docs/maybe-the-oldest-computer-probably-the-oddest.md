# 也许是最古老的电脑，也许是最奇怪的

> 原文：<https://hackaday.com/2019/08/03/maybe-the-oldest-computer-probably-the-oddest/>

【滨田忠雄】供职于更著名的富士通旗下子公司富士通 Tokki。1956 年，富士通决定与 IBM 竞争，并建造了基于继电器的计算机 FACOM128。这台电脑占地 70 平方米，重约 3 吨。到 1959 年，他们已经学到了足够的知识来制作一个经过改进的 FACOM128B 模型。[滨田]的工作是让富士通沼津工厂的这些[怪兽中的一个运转起来](http://www.asahi.com/ajw/articles/AJ201907280007.html)。根据日本计算机博物馆的说法，它可能是 T2 最古老的工作计算机 T3。

计算机中的继电器是由电话交换网络改造而来的。计算机有一个变址寄存器和一个中断。它使用二进制(基数为 5)系统，可以自动检测错误，并通过使用冗余(每个十进制数字占用 7 位)和检查结果与它们的补码(分别计算)来重新计算。

互联网上没有太多关于旧机器的信息，有的往往是日文的。计算机是为速度(相对而言)而制造的，使用异步控制，所以它不必以适合机器最慢部分的速率计时。

一个字是 69 位，尽管这有误导性，因为其中一些专用于自动自检功能。有 180 个单词的通用内存。也有专门的存储纸带、打印机和其他项目的内存库。一个只读存储器保存计算中需要的常用常数。该计算机甚至有一个浮点单元，可以保存 8 个有效数字和一个介于-19 和+19 之间的指数。

FACOM128 系列是一台中继计算机，尽管当时基于电子管的计算机已经出现。然而，早期计算机的经验使富士通确信计算机需要没有错误。当时，继电器比电子管可靠得多，结合自检和自动重新执行，FACOM128 为当时提供了一个非常可靠的计算平台。128B 更快，增加了一些指令，如扩展长度的加法和减法，提供用户定义的常数，也有更好的文档。