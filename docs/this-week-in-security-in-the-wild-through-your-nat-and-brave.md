# 本周安全:在野外，通过你的 NAT，勇敢

> 原文：<https://hackaday.com/2020/11/06/this-week-in-security-in-the-wild-through-your-nat-and-brave/>

本周的大部分报道都是在补丁发布前就被删除的漏洞，其中很多都被利用了。系好安全带！

### Windows 内核加密

第一个是 [CVE-2020-17087，Windows 内核加密驱动](https://bugs.chromium.org/p/project-zero/issues/detail?id=2104)中的一个问题。易受攻击的系统调用可以从非特权用户空间访问，甚至可能从沙盒环境内部访问。由此产生的缓冲区溢出可导致在内核环境中执行任意代码，这意味着这是对受害系统进行根级控制的快速跳转。

这里被攻击的代码缺陷到底是什么？它位于二进制到十六进制转换例程中的一点缓冲区分配逻辑中。该函数接受无符号的短长度参数。该值用于计算输出缓冲区大小，方法是将其乘以 6，并使用一个无符号短整型来保存该值。看到问题了吗？足够大的值将会翻转，而输出缓冲区的大小将会太小。这是导致缓冲区溢出的值溢出。

因为该问题正被积极利用，该报告在发现后仅七天就被公之于众。截至本文撰写之时，该漏洞仍未在 Windows 10 中打补丁。它似乎早在 Windows 7 上就存在了，由于不支持，Windows 7 可能不会得到修复。【编者刻薄注:谢谢，闭源软件。]

### 英特尔密钥提取

几十年来，微码一直是 CPU 架构的一部分。从某种角度来看，处理器总是有某种微码——将指令转换成离散硬件操作的逻辑。正如我们今天所认为的，微码是随奔腾 Pro 一起出现在 x86 处理器上的。有了该处理器，终于可以在启动时更新微码层，修复制造后发现的错误和问题。英特尔一直将微码作为加密的 blob 分发，使研究人员无法调查更新之间的变化。这一限制可能会被解除，因为三名研究人员已经设法从现代英特尔 CPU 中提取出加密密钥。

由于存在允许访问英特尔芯片内部调试接口的漏洞，该提取是可能的。这种技术需要物理接触机器，并且芯片在电源循环时重置到其出厂状态。时间会告诉我们从英特尔处理器的隐藏深处还会挖掘出什么有趣的花絮。关注[芯片红丸库](https://github.com/chip-red-pill?tab=repositories)正在进行的工作。

### 荒野中的神谕

针对 Oracle 产品的两种独立攻击正在被频繁使用。第一个是 Weblogic 中的 CVE-2020-14882，[一个只需要一个 HTTP GET 来触发](https://isc.sans.edu/forums/diary/PATCH+NOW+CVE202014882+Weblogic+Actively+Exploited+Against+Honeypots/26734/)的预授权 RCE。这在最新的安全更新中得到了修补，[很快对](https://testbnull.medium.com/weblogic-rce-by-only-one-get-request-cve-2020-14882-analysis-6e4b09981dbf)进行了逆向工程。(那是用越南语写的。谷歌翻译做得很好，足以跟进。)

第二次攻击是 [CVE-2020-14871，甲骨文 Solaris](https://www.zdnet.com/article/hacker-group-uses-solaris-zero-day-to-breach-corporate-networks/) 中的 PAM 漏洞。这是一个真正的零日，被利用了几个月才在同一套安全更新中修复。火眼公司是最初发现攻击的公司，[，并好心解释它](https://www.fireeye.com/blog/threat-research/2020/11/critical-buffer-overflow-vulnerability-in-solaris-can-allow-remote-takeover.html)。可插拔身份验证模块(PAM)有一个最大响应大小，并使用该大小构建一个缓冲区来保存传入的请求。Solaris 代码无法对请求进行任何检查，如果输入字符串太长，它只是简单地将字符串复制到缓冲区中，超过了末尾。

现在，您认为我们可以在哪里操作 PAM 请求的输入消息？安全外壳守护进程怎么样？是的，在键盘交互模式下发出 SSH 请求，并使用超过 512 个字符的用户名。在一个简单的测试中，PAM 只是崩溃了，但是有可能操纵用户名来危害机器。

这是最坏的情况。Solaris 的 SSHD 守护程序的默认配置容易受到简单的攻击。只需将 SSH 暴露在互联网上，您的机器就可能受到威胁。使用 SSH 密钥并禁用所有其他 SSH 登录方法似乎可以减轻这个漏洞，特别是如果您甚至完全禁用 SSH PAM 的话。OpenIndiana 中也存在此漏洞。2020.10 应该包含修复，但我找不到任何关于之前版本的信息，2020.04 正在打补丁。顾客小心上当。

### 小心 BMC

我一直对基板管理控制器(BMC)持怀疑态度。是的，能够访问远程计算机的 BIOS 界面非常有用。BMC 甚至可以用于远程重装整个操作系统。对于一台被锁在远程数据中心的机器来说，BMC 可以拯救生命。

BMC 也是在您的硬件上运行的第二个操作系统，您无法控制它。我从来都不习惯把那个黑盒操作系统连接到互联网上。我有一对服务器，我在每台服务器上使用了一个辅助以太网端口，从每台服务器交叉连接到另一台服务器的 BMC 端口。我可以 SSH 进入并访问界面，同时保持 BMC 完全隔离。事实证明，[我的偏执是完全有道理的](https://www.securityweek.com/nvidia-patches-ami-bmc-vulnerabilities-impacting-several-major-vendors)。这篇文章是专门针对 NVIDIA SCADA 系统的，但至少其中一些漏洞存在于这个 BMC 系统的其他迭代中。最糟糕的违规者是 CVE 202011483，硬编码凭据。这种类型的错误通常是一个调试帐户，有人在发布固件之前忘记禁用，它仍然是任何运行此 BMC 的系统的主要后门。古老的格言仍然适用:不要把它连接到互联网上！

### 谷歌的 Project Zero 详细介绍了 GitHub 漏洞

Project Zero 公布了 GitHub 的 Actions 系统中一个缺陷的细节。您可能已经与动作进行了交互——当一个项目根据拉请求自动运行一个测试套件，或者将新的错误报告复制到其他存储库时，它就是幕后的动作。[该漏洞是命令注入](https://bugs.chromium.org/p/project-zero/issues/detail?id=2070&can=2&q=&colspec=ID%20Type%20Status%20Priority%20Milestone%20Owner%20Summary&cells=ids)。Project Zero bug 报告指出`set-env`命令是最麻烦的，因为他们的 PoC 包括发送到底层节点服务器的参数，所以我倾向于同意。

这里的政治角度也很有趣。GitHub 在收到报告后的第 103 天的最后一刻要求延长披露时间。在 10 月 1 日的辩护中，GitHub 的确发布了一份公告，披露了除 PoC 代码之外的所有内容。这只是其中一个安全问题，也是一些用户的一个特性。如果您管理一个使用动作的 GitHub 项目，可能值得花一些时间来确保您不会受到命令注入的攻击。

### 通过 NAT 的滑流

不管你喜不喜欢，NAT 已经成为我们网络的一部分很多年了。不管它是否真的是防火墙，我同意罗伯特·格雷厄姆的观点:

> 在所有的安全特性中，每天阻止最多网络攻击/黑客的第一件事是… NAT。
> 
> —robᵉʳᵗ·格拉汉姆😷，挑衅者(@ ErrataRob)[2019 年 5 月 14 日](https://twitter.com/ErrataRob/status/1128091819965931520?ref_src=twsrc%5Etfw)