# 简单的传感器为 VR 手提供详细的动作捕捉

> 原文：<https://hackaday.com/2019/03/14/simple-sensor-provides-detailed-motion-capture-for-vr-hands/>

考虑你手臂末端的附件的复杂性。人类的手包含了身体全部骨骼的四分之一以上，使用手本身和延伸到前臂的几十块肌肉，并且能够做出几乎无限变化的动作。它们是精致的机器。

然而，当涉及到虚拟现实时，大多数模拟将手视为无活性的斑点。这可能部分是由于它们的复杂性；从如此多的关节进行运动捕捉可能在计算上具有挑战性。但是[这个压力感应手部动作捕捉装置](https://hackaday.io/project/164152-pressure-sensitive-virtual-reality-controller)旨在改变这种情况。这是[Leslie]、[Hunter]和[Matthew]的一个本科项目的产品，其想法是为虚拟现实模拟器提供一种经济有效的捕捉手势的方法，虚拟现实模拟器通常专注于捕捉全身的大运动。

该传感器由聚氨酯泡沫夹层构成，其中嵌入了应变计传感器。用户将他或她的手滑入泡沫中，并将手指放在传感器上。10 行 20 行的代码将三明治中的手指运动转化为操纵杆运动的 5 个轴，然后发送到虚幻引擎，在那里手指运动被转化为手的 3D 模型，以玩“石头、剪子、布”的虚拟现实游戏。

[莱斯利]和她的同事们在这方面有一条路要走；测试人员抱怨说，平手姿势不自然，泡沫很快使东西变热。也许类似于这些捕捉手势的手套的东西会更有用？