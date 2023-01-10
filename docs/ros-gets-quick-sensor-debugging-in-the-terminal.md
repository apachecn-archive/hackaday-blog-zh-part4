# ROS 在终端中获得快速传感器调试

> 原文：<https://hackaday.com/2019/03/31/ros-gets-quick-sensor-debugging-in-the-terminal/>

传感器在机器人技术中至关重要。机器人依靠它的传感器组件来执行它的编程任务。如果传感器损坏或不起作用，机器人的表现可能无法预测，甚至完全失败。[Dheera Venkatraman]一直致力于通过机器人操作系统的 rosshow 软件包使调试传感器问题变得更加容易。

通常情况下，如果你想确定一个摄像头在机器人上工作，通常你必须连接一个显示器和其他外围设备，手动检查，然后当你完成后再把所有东西放好。[Dheera]认为这对于基本的传感器检查来说太痛苦了。

相反，rosshow 使用 SSH 的力量来加速事情的进展。登录机器人，发出一些命令行指令，rosshow 将开始在你的远程机器的终端上显示传感器数据。这是通过在终端中使用 Unicode 盲文实现的。当然，你不会从你的高清相机得到全分辨率的反馈，激光扫描仪的显示也不完全完美。但它足以提供传感器连接和工作的即时验证，并将这些常规连接检查的速度提高一个数量级。

如果你正在考虑下一个构建的软件平台，机器人操作系统是一个特别有用的平台。如果你确实把一些东西放在一起，[一定要让我们知道。](http://hackaday.com/submit-a-tip)