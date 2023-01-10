# 使用 CoopCommand 自动化您的家禽

> 原文：<https://hackaday.com/2021/05/08/automate-your-poultry-with-coopcommand/>

从熟睡的母鸡下取出的新鲜鸡蛋，其味道很难与超市中的同类产品相提并论。拥有一群心满意足的家禽的满足感是有代价的，表现为对家禽健康状况的持续监控和管理。这是一个 [[hms-11]试图用 CoopCommand](https://hackaday.io/project/179275-coopcommand) 解决的问题，CoopCommand 是一个自动监控鸡舍内环境的系统。它控制着一盏灯来抵消冬天时间变短的影响，在冷的时候给他们的水加温，在热的时候有一个风扇来冷却和通风，还有一个摄像头来随时监视他们。

其核心是控制 coop 功能的 ATmega328 和用于网络连接和视觉监控的 ESP32 摄像头板。一个字母数字液晶显示器和一组按钮提供了界面，所有这些都安装在智能 3D 打印外壳中的定制 PCB 上。同时，所有文件[都可以在 GitHub 库](https://github.com/hms-11/CoopCommand)中找到。

就良好的畜牧业而言，机器无法取代人类的照顾和关注，因为家禽饲养者总是需要关注他们的需求。但是像这样的系统可以对它们的福利做出重要贡献，从而提高它们的产蛋能力。