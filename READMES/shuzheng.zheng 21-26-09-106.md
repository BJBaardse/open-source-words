zheng 交流qq群：133107819、284280411、305155242🈵、528049386、157869467🈵、570766789🈵、601147566🈵、309985359🈵、336380857🈵、522723488、556447629、654558397🈵、392564561🈵、494594000🈵、494070275🈵、168267539🈵、652798487🈵、650979251🈵、622461564🈵、219381522🈵、487874426🈵、398342630🈵、205986087🈵、574153262🈵、606890936🈵、565434047🈵、680947971🈵、341884034🈵、562977817🈵、478962414🈵、679219230🈵、676766033🈵、621874750🈵、522903600🈵、524932879🈵、376261902🈵、481096887🈵、232104667🈵、637879277🈵、697575367🈵、702995203🈵、708665910🈵、697141239🈵、574057714🈵、631332162🈵、591739143🈵、731016871🈵、598738752🈵、748759166🈵、159816595 群内含各种工具、文档、视频教程下载 前言 zheng项目不仅仅是一个开发架构，而是努力打造一套从 前端模板 基础框架 分布式架构 开源项目 持续集成 自动化部署 系统监测 无缝升级 的全方位j2ee企业级开发解决方案。 项目介绍 基于spring springmvc mybatis分布式敏捷开发系统架构，提供整套公共微服务服务模块：内容管理、支付中心、用户管理（包括第三方）、微信平台、存储系统、配置中心、日志分析、任务和通知等，支持服务治理、监控和追踪，努力为中小型企业打造全方位j2ee企业级开发解决方案。 组织结构 lua zheng ├── zheng common ssm框架公共模块 ├── zheng admin 后台管理模板 ├── zheng ui 前台thymeleaf模板 端口 1000 ├── zheng config 配置中心 端口 1001 ├── zheng upms 用户权限管理系统 ├── zheng upms common upms系统公共模块 ├── zheng upms dao 代码生成模块，无需开发 ├── zheng upms client 集成upms依赖包，提供单点认证、授权、统一会话管理 ├── zheng upms rpc api rpc接口包 ├── zheng upms rpc service rpc服务提供者 └── zheng upms server 用户权限系统及sso服务端 端口 1111 ├── zheng cms 内容管理系统 ├── zheng cms common cms系统公共模块 ├── zheng cms dao 代码生成模块，无需开发 ├── zheng cms rpc api rpc接口包 ├── zheng cms rpc service rpc服务提供者 ├── zheng cms search 搜索服务 端口 2221 ├── zheng cms admin 后台管理 端口 2222 ├── zheng cms job 消息队列、任务调度等 端口 2223 └── zheng cms web 网站前台 端口 2224 ├── zheng pay 支付系统 ├── zheng pay common pay系统公共模块 ├── zheng pay dao 代码生成模块，无需开发 ├── zheng pay rpc api rpc接口包 ├── zheng pay rpc service rpc服务提供者 ├── zheng pay sdk 开发工具包 ├── zheng pay admin 后台管理 端口 3331 └── zheng pay web 演示示例 端口 3332 ├── zheng ucenter 用户系统 包括第三方登录 ├── zheng ucenter common ucenter系统公共模块 ├── zheng ucenter dao 代码生成模块，无需开发 ├── zheng ucenter rpc api rpc接口包 ├── zheng ucenter rpc service rpc服务提供者 └── zheng ucenter web 网站前台 端口 4441 ├── zheng wechat 微信系统 ├── zheng wechat mp 微信公众号管理系统 ├── zheng wechat mp dao 代码生成模块，无需开发 ├── zheng wechat mp service 业务逻辑 └── zheng wechat mp admin 后台管理 端口 5551 └── zheng ucenter app 微信小程序后台 ├── zheng api api接口总线系统 ├── zheng api common api系统公共模块 ├── zheng api rpc api rpc接口包 ├── zheng api rpc service rpc服务提供者 └── zheng api server api系统服务端 端口 6666 ├── zheng oss 对象存储系统 ├── zheng oss sdk 开发工具包 ├── zheng oss web 前台接口 端口 7771 └── zheng oss admin 后台管理 端口 7772 ├── zheng message 任务通知系统 ├── zheng message sdk 开发工具包 ├── zheng message server 服务端 端口 8881 socketio端口 8882 └── zheng message client 客户端 ├── zheng shop 电子商务系统 └── zheng demo 示例模块 包含一些示例代码等 ├── zheng demo rpc api rpc接口包 ├── zheng demo rpc service rpc服务提供者 └── zheng demo web 演示示例 端口 9999 技术选型 后端技术 技术 名称 官网 spring framework 容器 http projects spring io spring framework springmvc mvc框架 http docs spring io spring docs current spring framework reference htmlsingle mvc apache shiro 安全框架 http shiro apache org spring session 分布式session管理 http projects spring io spring session mybatis orm框架 http www mybatis org mybatis 3 zh index html mybatis generator 代码生成 http www mybatis org generator index html pagehelper mybatis物理分页插件 http git oschina net free mybatis pagehelper druid 数据库连接池 https github com alibaba druid fluentvalidator 校验框架 https github com neoremind fluent validator thymeleaf 模板引擎 http www thymeleaf org velocity 模板引擎 http velocity apache org zookeeper 分布式协调服务 http zookeeper apache org dubbo 分布式服务框架 http dubbo io tbschedule elastic job 分布式调度框架 https github com dangdangdotcom elastic job redis 分布式缓存数据库 https redis io solr elasticsearch 分布式全文搜索引擎 http lucene apache org solr https www elastic co quartz 作业调度框架 http www quartz scheduler org ehcache 进程内缓存框架 http www ehcache org activemq 消息队列 http activemq apache org jstorm 实时流式计算框架 http jstorm io fastdfs 分布式文件系统 https github com happyfish100 fastdfs log4j 日志组件 http logging apache org log4j 1 2 swagger2 接口测试框架 http swagger io sequence 分布式高效id生产 http git oschina net yu120 sequence alioss qiniu qcloudcos 云存储 https www aliyun com product oss http www qiniu com https www qcloud com product cos protobuf json 数据序列化 https github com google protobuf jenkins 持续集成工具 https jenkins io index html maven 项目构建管理 http maven apache org netty socketio 实时推送 https github com mrniko netty socketio 前端技术 技术 名称 官网 jquery 函式库 http jquery com bootstrap 前端框架 http getbootstrap com bootstrap table bootstrap数据表格 http bootstrap table wenzhixin net cn font awesome 字体图标 http fontawesome io material design iconic font 字体图标 https github com zavoloklom material design iconic font waves 点击效果插件 https github com fians waves ztree 树插件 http www treejs cn v3 select2 选择框插件 https github com select2 select2 jquery confirm 弹出窗口插件 https github com craftpip jquery confirm jquery easyui 基于jquery的ui插件集合体 http www jeasyui com react 界面构建框架 https github com facebook react editor md markdown编辑器 https github com pandao editor md zhengadmin 后台管理系统模板 https github com shuzheng zhengadmin automail 邮箱地址自动补全插件 https github com shuzheng automail zheng jprogress js 加载进度条插件 https github com shuzheng zheng jprogress js zheng jtotop js 返回顶部插件 https github com shuzheng zheng jtotop js socket io js socketio插件 https socket io 架构图 模块依赖 模块介绍 zheng common spring springmvc mybatis框架集成公共模块，包括公共配置、mybatisgenerator扩展插件、通用baseservice、工具类等。 zheng admin 基于bootstrap实现的响应式material design风格的通用后台管理系统，zheng项目所有后台系统都是使用该模块界面作为前端展示。 zheng ui 各个子系统前台thymeleaf模板，前端资源模块，使用nginx代理，实现动静分离。 zheng upms 本系统是基于rbac授权和基于用户授权的细粒度权限控制通用平台，并提供单点登录、会话管理和日志管理。接入的系统可自由定义组织、角色、权限、资源等。用户权限 所拥有角色权限合集 用户加权限 用户减权限，优先级：用户减权限 用户加权限 角色权限 zheng oss 文件存储系统，提供四种方案： 阿里云 oss 腾讯云 cos 七牛云 本地分布式存储 zheng api 服务网关，对外暴露统一规范的接口和包装响应结果，包括各个子系统的交互接口、对外开放接口、开发加密接口、接口文档等服务，可在该模块支持验签、鉴权、路由、限流、监控、容错、日志等功能。示例图： zheng cms 内容管理系统：支持多标签、多类目、强大评论的内容管理，有基本单页展示，菜单管理，系统设置等功能。 zheng pay 一站式支付解决方案，统一下单接口，支持支付宝、微信、网银等多种支付方式。不涉及业务的纯粹的支付平台。 统一下单（统一下单接口、统一扫码）、订单管理、数据分析、财务报表、商户管理、渠道管理、对账系统、系统监控。 zheng ucenter 通用用户管理系统， 实现最常用的用户注册、登录、资料管理、个人中心、第三方登录等基本需求，支持扩展二次开发。 zheng wechat mp 微信公众号管理平台，除实现官网后台自动回复、菜单管理、素材管理、用户管理、消息群发等基础功能外，还有二维码推广、营销活动、微网站、会员卡、优惠券等。 zheng wechat app 微信小程序后台 zheng message 基于netty实现socketio的实时推送系统。支持命名空间、二进制数据、ssl、ack等功能。 环境搭建（qq群内有“zheng环境搭建和系统部署文档 doc”） 开发工具 mysql 数据库 jetty 开发服务器 tomcat 应用服务器 svn git 版本管理 nginx 反向代理服务器 varnish http加速器 intellij idea 开发ide powerdesigner 建模工具 navicat for mysql 数据库客户端 开发环境： jdk7 mysql5 5 redis zookeeper activemq dubbo admin dubbo monitor 工具安装 环境搭建和系统部署文档 作者：小兵，qq群共享提供下载 资源下载 jdk7 http www oracle com technetwork java javase downloads java archive downloads javase7 521261 html maven http maven apache org download cgi redis https redis io download activemq http activemq apache org download archives html zookeeper http www apache org dyn closer cgi zookeeper dubbo http dubbo io download zh htm elastic stack https www elastic co downloads nginx http nginx org en download html jenkins http updates jenkins ci org download war dubbo admin 2 5 3 http download csdn net detail shuzheng5201314 9733652 dubbo admin 2 5 4 snapshot jdk8 http download csdn net detail shuzheng5201314 9733657 更多资源请加qq群 开发指南 1、本机安装jdk7、mysql、redis、zookeeper、activemq并启动相关服务，使用默认配置默认端口即可 2、克隆源代码到本地并打开，推荐使用intellij idea，本地编译并安装到本地maven仓库 修改本地host 127 0 0 1 ui zhangshuzheng cn 127 0 0 1 upms zhangshuzheng cn 127 0 0 1 cms zhangshuzheng cn 127 0 0 1 pay zhangshuzheng cn 127 0 0 1 ucenter zhangshuzheng cn 127 0 0 1 wechat zhangshuzheng cn 127 0 0 1 api zhangshuzheng cn 127 0 0 1 oss zhangshuzheng cn 127 0 0 1 config zhangshuzheng cn 127 0 0 1 zkserver 127 0 0 1 rdserver 127 0 0 1 dbserver 127 0 0 1 mqserver 编译流程 maven编译安装zheng pom xml文件即可 启动顺序（后台） 准备工作 新建zheng数据库，导入project datamodel文件夹下的zheng sql 修改各dao模块和rpc service模块的redis properties、jdbc properties、generator properties数据库连接等配置信息，其中master redis password、master jdbc password、slave jdbc password、generator jdbc password密码值使用了aes加密，请使用com zheng common util aesutil工具类修改这些值 启动zookeeper、redis、activemq、nginx（配置文件参考project tools nginx下的 conf文件） zheng upms 首先启动 zheng upms rpc service 直接运行src目录下的zhengupmsrpcserviceapplication main方法启动 zheng upms server jetty ，然后按需启动对应子系统xxx的zheng xxx rpc service main方法 zheng xxx webapp jetty 访问 http upms zhangshuzheng cn 1111 ，子系统菜单已经配置到zheng upms权限中，不用直接访问子系统，默认帐号密码：admin 123456 登录成功后，可在右上角切换已注册系统访问 zheng cms zheng cms admin：启动activemq 启动 启动zheng rpc service 启动zheng cms admin zheng cms web：启动nginx代理zheng ui静态资源，配置文件可参考 nginx conf zheng oss 首先启动zheng oss web服务 开发阶段，如果zheng oss web没有公网域名，推荐使用ngrok内网穿透工具，为开发环境提供公网域名，实现上传回调 启动nginx代理zheng ui静态资源 开发演示（qq群内有“zheng十分钟视频：从检出到启动 wmv”） 创建数据表（建议使用powerdesigner） 直接运行对应项目dao模块中的generator main ，可自动生成单表的crud功能和对应的model、example、mapper、service代码 生成的model和example均已实现serializable接口，支持分布式 已包含抽象类baseserviceimpl，只需要继承抽象类并传入泛型参数，即可默认实现mapper接口所有方法，特殊需求直接扩展即可 baseserviceimpl默认已实现四种根据条件分页接口 selectbyexamplewithblobsforstartpage selectbyexampleforstartpage selectbyexamplewithblobsforoffsetpage selectbyexampleforoffsetpage baseserviceimpl方法根据读写操作自动切换主从数据源，继承的扩展接口，可手动通过dynamicdatasource setdatasource datasourceenum xxx getname 指定数据源 启动流程：优先rcp service服务提供者，再启动其他webapp 扩展流程：可扩展和拆分rpc api和rpc service模块，可按微服务拆分或场景拆分 部署方式（qq群内有“zheng十分钟视频：从打包到linux服务器部署 wmv”） war包项目：使用tomcat等web容器启动 rpc service服务提供者jar包：将打包后的zheng xxx rpc service assembly tar gz文件解压，使用bin目录的管理脚本运行即可，支持优雅停机。 框架规范约定 约定优于配置 convention over configuration ，此框架约定了很多编程规范，下面一一列举： service类，需要在叫名service的包下，并以service结尾，如cmsarticleserviceimpl controller类，需要在以controller结尾的包下，类名以controller结尾，如cmsarticlecontroller java，并继承basecontroller spring task类，需要在叫名task的包下，并以task结尾，如testtask java mapper xml，需要在名叫mapper的包下，并以mapper xml结尾，如cmsarticlemapper xml mapper接口，需要在名叫mapper的包下，并以mapper结尾，如cmsarticlemapper java model实体类，需要在名叫model的包下，命名规则为数据表转驼峰规则，如cmsarticle java spring配置文件，命名规则为applicationcontext xml 类名：首字母大写驼峰规则；方法名：首字母小写驼峰规则；常量：全大写；变量：首字母小写驼峰规则，尽量非缩写 springmvc配置加到对应模块的springmvc servlet xml文件里 配置文件放到src main resources目录下 静态资源文件放到src main webapp resources目录下 jsp文件，需要在 web inf jsp目录下 requestmapping和返回物理试图路径的url尽量写全路径，如： requestmapping manage 、return manage index requestmapping指定method 模块命名为项目 子项目 业务，如zheng cms admin 数据表命名为：子系统 表，如cms article 更多规范，参考 阿里巴巴java开发手册 http git oschina net shuzheng zheng attach files 演示地址 演示地址： http upms zhangshuzheng cn 预览图 数据模型 拓扑图 开发进度 参与开发 首先谢谢大家支持，如果你希望参与开发，欢迎通过github上fork本项目，并pull request您的commit。 常见问题 eclipse下，dubbo找不到dubbo xsd报错，不影响使用，如果要解决，可参考 http blog csdn net gjldwz article details 50555922 报zheng xxx jar包找不到 请按照文档编译顺序，将源代码编译并安装到本地maven仓库 zheng cms admin启动卡住：因为没有启动activemq zheng upms server访问报session不存在：因为没有启动redis服务 界面没有样式：因为zheng admin没有编译安装到本地仓库 linux下执行rpc service脚本报“bin bash m 坏的解释器”，使用sed i s \r filename删除脚本中\r字符 附件 zheng相关博客 zheng 1：环境搭建及项目部署 zheng项目新建一个module学习学习 zheng项目系统简单的分析记录 zheng项目 从rpc service开始！ 进击zheng项目zheng umps server zheng环境搭建 让zheng支持activiti工作流 让zheng更完美地支持ajax提交的json数据 优秀文章和博客 创业互联网公司如何搭建自己的技术框架 微服务实战 单点登录原理与简单实现 iteye论坛关于权限控制的讨论 rbac新解：基于资源的权限管理 resource based access control 网站架构经验随笔 支付系统架构 spring整合jms 跟我学shiro目录贴 跟我学springmvc目录汇总贴 跟我学spring3 目录贴 跟我学openresty nginx lua 开发目录贴 redis中文网 读懂redis并配置主从集群及高可用部署 redis哨兵 实现redis高可用 elk elasticsearch logstash kibana 搭建实时日志分析平台 nginx基本功能极速入门 mybatis genarator 自定义插件 elasticsearch权威指南（中文版） springmvc对简单对象、set、list、map的数据绑定和常见问题 如何细粒度地控制你的mybatis二级缓存 git 在团队中的最佳实践 如何正确使用git flow 做个男人，做个成熟的男人，做个有城府的男人 在线小工具 在线cron表达式生成器 在线工具 程序员的工具箱 在线文档 jdk7英文文档 spring4 x文档 mybatis3官网 dubbo官网 nginx中文文档 freemarker在线手册 velocity在线手册 bootstrap在线手册 git官网中文文档 thymeleaf 许可证 mit