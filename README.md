# openDB

数据库设计，是数字经济的基础，是重要的软基建。

`openDB`，是一套开放的数据表设计规范，包括了表名、字段等schema定义以及初始数据。

以用户表为例，它约定了一个标准用户表的表名和字段定义，并且基于nosql的特性，可以由开发者自行扩展字段。

`openDB`是[uniCloud](https://uniapp.dcloud.io/uniCloud/)的重要软基建，支撑uniCloud数字生态的发展。

# 需求背景
- 很多js工程师不善于数据库设计，希望有成熟的数据库模板，避免走弯路
- 有利于产业分工。业务开发、统计分析、智能推荐、数据转换等都是不同的专业角色，大多数开发者仅善于业务开发，需要专业的数据服务商为其提供服务，如果数据库标准统一，各个角色就可以在插件市场各自提供插件。
  * 比如有专业数据服务商，基于openDB中电商规范，提供“猜你喜欢”插件，就可以被轻松的引入到开发者的应用中；
  * 比如有专业的数据导入导出插件，可以方便的从ecshop等系统中迁移历史数据；
  * 比如有专业的cms后台厂商，基于openDB中新闻规范，提供更好的新闻编辑工具。
- 统一的数据库标准，有利于开发者择优切换插件。有利于插件生态的繁荣，并最终通过吸引更多用户做大蛋糕来反哺插件作者。
  * 比如有多个新闻应用模板，均基于openDB中的新闻规范，那么开发者可以方便的切换到做的更好的插件上。
- 数据孤岛问题。当多个应用之间的数据库规范相同，他们之间的跨应用数据交换就变的更容易。未来uniCloud会提供更方便的跨应用数据交换机制。
- 统一的初始数据。比如地区表等数据，在openDB中有初始化数据，开发者们共享一个相同数据源即可。

[uni-id](https://uniapp.dcloud.io/uniCloud/uni-id)的账户统一，是`openDB`的成功实践。基于uni-id规范，有电商插件、有IM插件、有PC管理插件，开发者可以方便的把这些插件整合到自己的同一应用中。


# openDB中的已有规范：

目前`openDB`已经支持几十张表。可以在[https://gitee.com/dcloud/opendb/tree/master/collection](https://gitee.com/dcloud/opendb/tree/master/collection)查看。

部分常用表单独提供文档如下：

1. [用户管理（uni-id）](uni-id.md)
2. [文章&评论（opendb-news）](opendb-news.md)
3. [电商系统（opendb-mall）](opendb-mall.md)
4. [新闻系统（opendb-news）](opendb-news.md)
5. [日志管理（opendb-log）](opendb-log.md)

# 预置数据

`openDB`不仅支持定义常用的数据表字段，还可以预置初始化数据。

比如，[opendb-city-china](https://gitee.com/dcloud/opendb/tree/master/collection/opendb-city-china)是opendb中定义好的`中国城市字典表`，它的定义分为两个部分：
- collection.json：定义数据表名称、所含字段、每个字段的类型以及读写权限规则等；
- data.json：定义初始化内容

你通过[uniCloud web控制台](https://unicloud.dcloud.net.cn)创建`openDB`表时，`uniCloud`会自动校验该opendb表定义中是否包含`data.json`，若包含，则在创建表定义后，自动导入`data.json`。

如果你的 HBuilderX 项目中，`uniCloud/database`目录下定义的数据表中含有opendb表定义，则对该opendb表执行`上传DB Schema`操作时，uniCloud服务端会判断该opendb表是否已存在：
- 若该opendb表已存在，则仅更新 `DB Schema`；
- 若该opendb表不存在，则先创建该表，然后校验该opendb表定义中是否包含`data.json`，若包含`data.json`，则自动导入`data.json`

# 数据表升级

`openDB`数据表在后续的更新迭代中，可能会涉及到`schema`及`预置数据`的变更。自`HBuilderX 3.5.1`之后，opendb表支持检查更新。

以[opendb-city-china](https://gitee.com/dcloud/opendb/tree/master/collection/opendb-city-china)为例，当我们要修改或补充城市时，为了兼容已部署的数据表，应提供差量数据，这时我们需要做的是：
- 更新 `opendb-city-china/package.json`中的`version`字段为升级后的版本号；
- 新增 `opendb-city-china/collection.update-原始版本号-升级版本号.jql` JQL数据库管理器文件，内容为差量数据的JQL语句；

比如行政区域的撤销或设立需要数据升级，并且定义升级后的版本号为0.0.2，这时需要将差量数据以JQL语句的形式写入文件`opendb-city-china/collection.update-0.0.1-0.0.2.jql`中，并更新`opendb-city-china/package.json`的`version`字段。


# 如何引入到自己的服务空间

在[uniCloud web控制台](https://unicloud.dcloud.net.cn)，新建表时，可直接选择所有`openDB`的表。

首先选分类，每个分类下又有若干表，表结构和预置数据可直接预览。支持多个表一起创建。

![](https://static-eefb4127-9f58-4963-a29b-42856d4205ee.bspapp.com/newopendb.jpg)

`openDB`的表，不应修改表名，修改后就无法与其他插件连同了。

# 欢迎参与

`openDB`是一个持续发展的、由开发者共建的规范。DCloud欢迎各个业务领域的专业开发者提供规范。

开发者通过提pr的方式，给`openDB`添加规范，或者给已有规范的表添加字段，或者添加初始化数据。gitee支持轻量pr，尤其适合共同编辑规范。

- 您将在这个具有重大意义的项目中的贡献者名单中留下自己的名字
- 您提的pr成为规范将帮助您享受整个产业链的支持

其他注意：

- 为了向下兼容，`openDB`只增加表和字段，不删改。