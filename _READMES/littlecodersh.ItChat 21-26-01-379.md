itchat english version english version itchat是一个开源的微信个人号接口，使用python调用微信从未如此简单。 使用不到三十行的代码，你就可以完成一个能够处理所有信息的微信机器人。 当然，该api的使用远不止一个机器人，更多的功能等着你来发现，比如这些。 该接口与公众号接口itchatmp共享类似的操作方式，学习一次掌握两个工具。 如今微信已经成为了个人社交的很大一部分，希望这个项目能够帮助你扩展你的个人的微信号、方便自己的生活。 安装 可以通过本命令安装itchat： python pip install itchat 简单入门实例 有了itchat，如果你想要给文件传输助手发一条信息，只需要这样： python import itchat itchat auto login itchat send hello filehelper tousername filehelper 如果你想要回复发给自己的文本消息，只需要这样： python import itchat itchat msg register itchat content text def text reply msg return msg text itchat auto login itchat run 一些进阶应用可以在下面的开源机器人的源码和进阶应用中看到，或者你也可以阅览文档。 试一试 这是一个基于这一项目的开源小机器人，百闻不如一见，有兴趣可以尝试一下。 由于好友数量实在增长过快，自动通过好友验证的功能演示暂时关闭。 截屏 进阶应用 特殊的字典使用方式 通过打印itchat的用户以及注册消息的参数，可以发现这些值都是字典。 但实际上itchat精心构造了相应的消息、用户、群聊、公众号类。 其所有的键值都可以通过这一方式访问： python itchat msg register text def msg equals to print msg fromusername print msg fromusername 属性名为键值首字母小写后的内容。 python author itchat search friends nickname littlecoder 0 author send greeting littlecoder 各类型消息的注册 通过如下代码，微信已经可以就日常的各种信息进行获取与回复。 python import itchat time from itchat content import itchat msg register text map card note sharing def text reply msg msg user send s s msg type msg text itchat msg register picture recording attachment video def download files msg msg download msg filename typesymbol picture img video vid get msg type fil return s s typesymbol msg filename itchat msg register friends def add friend msg msg user verify msg user send nice to meet you itchat msg register text isgroupchat true def text reply msg if msg isat msg user send u s\u2005i received s msg actualnickname msg text itchat auto login true itchat run true 命令行二维码 通过以下命令可以在登陆的时候使用命令行显示二维码： python itchat auto login enablecmdqr true 部分系统可能字幅宽度有出入，可以通过将enablecmdqr赋值为特定的倍数进行调整： python 如部分的linux系统，块字符的宽度为一个字符（正常应为两字符），故赋值为2 itchat auto login enablecmdqr 2 默认控制台背景色为暗色（黑色），若背景色为浅色（白色），可以将enablecmdqr赋值为负值： python itchat auto login enablecmdqr 1 退出程序后暂存登陆状态 通过如下命令登陆，即使程序关闭，一定时间内重新开启也可以不用重新扫码。 python itchat auto login hotreload true 用户搜索 使用search friends方法可以搜索用户，有四种搜索方式： 1 仅获取自己的用户信息 2 获取特定username的用户信息 3 获取备注、微信号、昵称中的任何一项等于name键值的用户 4 获取备注、微信号、昵称分别等于相应键值的用户 其中三、四项可以一同使用，下面是示例程序： python 获取自己的用户信息，返回自己的属性字典 itchat search friends 获取特定username的用户信息 itchat search friends username abcdefg1234567 获取任何一项等于name键值的用户 itchat search friends name littlecodersh 获取分别对应相应键值的用户 itchat search friends wechataccount littlecodersh 三、四项功能可以一同使用 itchat search friends name littlecoder机器人 wechataccount littlecodersh 关于公众号、群聊的获取与搜索在文档中有更加详细的介绍。 附件的下载与发送 itchat的附件下载方法存储在msg的text键中。 发送的文件的文件名（图片给出的默认文件名）都存储在msg的filename键中。 下载方法接受一个可用的位置参数（包括文件名），并将文件相应的存储。 python itchat msg register picture recording attachment video def download files msg msg download msg filename itchat send s s img if msg type picture else fil msg filename msg fromusername return s received msg type 如果你不需要下载到本地，仅想要读取二进制串进行进一步处理可以不传入参数，方法将会返回图片的二进制串。 python itchat msg register picture recording attachment video def download files msg with open msg filename wb as f f write msg download 用户多开 使用如下命令可以完成多开的操作： python import itchat newinstance itchat new instance newinstance auto login hotreload true statusstoragedir newinstance pkl newinstance msg register itchat content text def reply msg return msg text newinstance run 退出及登陆完成后调用特定方法 登陆完成后的方法需要赋值在logincallback中。 而退出后的方法需要赋值在exitcallback中。 python import time import itchat def lc print finish login def ec print exit itchat auto login logincallback lc exitcallback ec time sleep 3 itchat logout 若不设置logincallback的值，则将会自动删除二维码图片并清空命令行显示。 常见问题与解答 q 如何通过这个包将自己的微信号变为控制器？ a 有两种方式：发送、接受自己username的消息；发送接收文件传输助手（filehelper）的消息 q 为什么我发送信息的时候部分信息没有成功发出来？ a 有些账号是天生无法给自己的账号发送信息的，建议使用filehelper代替。 作者 littlecoder 构架及维护python2 python3版本。 tempdban 协议、构架及日常维护。 chyroc 完成第一版本的python3构架。 类似项目 youfou wxpy 优秀的api包装和配套插件，微信机器人 优雅的微信个人号api liuwons wxbot 类似的基于python的微信机器人 zixia wechaty 基于javascript es6 的微信个人账号机器人nodejs框架 库 sjdy521 mojo weixin 使用perl语言编写的微信客户端框架，可通过插件提供基于http协议的api接口供其他语言调用 hanson vbot 基于php7的微信个人号机器人，通过实现匿名函数可以方便地实现各种自定义的功能 yaphone itchat4j 用java扩展个人微信号的能力 kanjielu jeeves 使用springboot开发的微信机器人 问题和建议 如果有什么问题或者建议都可以在这个issue和我讨论 或者也可以在gitter上交流： 当然也可以加入我们新建的qq群讨论：549762872 205872856