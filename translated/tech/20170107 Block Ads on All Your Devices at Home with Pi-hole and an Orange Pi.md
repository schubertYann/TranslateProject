用 Pi-hole 和 Orange Pi 在你所有的设备上阻止广告
============================================================


你是否发现在你的浏览器、智能手机和平板上设置广告拦截器很恼火？ 至少我是这样的。我家里有一些“智能”设备，然而它们似乎没有任何类型的广告拦截软件。 好了，我了解到 [Pi-hole][2] 是一个 pi 上的广告拦截软件，它能在到达你的设备之前阻止所有的广告。它能让你列出任何域的黑名单或白名单，并且它有一个很好的面板，让你深入了解你的家庭网络最常访问的域/网站、最活跃的设备和最常见的广告商。

Pi-hole 的确是针对树莓派上运行的，但我想知道它能否在我运行 Armbian Linux 的廉价 Orange Pi 上运行。 好吧，它绝对可以！下面是我让 Pi-hole 能快速运行的方法。


### 安装 Pi-hole

安装 Pi-hole 是使用终端完成的，所以打开你的 Orange Pi 桌面上的终端或 ssh 到 pi。

你将下载软件，并进入到你选择的目录，确保你有写入权限。像这样：


```
cd <your preferred directory>/
```

我偏离了 Pi-hole 主页上的“一键”安装。 我的意思是，他们说在命令下面说“管道到 bash 可能是危险的”，本地安装是“更安全”。所以，这里是我的本地安装步骤：

```
git clone --depth 1 https://github.com/pi-hole/pi-hole.git Pi-hole
cd Pi-hole/automated\ install/
./basic-install.sh
```

如果你没有以 root 用户身份登录，那么基本安装脚本将提示你输入密码，然后再继续。 如果需要，脚本将下载并安装一些必备的 Linux 软件包。接着它会显示一个红蓝界面，提示你回答有关如何配置 Pi-hole 的几个问题。以我的经验，直接接受默认值就可以了，我后来发现 Pi-hole 的 web 程序可以更改设置，如DNS提供商。

该脚本将告诉你在图形界面和终端中 Pi-hole 的密码。 请记住该密码！

脚本还会告诉你 Pi-hole 的网址，应该像这样：

```
http://<your pi’s IP address>/admin
```

或者类似这样

```
http://orangepipc/admin
```

你需要输入 Pi-hole 密码，接着你会看到像下面这样的漂亮面板：

 ![Ph-hole](https://i1.wp.com/piboards.com/wp-content/uploads/2017/01/ph-hole.png?resize=640%2C532) 

请记住更改家庭网络路由器上的 DNS 设置并使用你 pi 的地址。 否则，广告不会被过滤！

上面的说明与 Pi-hole 网站提供的替代“安全”方法大致相同，尽管 Armbian 没有被列为官方支持的操作系统。我相信这些说明应该在 Raspberry Pi 或其他运行某种形式的基于 Debian 的 Linux 操作系统的 pi 上工作。但是，我并没有测试，我有兴趣听到你的经验（请给我留下简短的评论）。


### 思考和观察

运行 Pi-hole 一段时间后，在 Pi-hole 面板上出现一些学习信息，我发现有比我所知道的更多的网络活动，它们并不是所有我批准的活动。例如，有一些我不知道的关于游戏程序的“有趣”连接从我的孩子的设备上发出，加上社交网络程序显然一直在给我发送骚扰数据。总之，无论是否是良性流量，我很高兴减少了流量负载，即使有点少。。。我的意思是，为什么我应该允许我不想要的或者不关心的应用程序和广告吃掉我的网络流量？好吧，现在他们被封锁了。

像这样为 Orange Pi 设置广告屏蔽很便宜、容易，并有助于在限制一些不必要的流量从我的家庭网络中来回（特别是关于孩子们的）中放松我的大脑。如果你有兴趣，你可以看到我上一篇文章关于如何[轻松设置一个 Orange Pi][3]，并使用下面的链接来查看 Orange Pi 是多么便宜。我相信这是一个值得投资东西。

Amazon 上的 Orange Pi (附属链接):  [Orange Pi PC Single Board Computer Quad Core ARM Cortex-A7 1GB DDR3 4K Decode][4]

[AliExpress 上的Orange Pi 商店][5] (附属连接).

编辑：这篇文章讽刺的是，如果你成功设置了 Pi-hole，这个站点上的链接 (s.click.aliexpress.com) 将被屏蔽，是否加入到白名单取决于你。

--------------------------------------------------------------------------------

via: http://piboards.com/2017/01/07/block-ads-on-all-your-devices-at-home-with-pi-hole-and-an-orange-pi/

作者：[MIKE WILMOTH][a]
译者：[geekpi](https://github.com/geekpi)
校对：[校对者ID](https://github.com/校对者ID)

本文由 [LCTT](https://github.com/LCTT/TranslateProject) 原创编译，[Linux中国](https://linux.cn/) 荣誉推出

[a]:http://piboards.com/author/piguy/
[1]:http://s.click.aliexpress.com/deep_link.htm?aff_short_key=N3VJQBY&dl_target_url=http://best.aliexpress.com
[2]:https://pi-hole.net/
[3]:http://piboards.com/2017/01/04/easy-set-up-orange-pi/
[4]:https://www.amazon.com/gp/product/B018W6OTIM/ref=as_li_tl?ie=UTF8&camp=1789&creative=9325&creativeASIN=B018W6OTIM&linkCode=as2&tag=piboards-20&linkId=ac292a536d58eabf1ee73e2c575e1111
[5]:http://s.click.aliexpress.com/e/bAMVj2R
