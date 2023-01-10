# 带有现代技术的巴黎古董地图

> 原文：<https://hackaday.com/2021/04/10/antique-map-of-paris-with-modern-tech/>

有很多人喜欢古董，从汽车、家具到艺术品。虽然这可能有点生存偏见，但很容易欣赏这些更古老的东西的优质材料、工艺，甚至简单。然而，他们错过了我们所有的现代技术，所以对经典作品进行“还原”是当今一项受欢迎的活动。例如，这张古老的巴黎地图是由美丽的硬木制成的，但也被一些现代设施所强化。

起初，这个项目的创造者[Marc]只是想给它一些环境照明，但最终经过两年的发展，它背后隐藏了一系列根据当前太阳和月亮位置照明的 Neopixels。Neopixels 从 ESP8266 获得指令，ESP8266 根据当前日期使用[Marc]自己编写的代码计算这些位置。由于 ESP8266 的局限性，它不是特别精确，但它能很好地完成工作。

为了提高精确度，[Marc]指出，可以使用 ESP32 来代替，但我们现在可以给 ESP8266 一个通行证，因为整个项目是一个优秀的艺术装置，即使它在计算上略有偏差。如果你需要更高的精度来跟踪天体，[你也可以随时抓住一个树莓派](https://hackaday.com/2016/04/14/a-star-tracking-telescope-mount/)。