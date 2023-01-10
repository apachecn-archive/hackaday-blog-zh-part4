# 蓝牙唱机为黑胶唱片注入新的活力

> 原文：<https://hackaday.com/2021/11/24/bluetooth-record-player-puts-a-new-spin-on-vinyl/>

你知道，前几天我们刚刚在编剧的地牢里讨论了奇怪和/或过时的音频格式。(对了，你有没有在 DAT 或者 MiniDisc 上买过东西？)尽管黑胶唱片并不奇怪，也不(如今)过时，但事实上[JGJMatt]的这款蓝牙唱片播放器非常现代，这让它变得更加神奇。

[![](img/f3896bdc384eaf5f70ed5a45634019bf.png)](https://hackaday.com/wp-content/uploads/2021/11/bluetooth-record-player.gif) 自从汉堡音响或克罗斯利的半新仿制品问世以来，我们还没有见过这样的便携式设备。但这还不是最值得注意的部分——这东西与普通的唱机相反。翻译:当播放器旋转时，唱片静止不动，它通过蓝牙将音频发送到耳机或扬声器。

这个便携式播放器内部是一个 Arduino Nano，驱动一个带蜗轮箱的 5v 直流电机。这个建筑真的没有太多东西了——主要是电源、一个针筒和一个蓝牙音频发射器。盖子上有一个 TTP223 触摸模块，允许[JGJMatt]挥挥手就可以关闭它。

[JGJMatt]说这是一个原型/正在进行中的工作，并欢迎来自社区的输入。现在，驱动系统很好，蓝牙也很稳定，但 tone arm 还有一些改进的空间——在测试中，它只播放了唱片的一小部分，并在最里面和最外面的部分滑动和滑动。现在，[JGJMatt]正在尝试两部分臂的方法，其中第一个钻头伸出并锁定到位，然后第二个臂从那里伸出并自由移动。

商业电唱机不仅仅可以播放唱片。如果你有一个旧的，甚至不够好到可以在旧货店复制一张星舰唱片，你可以把它变成一个陶轮或者一把吉他颤音。