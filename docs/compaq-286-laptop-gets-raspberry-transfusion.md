# 康柏 286 笔记本电脑获得树莓输血

> 原文：<https://hackaday.com/2022/04/02/compaq-286-laptop-gets-raspberry-transfusion/>

我们知道，我们知道。你们很多人不喜欢把一台老式电脑(或其他任何东西，就此而言)内部掏空并用现代电子设备替换的项目。但是你真的能看着笨重的[康柏 LTE 286 笔记本电脑(Dmitry Brant)将一个树莓派破解成](https://dmitrybrant.com/2022/02/20/a-retro-laptop-like-no-other)并诚实地说这是一台值得历史保存的机器吗？这款 30 多年前的笔记本电脑拥有 saltine cracker 的所有设计元素和与之匹配的性能。至少现在在引擎盖下有了 Pi，你可以在上面玩一些更新的游戏。

T2 另外，[德米特里]说机器已经损坏到不值得修理的地步了。唯一留在外壳本身之外的库存硬件是键盘，多亏了一个微小的微控制器，他才能让键盘与 USB 通信。目前还不清楚是否有人试图让键盘上方的开关工作，但我们认为将它们连接到 MCU 上的一些备用 GPIO 引脚不会太难，可以增加一点真实性。

机器的下半部分被清理出来，简直就是原来的外壳，这给他足够的空间来放置 Pi 3B 和控制新的 9 英寸 TFT 显示屏的 HDMI 驱动板。说到这一点，新的面板是一个足够接近原来的长宽比匹配，只有小挡板的修改是必要的，以使其适应。现代的液晶显示器比原来的有了很大的改进，但看起来并不太显眼。

虽然康柏内部仍有足够的可用空间，但[Dmitry]已经选择此时不包括板载电池。相反，通过机器侧面的隔板安装 USB 连接器向 Pi 和相关硬件供电。看起来添加对现成 USB 电池组的支持不会太麻烦，[就像我们最近看到的一个设计特别好的复古未来主义折叠 cyberdeck](https://hackaday.com/2022/03/28/retro-portable-computer-packs-printer-for-the-trip/) 一样，但我们远远没有告诉黑客他们应该如何处理他们定制的计算机。