
## 用户积分表

表名：uni-id-scores

| 字段				| 类型		| 必填	| 描述											|
| ----------------	| ---------	| ----	| -------------------------------------------	|
| \_id				| Object ID	| 是	| 存储文档 ID，系统自动生成			|
| user_id			| String	| 是	|												|
| score				| Integer	| 是	| 本次变化的积分									|
| type				| Integer	| 否	| 积分类型 1:收入 2:支出									|
| balance			| Integer	| 是	| 变化后的积分余额									|
| comment			| String	| 否	| 备注，说明积分新增、消费的缘由				|
| create_date		| Timestamp	| 否	| 创建时间										|


## 用户任务表

表名：uni-id-task

| 字段				| 类型		| 必填	| 描述											|
| ----------------	| ---------	| ----	| -------------------------------------------	|
| \_id				| Object ID	| 是	| 存储文档 ID，系统自动生成			|
| name				| String	| 是	| 任务名称										|
| comment			| String	| 是	| 任务描述										|
| bounty			| Integer	| 否	| 任务完成后的奖励积分							|
| max_per_hour		| Integer	| 否	| 每小时允许执行的最大次数						|
| max_per_day		| Integer	| 否	| 每天允许执行的最大次数						|
| max_per_week		| Integer	| 否	| 每周允许执行的最大次数						|
| create_date		| Timestamp	| 否	| 创建时间										|

表名：uni-id-task-log

| 字段				| 类型		| 必填	| 描述											|
| ----------------	| ---------	| ----	| -------------------------------------------	|
| \_id				| Object ID	| 是	| 存储文档 ID，系统自动生成			|
| user_id			| String	| 是	| 用户ID										|
| task_id			| String	| 是	| 任务ID										|
| result			| Boolean	| 否	| 任务执行结果，true:成功，false：失败			|
| bounty			| Integer	| 否	| 奖励积分										|
| create_date		| Timestamp	| 否	| 创建时间										|
