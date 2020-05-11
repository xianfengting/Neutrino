# Forge是什么

本教程是一个基于Forge的Mod开发教程，那么自然而然的要回答一个问题：「Forge是什么？」

乍一看，这个好像根本就不是一个问题，「Forge？Forge不就是Forge吗？」看到这个问题的你内心中的第一个浮现出的想法估计就是这个。

但是回答这个问题还是非常有必要的，接下去我会稍微讲一讲Forge是什么，以及Forge的历史。这些看上去和我们教程无关的内容，其实是Mod开发领域的「乡谣（Lore）」，比如srg名和notch名是什么，mcp又是什么？

首先我们得从Minecraft本身说起，首先我们得明确Minecraft是一个用Java写成的商业软件。这意味着两件事：Minecraft相对容易被修改，代码本身是不开源而且是被混淆过的。因为长时间Mojang都没有给Minecraft提供官方API[^1]，所以「Mod Coder Pack」项目诞生了（以下简称为MCP）。

还记得我之前说过的，Minecraft的两个特性吗？MCP就利用这两个特性，实现了一套工具，可以让开发者可以直接修改Minecraft jar包里的内容。

于是srg名，notch名和mcp名称诞生了。

那么这三个是什么呢？

首先是`notch名`，他是Minecraft直接反编译得到的混淆之后的名称，通常是无意义的字母数字组合。你从名称Notch就可以看出，这个名字是直接来自Minecraft（~~以及对Notch的怨念~~），举例来说 `j`就是一个典型的`notch名`。

接下来是`srg名`，这个名字是和`notch名`是一一对应的，`srg名`在一个版本里是不会变动的，之所以叫做`srg名`，是为了纪念MCP项目开发的领导者Searge。在srg名阶段，Minecraft中的类名已经是可读了，变量方法等名称虽然还是不可读，但是有相对应的前缀和尾缀来区分了。以上面的`j`为例，它的srg名是`func_70114_g`。

最后是`mcp名`，这个名称也是我们mod开发中接触最多的名称，在`mcp名`阶段，代码已经是可读的了。和我们正常写Java程序中的名称没什么两样。但是`mcp名`是会变动的。举例来说上面的`func_70114_g`它的`mcp名`是`getCollisionBox`。`mcp名`中的类名和`srg名`中的类名是相同的。

接下来我们来讲Forge，随着时间的发展，Mod开发者们意识到，直接修改Jar文件写mod的方式太过于粗暴了，而且Mod和Mod之间的兼容性可以说基本没有，Mod开发者们急需一种工具可以方便地开发Mod，而且能保证mod和mod之间的兼容性，于是Forge就诞生了。

Forge其实就是一套通过修改Minecraft方式实现的第三方API，而且随着时间的发展，MCP现在已经死亡了，除了Forge这套API，Fabric也风头正盛，而Forge本身也在Minecraft 1.13版本到来之后经历了一次重写，引入了大量函数式编程的API。

那么我们上面提及的三个名字在Forge中是怎么使用的呢？

在你安装完Forge之后，游戏的运行过程中，所有的内容都会以`srg名`运行，你编译好的mod同样也会被混淆成`srg名`，保证它可以正常运行。

---

[^1]: API 即 「Application programming interface（应用程序接口）」，是程序的提供的一种机制允许第三方修改或者添加功能。
