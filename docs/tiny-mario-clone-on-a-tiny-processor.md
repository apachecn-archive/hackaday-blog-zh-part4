# 微型处理器上的微型马里奥克隆

> 原文：<https://hackaday.com/2020/10/14/tiny-mario-clone-on-a-tiny-processor/>

我们已经习惯了在商品微控制器上运行复古游戏，而以前它们需要当时最先进的控制台硬件。[【邓肯】的马里奥克隆](https://shepherdingelectrons.blogspot.com/2020/01/tinymario.html)将这种风格推进了一点，使用的不是带有大量外设引脚的处理器，而是不起眼的 ATtiny85。它的八个引脚驱动两个有机发光二极管显示器，并接受廉价的类似任天堂控制器的按钮输入。

这份报告被分成软件和硬件两部分，所有的软件本身都可以从 GitHub 库获得。他为显示器的 i2C 提供了令人印象深刻的速度，ATtiny 缺少引脚的问题通过巧妙使用电阻分压器来解决，为每个按下的按钮提供不同的电压。有了电压真值表，他甚至能够检测到多个同时按下的按钮。音乐是通过将声音存储在 EEPROM 中，并以 16 MHz 的时钟频率进行流畅的游戏来利用芯片的有限资源实现的。

整体安装在控制器的外壳内，其 USB 接口被移除，并由智能定制 PCB 取代。地平面填充的意外问题导致了读取按钮的临时障碍，但最终产品是一个非常类似任天堂的体验。我们喜欢它。