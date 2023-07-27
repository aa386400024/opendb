## 文章&评论

### 文章表


表名：opendb-news-articles

| 字段								| 类型			| 必填| 描述																				|
| ----------------		| ---------	| ----| -------------------------------------------	|
| \_id								| Object ID	| 是	| 存储文档 ID（文章 ID），系统自动生成				|
| user_id							| String		| 是	| 文章作者ID， 参考`uni-id-users` 表					|
| category_id					| String		| 否	| 分类 id，参考`opendb-news-categories`表				|
| title								| String		| 是	| 标题																				|
| content							| String		| 是	| 文章内容																		|
| excerpt							| String		| 否	| 文章摘录																		|
| article_status			| Integer		| 是	| 文章状态：0 草稿箱 1 已发布									|
| view_count					| Integer		| 是	| 阅读数量																		|
| like_count					| Integer		| 是	| 喜欢数、点赞数															|
| is_sticky						| Boolean		| 是	| 是否置顶																		|
| is_essence					| Boolean		| 是	| 阅读加精																		|
| comment_status			| Integer		| 是	| 评论状态：0 关闭  1 开放										|
| comment_count				| Integer		| 是	| 评论数量																		|
| last_comment_user_id| String		| 否	| 最后回复用户 id，参考`uni-id-users` 表			|
| avatar							| String		| 否	| 缩略图地址																	|
| publish_date				| Timestamp	| 否	| 发表时间																		|
| publish_ip					| String		| 否	| 发表时 IP 地址															|
| last_modify_date		| Timestamp	| 否	| 最后修改时间																|
| last_modify_ip			| String		| 否	| 最后修改时 IP 地址													|

### 文章类别

表名：opendb-news-categories

| 字段						| 类型			| 必填| 描述																				|
| ----------------| ---------	| ----| -------------------------------------------	|
| \_id						| Object ID	| 是	| 存储文档 ID（文章 ID），系统自动生成				|
| name						| String		| 是	| 类别名称																		|
| description			| String		| 是	| 类别描述																		|
| icon						| String		| 是	| 类别图标地址																|
| sort						| Integer		| 否	| 类别显示顺序																|
| article_count		| Integer		| 否	| 该类别下文章数量														|
| create_date			| Timestamp	| 否	| 创建时间																		|


### 评论表

表名：opendb-news-comments

| 字段						| 类型			| 必填| 描述																					|
| ----------------| ---------	| ----| -------------------------------------------		|
| \_id						| Object ID	| 是	| 存储文档 ID（文章 ID），系统自动生成					|
| article_id			| String		| 是	| 文章ID，opendb-news-posts 表中的`_id`字段				|
| user_id					| String		| 是	| 评论者ID，参考`uni-id-users` 表								|
| comment_content	| String		| 是	| 评论内容																			|
| like_count			| Integer		| 是	| 评论喜欢数、点赞数														|
| comment_type		| Integer		| 是	| 回复类型： 0 针对文章的回复  1 针对评论的回复	|
| reply_user_id		| String		| 是	| 被回复的评论用户ID，comment_type为1时有效			|
| reply_comment_id| String		| 是	| 被回复的评论ID，comment_type为1时有效					|
| comment_date		| Timestamp	| 否	| 评论发表时间																	|
| comment_ip			| String		| 否	| 评论发表时 IP 地址														|
