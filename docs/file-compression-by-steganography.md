# 基于隐写术的文件压缩

> 原文：<https://hackaday.com/2019/10/19/file-compression-by-steganography/>

在一个存储空间有限而存储空间需求无限的世界里，数据压缩成为一个非常必要的问题。有几种数据压缩算法可能更为人们所熟悉——霍夫曼编码、LZW 压缩——还有一些更为神秘。

【Labunsky】决定利用他的隐写术知识[创造一种完全独特的文件压缩形式](https://medium.com/@labunskya/about-a-strange-data-compression-method-4d0d9d2e5714)，这也许会在其他信息理论家中获得更大的恶名。

隐写术是指将消息或文件隐藏在另一个文件中的方法，来自希腊语 *steganos* 表示“覆盖或隐藏”,而 *graphe* 表示“书写”。这种做法已经存在很久了，从用隐形墨水写字到在月饼里储存信息。使用的方法从在图像中隐藏信息以逃避审查到在文件中隐藏病毒以造成混乱。

![](img/d3664c1cbcc3894261f094130edd0188.png)

100%不【via xkcd】

开发者解释说，由于每个文件都只是一个比特序列，所以观察文件会导致认识到大多数比特在相同的位置上是相等的。对硬盘的某些位置进行修改可以节省存储空间，而不是存储文件的所有位。然而，重要的是要避免有损文件压缩，它会在压缩阶段对质量造成严重破坏。

他们最终实现的[压缩技术](https://github.com/LabunskyA/f5ar)基于 [F5 算法](https://link.springer.com/chapter/10.1007%2F3-540-45496-9_21)，该算法将二进制数据嵌入 JPEG 文件中，以减少内存中的总空间。压缩使用`libjpeg`进行 JPEG 解码和编码，使用`pcre`支持 POSIX 正则表达式，使用`tinydir`进行独立于平台的文件系统遍历。其中一个主要的修改是通过禁用基于密码的置换跨座来节省计算资源，置换跨座在多个文件之间均匀分布数据。

一个警告——即使改变压缩文件的一个比特也可能导致存储的所有数据全部损坏，所以要小心使用！