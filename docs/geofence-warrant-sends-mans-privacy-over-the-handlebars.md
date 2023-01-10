# 地理围栏授权发送自行车手的隐私超过车把

> 原文：<https://hackaday.com/2020/03/25/geofence-warrant-sends-mans-privacy-over-the-handlebars/>

大约一年前，扎卡里·麦考伊在佛罗里达州盖恩斯维尔的小区里骑自行车兜风。对他来说，这可能已经被遗忘了，但对历史来说却不是。因为麦考伊使用了一个应用程序来跟踪他的里程数，这条路线被永远铭刻在谷歌诗句中，并附在他的名字上。

在这次倒霉的骑车旅行的那天，麦考伊三次路过某个邻居的房子。虽然这通常不会引起恐慌，但这位邻居碰巧是那天一起盗窃案的受害者，价值数千美元的珠宝被盗。经过四天的调查，盖恩斯维尔警方没有任何线索，所以他们去县里申请地理围栏许可。多亏了 McCoy 自愿提供的所有位置数据，他成了头号嫌疑犯。

[![](img/986134e29ec9bf341b8ff35c6f1f4277.png)](https://hackaday.com/wp-content/uploads/2020/03/google-geofencing.png)

A generic geofence via [Google](https://developers.google.com/location-context/geofencing)

## 在地理围栏内骑自行车

麦考伊对此一无所知，直到骑车十个月后，他收到了谷歌发来的一封含糊不清的电子邮件。该邮件称，警方希望获得他的所有账户信息，谷歌将把这些信息交给警方，除非他放下一切，找到律师，并在接下来的七天内在法庭上成功阻止这些信息。

邮件中唯一的线索是一个案件编号，这让他找到了盖恩斯维尔警察局网站上的盗窃报告。不知道该怎么办，他向父母求助，父母用他们储蓄账户里的钱请了一名律师。这位律师很快发现，McCoy 之所以成为目标，是因为地理围栏搜查令，该搜查令允许执法部门搜索[谷歌庞大的 Sensorvault 档案库](https://www.eff.org/deeplinks/2019/04/googles-sensorvault-can-tell-police-where-youve-been)中在特定时间范围内在特定区域活动的所有移动设备的列表。这是无辜的反义词，直到被证明有罪，你可以想象，它指向许多无辜的人。

在这种情况下，唯一留下的隐私碎片是麦考伊将保持匿名，直到七天时间过去。幸运的是，麦考伊的律师能够在没有向警方透露的情况下澄清他的名字，尽管他们现在肯定知道这个案件已经成为全国新闻。怎么会？律师提交了一份动议，宣布地理围栏搜查令无效，这使得警方退缩了。州检察官办公室告诉麦考伊的律师，他们发现了导致他们远离他的客户的细节，他们只是撤销了搜查令。

[![](img/80a7c784b38d707e0b503b51cc96bd4e.png)](https://xkcd.com/501/)

There’s almost always a [relevant xkcd](https://xkcd.com/501/).

## EULA 文字墙是隐私监狱

像数百万人一样，扎卡里·麦考伊为了方便自愿牺牲了隐私。我们更多头发斑白的读者可能会失望地得知，麦考伊并没有通读那些长篇小说般的最终用户许可协议，也没有意识到他是在允许谷歌通过打开他的位置来记录他去过的所有地方。尽管最终是谷歌让他不得不聘请律师，但在这个特殊的等式中，他们可能不是唯一的坏人。

麦科伊用于跟踪他的自行车骑行的应用程序 RunKeeper 于 2008 年推出，几乎与 Android 手机本身一样长。2016 年，[拥有该应用的公司在欧洲陷入法律纠纷](https://www.androidauthority.com/runkeeper-user-location-tracking-data-advertisers-692346/),因为 RunKeeper 不仅在用户不使用时继续跟踪用户，还将用户位置数据发送给一家美国广告商。

这是老生常谈了，但值得重复:没有什么是免费的，除了你母亲的爱。如果你没有成本，那么你就是产品。仔细考虑你要加入什么，尽可能选择退出。