# 用树莓派和收据打印机获得 GitHub 门票 IRL

> 原文：<https://hackaday.com/2022/03/25/get-github-tickets-irl-with-a-raspberry-pi-and-a-receipt-printer/>

热敏收据打印机正在各种项目中寻找出路，远远超出了它们通常所处的销售点环境。虽然我们为黑客们为这些小宝石找到的所有创意和艺术用途喝彩，但这款 GitHub 实体票据打印机肯定是迄今为止最好的用途。

根据[Andrew Schmelyun]的说法，看到热敏打印机上弹出的快餐订单是这个建筑的灵感来源。像他这样维护超过 100 个 GitHub repos，任何一个 bug 报告或功能请求的细节都很容易在[Andrew]以前用来跟踪他的工作的大量便笺中丢失。为了实现这一点，他将一台爱普生热敏打印机与一台 Raspberry Pi Zero W 配合使用，并研究出了使用 PHP 向打印机发送数据的细节。幸运的是，[有一个为那个](https://github.com/mike42/escpos-php)准备的图书馆 GitHub 的美丽。

随着“你好，世界！”有点与众不同的是，[Andrew]将注意力转向了连接 GitHub。他在 GitHub 端设置了一些 webhooks，每当他的一个 repos 上报告了一个问题，他就发送一个 POST 请求。文章通过 ngrok 发送到运行在 Pi 上的 PHP web 服务器，服务器格式化数据并将文本发送到打印机。下面的推文中有一个短视频。

在打印机工作的声音和真正的枯树票之间，现在对安德鲁来说很难错过问题。我们已经看到[热敏打印机被塞进相机](https://hackaday.com/2020/09/27/old-polaroid-gets-a-pi-and-a-printer/)，曾经[发送图片给奶奶](https://hackaday.com/2022/01/21/sending-pics-to-grandma-no-smartphone-needed/)，甚至看着他们[慢慢自杀](https://hackaday.com/2020/10/03/receipt-printers-end-it-all-in-moving-art-piece/)，但是我们要向【安德鲁】致敬，因为他有着扎实的职业道德和使用收据打印机的有趣的新方法。

> 这就是我买收据打印机的原因:
> 
> 每次我的 GitHub 回购获得新的发行，我现在都会在我的办公桌上打印出一张实体票 pic.twitter.com/g6uYtGP9J7🪄
> 
> —安德鲁·施梅云(@ aschmelyun)[2022 年 3 月 24 日](https://twitter.com/aschmelyun/status/1506960015063625733?ref_src=twsrc%5Etfw)