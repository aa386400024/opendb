## 电商系统

### 商品表


表名：opendb-mall-goods

| 字段								| 类型			| 必填| 描述																																|
| ----------------		| ---------	| ----| -------------------------------------------													|
| \_id								| Object ID	| 是	| 存储文档 ID（文章 ID），系统自动生成																|
| category_id					| String		| 否	| 分类 id，参考`opendb-mall-categories`表																|
| goods_sn						| String		| 是	| 商品的唯一货号																											|
| name								| String		| 是	| 商品名称																														|
| keywords						| String		| 否	| 商品关键字，为搜索引擎收录使用																			|
| goods_desc					| String		| 否	| 商品详细描述																												|
| goods_thumb					| String		| 否	| 商品缩略图，用于在列表或搜索结果中预览显示													|
| goods_banner_imgs		| Array			| 否	| 商品详情页的banner图地址																						|
| remain_count				| int		| 是	| 库存数量																														|
| month_sell_count		| int		| 是	| 月销量																															|
| total_sell_count		| int		| 是	| 总销量																															|
| comment_count				| int		| 是	| 累计评论数																													|
| is_real							| Boolean		| 是	| 是否实物																														|
| is_on_sale					| Boolean		| 是	| 是否上架销售																												|
| is_alone_sale				| Boolean		| 是	| 是否能单独销售；如果不能单独销售，则只能作为某商品的配件或者赠品销售|
| is_best							| Boolean		| 是	| 是否精品																														|
| is_new							| Boolean		| 是	| 是否新品																														|
| is_hot							| Boolean		| 是	| 是否热销																														|
| add_date						| Timestamp	| 否	| 上架时间																														|
| last_modify_date		| Timestamp	| 否	| 最后修改时间																												|
| seller_note					| String		| 否	| 商家备注，仅商家可见																												|

### 商品 SKU 表

表名：opendb-mall-sku

名词解释：sku：Stock Keeping Unit。

sku 在电商系统中可定义库存控制的最小单元，同一个商品如有多个属性，则可定义多个sku。举例来说，某手机有8G内存和16G内存，则可定义两个sku，表示这种型号的差异。

理论上，基于商品的每个属性差异，可定义多个sku，比如颜色、重量、大小、材质等，故opendb中的商品sku，仅定义通用售价、库存数量等参数，各属性差异可由开发者自行扩展。

| 字段				| 类型		| 必填	| 描述											|
| ----------------	| ---------	| ----	| -------------------------------------------	|
| \_id				| Object ID	| 是	| 存储文档 ID（文章 ID），系统自动生成			|
| goods_id			| String	| 是	| 商品 id，参考 opendb-mall-goods 表			|
| sku_name			| String	| 是	| SKU名称										|
| price				| int		| 是	| 价格，以分为单位，避免浮点计算的精度问题		|
| market_price		| int		| 否	| 市场价，以分为单位，避免浮点计算的精度问题	|
| stock				| int		| 是	| 库存数量										|
| create_date		| Timestamp	| 是	| 创建时间										|
| update_date		| Timestamp	| 否	| 修改时间										|

### 商品类别

表名：opendb-mall-categories

| 字段						| 类型			| 必填| 描述																				|
| ----------------| ---------	| ----| -------------------------------------------	|
| \_id						| Object ID	| 是	| 存储文档 ID（文章 ID），系统自动生成				|
| name						| String		| 是	| 类别名称																		|
| description			| String		| 是	| 类别描述																		|
| create_date			| Timestamp	| 否	| 创建时间																		|


### 商品评论表

表名：opendb-mall-comments

| 字段						| 类型			| 必填| 描述																				|
| ----------------| ---------	| ----| -------------------------------------------	|
| \_id						| Object ID	| 是	| 存储文档 ID（文章 ID），系统自动生成				|
| goods_id				| String		| 是	| 商品ID，opendb-mall-goods 表中的`_id`字段			|
| user_id					| String		| 是	| 评论者ID，参考`uni-id-users` 表							|
| comment_content	| String		| 是	| 评论内容																		|
| comment_date		| Timestamp	| 否	| 评论发表时间																|
| comment_ip			| String		| 否	| 评论发表时 IP 地址													|
