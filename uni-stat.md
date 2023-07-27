
# 上报维度


## uni统计-平台表 uni-stat-app-platforms

### 字段说明

|字段名				|类型		|默认值		|说明					|
| :--------:		| :-----:	|:---------:|:-------------------:	|
|  _id				|  string	|  -		|ID，系统自动生成		|
|  code				|  string	|  -		|平台代码，客户端上报	|
|  name				|  string	|  -		|平台名称，管理端显示	|
|  order			|  int		|  -		|序号，管理端排序使用	|
|  create_time		|  timestamp|  -		|创建时间				|
|  last_modify_time	|  timestamp|  -		|最后修改时间			|


## uni统计-应用渠道表 uni-stat-app-channels


### 字段说明

|字段名				|  类型		|默认值		|说明												|
| :--------:		| :-----:	|:---------:|:---------------------------------------:			|
|  _id				| string	|-			|ID，系统自动生成									|
|  appid			| string	|-			|统计应用ID，对应opendb-app-list.appid				|
|  platform_id		| string	|-			|应用平台编号，对应uni-stat-app-platforms._id		|
|  channel_code		| string	|-			|客户端上报的渠道编码，如：xiaomi					|
|  channel_name		| string	|-			|渠道名称/场景名称，渠道名称管理员可编辑，管理端显示|
|  create_time		| timestamp	|-			|创建时间											|
|  last_modify_time	| timestamp	|-			|最后修改时间										|


## uni统计-小程序场景值对照表 uni-stat-mp-scenes

各平台小程序场景值

### 字段说明

|   字段名		|  类型		| 默认值	|            说明							|
| :--------:	| :-----:	|:-------:	| :-------------------:						|
|  _id			| string	|  -		|  ID，系统自动生成							|
|  platform		| string	|  -		|  应用平台，对应uni-stat-app-platforms.code|
|  scene_code	| string	|  -		|  场景代码									|
|  scene_name	| string	|  -		|  场景名称									|
|  create_time	| timestamp	|  -		|  创建时间									|


## uni统计-应用版本表 uni-stat-app-versions

### 字段说明

|   字段名			|  类型		| 默认值	|            说明								|
| :--------:		| :-----:	|:---------:| :-------------------:							|
|   _id				| string	|  -		|  ID，系统自动生成								|
|  appid			| string	|  -		|  统计应用ID，对应opendb-app-list.appid		|
|  platform_id		| string	|-			|应用平台编号，对应uni-stat-app-platforms._id	|
|  version			| string	|  -		|  应用版本										|
|  create_time		| timestamp	|  -		|  创建时间										|
|  last_modify_time	| timestamp	|  -		|  最后修改时间									|

说明：这是专为uni统计增加的版本表，和uni升级中心的版本表不同。

## uni统计-应用事件表 uni-stat-events

事件字典表

### 字段说明

|   字段名			|  类型		|  默认值		|            说明						|
| :--------:		| :-----:	|:----------:	| :-------------------:					|
|  _id				| string	|  -			|  ID，系统自动生成						|
|  appid			| string	|  -			|  统计应用ID，对应opendb-app-list.appid|
|  event_key		| string	|  -			|  事件键值，如：login					|
|  event_name		| string	|  -			|  事件名称，管理端显示，如：登录		|
|  create_time		| timestamp	|  -			|  创建时间								|
|  last_modify_time	| timestamp	|  -			|  最后修改时间							|


## uni统计-应用页面表 uni-stat-pages

### 字段说明

|   字段名		|  类型		|  默认值	|            说明						|
| :--------:	| :-----:	|:------:	| :-------------------:					|
| _id			| string	|  -		|ID，系统自动生成						|
| appid			| string	|  -		|统计应用ID，对应opendb-app-list.appid	|
| path			| string	|  -		|页面路径，如`pages/index/index`		|
| title			| string	|  -		|页面标题								|
| create_time	| timestamp	|  -		|创建时间								|


## uni统计-应用会话日志表 uni-stat-session-logs

### 字段说明

|   字段名				|  类型		| 默认值	|            说明								|
| :--------:			| :-----:	|:--------:	| :-----------------:							|
|  _id					| string	|  -		|  ID，系统自动生成								|
|  appid				| string	|  -		|  客户端携带的应用ID							|
|  version				| string	|  -		|  客户端上报的应用版本号						|
|  platform				| string	|  -		|  客户端上报的平台code							|
|  channel				| string	|  -		|  客户端上报的渠道code或场景值ID				|
|  device_id			| string	|  -		|  客户端携带的设备标识							|
|  last_visit_user_id	| string	|  -		|  本次会话最终访问用户的ID, uni-id-users._id	|
|  is_first_visit		| int		|  0		|  是否为该设备的首次访问，0否 1是				|
|  first_visit_time		| timestamp	|  -		|  该设备的首次访问时间							|
|  last_visit_time		| timestamp	|  -		|  该设备的最终访问时间							|
|  total_visit_count	| int		|  -		|  累计访问次数，客户端上报						|
|  entry_page_id		| string	|  -		|  本次会话入口页面ID, 同uni-stat-pages._id		|
|  exit_page_id			| string	|  -		|  本次会话退出页面ID, 同uni-stat-pages._id		|
|  page_count			| int		|  -		|  本次会话浏览的页面数，服务端计算				|
|  event_count			| int		|  -		|  本次会话产生的事件数，服务端计算				|
|  duration				| int		|  -		|  本次会话时长，单位为秒，服务端计算			|
|  sdk_version			| string	|  -		|  基础库版本号									|
|  platform_version		| string	|  -		|  平台版本，如微信、支付宝宿主App版本号		|
|  device_os			| int		|  -		|  设备系统编号，1：安卓，2：iOS，3：PC			|
|  device_os_version	| string	|  -		|  设备系统版本									|
|  device_net			| string	|  -		|  设备网络型号wifi/3G/4G/						|
|  device_vendor		| string	|  -		|  设备供应商apple/华为							|
|  device_model			| string	|  -		|  设备型号iphone8/mate30						|
|  device_language		| string	|  -		|  设备语言包									|
|  device_pixel_ratio	| string	|  -		|  设备像素比									|
|  device_window_width	| string	|  -		|  设备窗口宽度									|
|  device_window_height	| string	|  -		|  设备窗口高度									|
|  device_screen_width	| string	|  -		|  设备屏幕宽度									|
|  device_screen_height	| string	|  -		|  设备屏幕高度									|
|  location_ip			| string	|  -		|  ip地址										|
|  location_latitude	| double	|  -		|  纬度											|
|  location_longitude	| double	|  -		|  经度											|
|  location_country		| string	|  -		|  国家											|
|  location_province	| string	|  -		|  省份											|
|  location_city		| string	|  -		|  城市											|
|  is_finish			| int		|  -		|  本次会话是否结束，0：否，1是，服务端计算		|
|  create_time			| timestamp	|  -		|  创建时间										|




## uni统计-用户会话日志表 uni-stat-user-session-logs

用于记录登录用户的会话日志

### 字段说明
|   字段名			|  类型		| 默认值	|            说明											|
| :--------:		| :-----:	|:--------:	| :-----------------:										|
|  _id				| string	|  -		|  ID，系统自动生成											|
|  appid			| string	|  -		|  客户端携带的应用ID										|
|  version			| string	|  -		|  客户端上报的应用版本号									|
|  platform			| string	|  -		|  客户端上报的平台code										|
|  channel			| string	|  -		|  客户端上报的渠道code或场景值ID							|
|  session_id		| string	|  -		|  访问会话日志ID，对应uni-stat-session-logs._id			|
|  uid				| string	|  -		|  用户ID, uni-id-users._id，反解客户端请求携带的token获得	|
|  last_visit_time	| timestamp	|  -		|  该用户最后一次访问时间									|
|  entry_page_id	| string	|  -		|  本次会话入口页面ID, 同uni-stat-pages._id					|
|  exit_page_id		| string	|  -		|  本次会话退出页面ID, 同uni-stat-pages._id					|
|  page_count		| int		|  -		|  本次会话浏览的页面数，服务端计算							|
|  event_count		| int		|  -		|  本次会话产生的事件数，服务端计算							|
|  duration			| int		|  -		|  本次会话时长，单位为秒，服务端计算						|
|  is_finish		| int		|  -		|  本次会话是否结束，0：否，1是，服务端计算					|
|  create_time		| timestamp	|  -		|  创建时间													|



## uni统计-应用事件日志表 uni-stat-event-logs

### 字段说明

|   字段名				|  类型				|    默认值		|            说明											|
| :--------:			| :-----:			|:------------:	| :-------------------:										|
|  _id					| string			|  -			|  ID，系统自动生成											|
|  appid				| string			|   -			|  客户端携带的应用ID										|
|  version				| string			|  -			|  客户端上报的应用版本号									|
|  platform				| string			|  -			|  客户端上报的平台code										|
|  channel				| string			|  -			|  客户端上报的渠道code/场景值								|
|  device_id			| string			|  -			|  客户端携带的设备标识										|
|  uid					| string			|  -			|  用户ID, uni-id-users._id，反解客户端请求携带的token获得	|
|  session_id			| string			|  -			|  访问会话日志ID，对应uni-stat-session-logs._id			|
|  page_id				|   string			|  -			|  页面表ID，对应uni-stat-pages._id							|
|  event_key			|   string			|  -			|  客户端上报的key											|
|  param				|   string/Object	|  -			|  事件参数													|
|  sdk_version			| string			|  -			|  基础库版本号												|
|  platform_version		| string			|  -			|  平台版本，如微信、支付宝宿主App版本号					|
|  device_os			| int				|  -			|  设备系统编号，1：安卓，2：iOS，3：PC						|
|  device_os_version	| string			|  -			|  设备系统版本												|
|  device_net			| string			|  -			|  设备网络型号wifi/3G/4G/									|
|  device_vendor		| string			|  -			|  设备供应商apple/华为										|
|  device_model			| string			|  -			|  设备型号iphone8/mate30									|
|  device_language		| string			|  -			|  设备语言包												|
|  device_pixel_ratio	| string			|  -			|  设备像素比												|
|  device_window_width	| string			|  -			|  设备窗口宽度												|
|  device_window_height	| string			|  -			|  设备窗口高度												|
|  device_screen_width	| string			|  -			|  设备屏幕宽度												|
|  device_screen_height	| string			|  -			|  设备屏幕高度												|
|  create_time			| timestamp			|  -			|  创建时间													|



## uni统计-应用页面访问日志表 uni-stat-page-logs

### 字段说明

|   字段名					|  类型		|默认值	|            说明												|
| :--------:				| :-----:	|:-----:| :-------------------:											|
|   _id						| string	| -		|  ID，系统自动生成												|
|  appid					| string	| -		|  客户端携带的应用ID											|
|  version					| string	| -		|  客户端上报的应用版本号										|
|  platform					| string	| -		|  客户端上报的平台code											|
|  channel					| string	| -		|  客户端上报的渠道code/场景值									|
|  device_id				| string	| -		|  客户端携带的设备标识											|
|  uid						| string	|  -	|  用户ID, uni-id-users._id，反解客户端请求携带的token获得		|
|  session_id				| string	| -		|  访问会话日志ID，对应uni-stat-session-logs._id				|
|  page_id					|  string	| -		|  当前页面ID，对应uni-stat-pages._id							|
|  query_string				|  string	| -		|  附带参数														|
|  previous_page_id			|  string	| -		|  上级一个页面ID，为空表示第一个页面, 对应uni-stat-pages._id	|
|  previous_page_duration	|  int		| -		|  上级页面停留时间，单位秒，前端上报							|
|  previous_page_is_entry	|  int		| 0		|  上级页面是否为入口页, 0否 1是								|
|  create_time				| timestamp	| -		|  创建时间														|


## uni统计-分享日志表 uni-stat-share-logs

### 字段说明

|   字段名		|  类型		|   默认值		|            说明											|
| :--------:	| :-----:	|:-------------:| :-------------------:										|
|   _id			| string	| -				| ID，系统自动生成											|
|  appid		| string	| -				| 客户端携带的应用ID										|
|  version		| string	| -				| 客户端上报的应用版本号									|
|  platform		| string	| -				| 客户端上报的平台code										|
|  channel		| string	| -				| 客户端上报的渠道code/场景值								|
|  device_id	| string	| -				| 客户端携带的设备标识										|
|  uid			| string	|  -			|  用户ID, uni-id-users._id，反解客户端请求携带的token获得	|
|  session_id	| string	| -				| 访问会话日志ID，对应uni-stat-app-session-logs._id			|
|  page_id		| string	| -				| 当前页面ID，对应uni-stat-app-pages._id					|
|  create_time	| timestamp	| -				| 创建时间													|


## uni统计-应用错误日志表 uni-stat-error-logs

### 字段说明

|字段名				|类型		|默认值			|            说明											|
| :--------:		| :-----:	|:-----------:	| :-------------------:										|
| _id				| string	| -				| ID，系统自动生成											|
| appid				| string	| -				| 客户端携带的应用ID										|
| version			| string	| -				| 客户端上报的应用版本号									|
| platform			| string	| -				| 客户端上报的平台code										|
| channel			| string	| -				| 客户端上报的渠道code/场景值								|
| device_id			| string	| -				| 客户端携带的设备标识										|
| uid				| string	|  -			| 用户ID, uni-id-users._id，反解客户端请求携带的token获得	|
| os				| string	|  -			| 客户端操作系统											|
| ua				| string	|  -			| 客户端user-agent信息										|
| page_url			| string	|  -			| 页面url													|
| space_id			| string	|  -			| 服务空间编号												|
| space_provider	| string	|  -			| 服务空间提供商											|
| sdk_version		| string	| -				| 小程序基础库版本号										|
| platform_version	| string	| -				| 微信、支付宝宿主App的版本号								|
| error_msg			| string	| -				| 错误信息													|
| error_hash		| string	| -				| 错误hash码												|
| create_time		| timestamp	| -				| 创建时间													|


<!-- ## uni统计- 用户表 uni-stat-users

统计专属用户表，用于区分不同应用、平台、版本、渠道下的用户群体

### 字段说明

|字段名			|类型		|默认值			|            说明											|
| :--------:	| :-----:	|:-----------:	| :-------------------:										|
| _id			| string	| -				| ID，系统自动生成											|
| appid			| string	| -				| 客户端携带的应用ID										|
| version		| string	| -				| 客户端上报的应用版本号									|
| platform		| string	| -				| 客户端上报的平台code										|
| channel		| string	| -				| 客户端上报的渠道code/场景值								|
| uid			| string	| -				| 用户ID, uni-id-users._id，反解客户端请求携带的token获得	|
| is_new		| int		| 0				| 是否为新用户，0否 1是										|
| create_time	| timestamp	| -				| 创建时间													| -->




# 统计维度

***目前只是基础表，可根据实际统计业务进行补充、拆分、合并*** 

## uni统计- 应用统计结果表 uni-stat-result

统计结果包含：
- 新增用户/设备数
- 活跃用户/设备数
- 基础数据汇总

### 字段说明

|字段名						|类型			|默认值		|说明																		|
| :--------:				| :-----:		|:---------:| :-------------------:														|
|  _id						| string		|     -		|  ID，系统自动生成															|
|  appid					| string		|     -		|  统计应用ID，对应opendb-app-list.appid									|
|  platform_id				| string		|     -		|  应用平台ID，对应uni-stat-app-platforms._id								|
|  channel_id				| string		|     -		|  渠道/场景值ID，对应uni-stat-app-channels._id								|
|  version_id				| string		|     -		|  应用版本ID，对应uni-stat-app-versions._id								|
|  total_users				|   int			|     -		|  历史累计总用户数															|
|  new_user_count			|   int			|     -		|  本时间段新增用户数														|
|  active_user_count		|   int			|     -		|  本时间段活跃用户数														|
|  total_devices			|   int			|     -		|  历史累计总设备数															|
|  new_device_count			|   int			|     -		|  本时间段新增设备数														|
|  user_session_times		|   int			|     -		|  本时间段用户的会话次数													|
|  active_device_count		|   int			|     -		|  本时间段活跃设备数														|
|  app_launch_count			|   int			|     -		|  本时间段App启动或从后台切到前台的次数									|
|  page_visit_count			|   int			|     -		|  本时间段内PV的概念														|
|  count					|   int			|     -		|  本时间段报错次数															|
|  duration					|   int			|     -		|  本时间段内，所有会话访问总时长,单位秒									|
|  user_duration			| int			|     -		|  本次登录用户的会话总时长，单位为秒										|
|  avg_device_session_time	|   int			|     -		|  设备的次均停留时长,单位秒												|
|  avg_device_time			|   int			|     -		|  设均停留时长(平均每台设备的停留时长),单位秒								|
|  avg_user_session_time	|   int			|     -		|  用户的次均停留时长,单位秒												|
|  avg_user_time			|   int			|     -		|  人均停留时长(平均每个登录用户的停留时长),单位秒							|
|  bounce_times				|   int			|     -		|  跳出次数																	|
|  bounce_rate				|   double		|     -		|  跳出率																	|
|  retention				|   object		|     -		|  留存信息																	|
|  dimension				|   string		|     -		|  统计范围 day:按天统计，hour:按小时统计, week：按周统计，month：按月统计	|
|  stat_date				|   int			|     -		|  统计日期，格式yyyymmdd，例:20211201										|
|  start_time				|   timestamp	|     -		|  开始时间																	|
|  end_time					|   timestamp	|     -		|  结束时间																	|

说明：
- bounce_rate计算方式：一次会话仅访问一个页面的启动次数 / 总启动次数

- retention 用户留存信息字段结构说明：

``` json
{
	//活跃用户留存信息，可根据业务需要自行拓展
	active_user:{
		//1日后留存
		d_1:{
			//留存用户数
			user_count: 100,
			//留存率
			user_rate: 80.30
		},
		//2日后留存
		d_2:{
			user_count: 80,
			user_rate: 64.24
		},
		//3日后留存
		d_3:{
			user_count: 70,
			user_rate: 56.21
		},
		//4日后留存
		d_4:{
			user_count: 60,
			user_rate: 48.18
		},
		//5日后留存
		d_5:{
			user_count: 50,
			user_rate: 40.15
		},
		//6日后留存
		d_6:{
			user_count: 40,
			user_rate: 32.12
		},
		//7日后留存
		d_7:{
			user_count: 30,
			user_rate: 24.90
		},
		//14日后留存
		d_14:{
			user_count: 20,
			user_rate: 16.60
		},
		//30日后留存
		d_30:{
			user_count: 10,
			user_rate: 8.30
		}
	},
	//新增用户留存信息
	new_user:{
		//1日后留存
		d_1:{
			//留存用户数
			user_count: 100,
			//留存率
			user_rate: 80.30
		},
		//2日后留存
		d_2:{
			user_count: 80,
			user_rate: 64.24
		},
		//3日后留存
		d_3:{
			user_count: 70,
			user_rate: 56.21
		},
		//4日后留存
		d_4:{
			user_count: 60,
			user_rate: 48.18
		},
		//5日后留存
		d_5:{
			user_count: 50,
			user_rate: 40.15
		},
		//6日后留存
		d_6:{
			user_count: 40,
			user_rate: 32.12
		},
		//7日后留存
		d_7:{
			user_count: 30,
			user_rate: 24.90
		},
		//14日后留存
		d_14:{
			user_count: 20,
			user_rate: 16.60
		},
		//30日后留存
		d_30:{
			user_count: 10,
			user_rate: 8.30
		}
	},
	//活跃设备留存信息，可根据业务需要自行拓展
	active_device:{
		//1日后留存
		d_1:{
			//留存设备数
			device_count: 100,
			//留存率
			device_rate: 80.30
		},
		//2日后留存
		d_2:{
			device_count: 80,
			device_rate: 64.24
		},
		//3日后留存
		d_3:{
			device_count: 70,
			device_rate: 56.21
		},
		//4日后留存
		d_4:{
			device_count: 60,
			device_rate: 48.18
		},
		//5日后留存
		d_5:{
			device_count: 50,
			device_rate: 40.15
		},
		//6日后留存
		d_6:{
			device_count: 40,
			device_rate: 32.12
		},
		//7日后留存
		d_7:{
			device_count: 30,
			device_rate: 24.90
		},
		//14日后留存
		d_14:{
			device_count: 20,
			device_rate: 16.60
		},
		//30日后留存
		d_30:{
			device_count: 10,
			device_rate: 8.30
		}
	},
	//新增设备留存信息
	new_device:{
		//1日后留存
		d_1:{
			//留存设备数
			device_count: 100,
			//留存率
			device_rate: 80.30
		},
		//2日后留存
		d_2:{
			device_count: 80,
			device_rate: 64.24
		},
		//3日后留存
		d_3:{
			device_count: 70,
			device_rate: 56.21
		},
		//4日后留存
		d_4:{
			device_count: 60,
			device_rate: 48.18
		},
		//5日后留存
		d_5:{
			device_count: 50,
			device_rate: 40.15
		},
		//6日后留存
		d_6:{
			device_count: 40,
			device_rate: 32.12
		},
		//7日后留存
		d_7:{
			device_count: 30,
			device_rate: 24.90
		},
		//14日后留存
		d_14:{
			device_count: 20,
			device_rate: 16.60
		},
		//30日后留存
		d_30:{
			device_count: 10,
			device_rate: 8.30
		}
	}
}
```



## uni统计 - 页面统计结果表 uni-stat-page-result

用于统计客户端的页面访问情况

### 字段说明

|   字段名			|  类型			|  默认值	|            说明															|
| :--------:		| :-----:		|:---------:| :-------------------:														|
|   _id				| string		|     -		|  ID，系统自动生成															|
|  appid			| string		|     -		|  统计应用ID，对应opendb-app-list.appid									|
|  platform_id		| string		|     -		|  应用平台ID，对应uni-stat-app-platforms._id								|
|  channel_id		| string		|     -		|  渠道/场景值ID，对应uni-stat-app-channels._id								|
|  version_id		| string		| -			|  应用版本ID，对应uni-stat-app-versions._id								|
|  page_id			|   string		| -			|  页面表ID，对应uni-stat-app-pages._id										|
|  visit_times		|   int			|     -		|  访问次数																	|
|  visit_users		|   int			|     -		|  访问登录用户数															|
|  visit_devices	|   int			|     -		|  访问设备数																|
|  exit_times		|   int			|     -		|  从当前页面退出次数														|
|  duration			|   int			|     -		|  访问总时长,单位秒														|
|  share_count		|   int			|     -		|  分享次数																	|
|  entry_users		|   int			|     -		|  当前页作为入口页的用户数													|
|  entry_devices	|   int			|     -		|  当前页作为入口页的设备数													|
|  entry_count		|   int			|     -		|  当前页作为入口页的总次数													|
|  entry_duration	|   int			|     -		|  当前页作为入口时，本页面的总访问时长,单位秒								|
|  bounce_times		|   int			|     -		|  跳出次数																	|
|  bounce_rate		|   double		|     -		|  跳出率																	|
|  dimension		|   string		|     -		|  统计范围 day:按天统计，hour:按小时统计, week：按周统计，month：按月统计	|
|  stat_date		|   int			|     -		|  统计日期，格式yyyymmdd，例:20211201										|
|  start_time		|   timestamp	|     -		|  开始时间																	|
|  end_time			|   timestamp	|     -		|  结束时间																	|


## uni统计 - 事件统计结果表 uni-stat-event-result

用于统计客户端的事件触发频率

### 字段说明

|   字段名		|  类型			|   默认值		|            说明															|
| :--------:	| :-----:		|:------------:	| :-------------------:														|
|   _id			| string		|   -			|  ID，系统自动生成															|
|  appid		| string		|     -			|  统计应用ID，对应opendb-app-list.appid									|
|  platform_id	| string		|     -			|  应用平台ID，对应uni-stat-app-platforms._id								|
|  channel_id	| string		|     -			|  渠道/场景值ID，对应uni-stat-app-channels._id								|
|  version_id	| string		| -				| 应用版本ID，对应uni-stat-app-versions._id									|
|  event_key	|   string		| -				|  事件key																	|
|  event_count	|   int			|     -			|  触发次数																	|
|  user_count	|   int			|     -			|  触发该事件的用户数														|
|  device_count	|   int			|     -			|  触发该事件的设备数														|
|  dimension	|   string		|     -			|  统计范围 day:按天统计，hour:按小时统计, week：按周统计，month：按月统计	|
|  stat_date	|   int			|     -			|  统计日期，格式yyyymmdd，例:20211201										|
|  start_time	|   timestamp	|     -			|  开始时间																	|
|  end_time		|   timestamp	|     -			|  结束时间																	|


## uni统计 - 错误数据统计结果表 uni-stat-error-result

用于统计客户端的错误信息

### 字段说明

|   字段名		|  类型			|     默认值	|            说明															|
| :--------:	| :-----:		|:-------------:| :-------------------:														|
|   _id			| string		|  -			|  ID，系统自动生成															|
|  appid		| string		|  -			|  统计应用ID，对应opendb-app-list.appid									|
|  platform_id	| string		|  -			|  应用平台ID，对应uni-stat-app-platforms._id								|
|  channel_id	| string		|  -			|  渠道/场景值ID，对应uni-stat-app-channels._id								|
|  version_id	| string		|  -			|  应用版本ID，对应uni-stat-app-versions._id								|
|  hash			| string		|  -			|  错误hash码																|
|  msg			| string		|  -			|  错误信息																	|
|  count		| int			|  -			|  报错次数																	|
|  last_time	| timestamp		|  -			|  最近一次报错时间															|
|  dimension	|   string		|     -			|  统计范围 day:按天统计，hour:按小时统计, week：按周统计，month：按月统计	|
|  stat_date	|   int			|  -			|  统计日期，格式yyyymmdd，例:20211201										|
|  start_time	|   timestamp	|  -			|  开始时间																	|
|  end_time		|   timestamp	|  -			|  结束时间																	|



## uni统计 - 忠诚度（粘性）统计结果表 uni-stat-loyalty-result

用于分析用户粘性

### 字段说明

|   字段名			|  类型			|     默认值	|            说明								|
| :--------:		| :-----:		|:-------------:| :-------------------:							|
|   _id				| string		|  -			|  ID，系统自动生成								|
|  appid			| string		|  -			|  统计应用ID，对应opendb-app-list.appid		|
|  platform_id		| string		|  -			|  应用平台ID，对应uni-stat-app-platforms._id	|
|  channel_id		| string		|  -			|  渠道/场景值ID，对应uni-stat-app-channels._id	|
|  version_id		| string		|  -			|  应用版本ID，对应uni-stat-app-versions._id	|
|  visit_depth_data	| object		|  -			|  访问深度（页面数量）数据						|
|  duration_data	| object		|  -			|  访问时长数据									|
|  stat_date		|   int			|  -			|  统计日期，格式yyyymmdd，例:20211201			|
|  start_time		|   timestamp	|  -			|  开始时间										|
|  end_time			|   timestamp	|  -			|  结束时间										|


- visit_depth_data 访问深度数据字段结构说明：
``` json
{
	//访问用户数
	visit_users:[
		//仅访问1个页面的总用户数
		p_1:1000,
		//仅访问2个页面的总用户数
		p_2:900,
		//仅访问3个页面的总用户数
		p_3:800,
		//仅访问4个页面的总用户数
		p_4:700,
		//访问5-10个页面的总用户数
		p_5:600,
		//访问10个以上页面的总用户数
		p_10:500
	],
	//访问设备数
	visit_devices:[
		//仅访问1个页面的总设备数
		p_1:1000,
		//仅访问2个页面的总设备数
		p_2:900,
		//仅访问3个页面的总设备数
		p_3:800,
		//仅访问4个页面的总设备数
		p_4:700,
		//访问5-10个页面的总设备数
		p_5:600,
		//访问10个以上页面的总设备数
		p_10:500
	],
	//访问次数
	visit_times:[
		//仅访问1个页面的总访问次数
		p_1:1000,
		//仅访问2个页面的总访问次数
		p_2:900,
		//仅访问3个页面的总访问次数
		p_3:800,
		//仅访问4个页面的总访问次数
		p_4:700,
		//访问5-10个页面的总访问次数
		p_5:600,
		//访问10个以上页面的总访问次数
		p_10:500
	]
}
```


- duration_data 访问时长数据字段结构说明：
``` json
{
	//访问用户数
	visit_users:{
		//仅访问0-2秒就退出的总用户数
		s_:1000,
		//仅访问3-5秒就退出的总用户数
		s_3:900,
		//仅访问6-10秒就退出的总用户数
		s_6:800,
		//仅访问11-20秒就退出的总用户数
		s_11:700,
		//访问21-30秒退出的总用户数
		s_21:600,
		//访问31-50秒退出的总用户数
		s_31:500,
		//访问51-100秒退出的总用户数
		s_51:400,
		//访问100秒以上退出的总用户数
		s_100:300
	},
	//访问设备数
	visit_devices:{
		//仅访问0-2秒就退出的总设备数
		s_:1000,
		//仅访问3-5秒就退出的总设备数
		s_3:900,
		//仅访问6-10秒就退出的总设备数
		s_6:800,
		//仅访问11-20秒就退出的总设备数
		s_11:700,
		//访问21-30秒退出的总设备数
		s_21:600,
		//访问31-50秒退出的总设备数
		s_31:500,
		//访问51-100秒退出的总设备数
		s_51:400,
		//访问100秒以上退出的总设备数
		s_100:300
	},
	//访问次数
	visit_times:{
		//仅访问0-2秒就退出的总访问次数
		s_0:1000,
		//仅访问3-5秒就退出的总访问次数
		s_3:900,
		//仅访问6-10秒就退出的总访问次数
		s_6:800,
		//仅访问11-20秒就退出的总访问次数
		s_11:700,
		//访问21-30秒退出的总访问次数
		s_21:600,
		//访问31-50秒退出的总访问次数
		s_31:500,
		//访问51-100秒退出的总访问次数
		s_51:400,
		//访问100秒以上退出的总访问次数
		s_100:300
	}
}
```

## uni统计- 活跃设备表 uni-stat-active-devices

由每日跑批合并，仅添加当日新增设备，以及本周或本月首次访问的老设备，该数据供周统计/月统计使用。

- 解决问题：直接通过日志数据查询获取周/月维度的设备数量可能会因为数据量过大而造成查询超时

### 字段说明

|   字段名		|  类型		|    默认值	|            说明									|
| :--------:	| :-----:	|:---------:| :-------------------:								|
|   _id			| string	|    -		|     ID，系统自动生成								|
|  appid		| string	|     -		|     统计应用ID，对应opendb-app-list.appid			|
|  platform_id	| string	|     -		|   应用平台ID，对应uni-stat-app-platforms._id		|
|  channel_id	| string	|     -		|    渠道/场景值ID，对应uni-stat-app-channels._id	|
|  version_id	| string	| -			|  应用版本ID，对应uni-stat-app-versions._id		|
|  device_id	| string	| -			| 客户端携带的设备标识								|
|  is_new		| int		|  0		|  是否为新设备，0否 1是							|
|  dimension	| string	|  week		| 时间范围  week：周，month：月						|
|  create_time	| timestamp	|  -		|  创建时间											|

## uni统计- 活跃用户表 uni-stat-active-users

由每日跑批合并，仅添加当日新增用户，以及本周或本月首次访问的老用户，该数据供周统计/月统计使用。

- 解决问题：直接通过日志数据查询获取周/月维度的用户数量可能会因为数据量过大而造成查询超时

### 字段说明

|   字段名		|  类型		|    默认值	|            说明									|
| :--------:	| :-----:	|:---------:| :-------------------:								|
|   _id			| string	|    -		|     ID，系统自动生成								|
|  appid		| string	|     -		|     统计应用ID，对应opendb-app-list.appid			|
|  platform_id	| string	|     -		|   应用平台ID，对应uni-stat-app-platforms._id		|
|  channel_id	| string	|     -		|    渠道/场景值ID，对应uni-stat-app-channels._id	|
|  version_id	| string	| -			|  应用版本ID，对应uni-stat-app-versions._id		|
|  uid			| string	| -			| 客户端上报的用户编号								|
|  dimension	| string	|  week		| 时间范围  week：周，month：月						|
|  create_time	| timestamp	|  -		|  创建时间											|



## uni统计- 运行错误记录表 uni-stat-run-errors

uni统计发生错误时可以通过该日志排查问题，恢复数据

### 字段说明

|   字段名		|  类型		|    默认值	|            说明		|
| :--------:	| :-----:	|:---------:| :-------------------:	|
|   _id			| string	|  -		|  ID，系统自动生成		|
|  mod			| string	|  -		|  运行模块				|
|  params		| object	|  -		|  运行参数				|
|  error		| string	|  -		|  错误信息				|
|  create_time	| timestamp	|  -		|  创建时间				|


## uni统计-原生应用崩溃日志表 uni-stat-app-crash-logs

### 字段说明

|字段名						|类型		|默认值			|            说明																	|
| :--------:				| :-----:	|:-----------:	| :-------------------:																|
| _id						| string	| -				| ID，系统自动生成																	|
| appid						| string	| -				| 客户端携带的应用ID																|
| version					| string	| -				| 客户端上报的应用版本号															|
| platform					| string	| -				| 平台android\/ios																	|
| channel					| string	| -				| 客户端上报的渠道code\/场景值														|
| sdk_version				| string	| -				| 基础库版本号																		|
| device_id					| string	| -				| 客户端携带的设备标识																|
| device_net				| string	| -				| 设备网络型号wifi\/3G\/4G\/														|
| device_os					| string	| -				| 系统版本：iOS平台为系统版本号，如15.1；Android平台为API等级，如30					|
| device_os_version			| string	| -				| 系统版本名称：iOS平台与os字段一致；Android平台为版本名称，如5.1.1					|
| device_vendor				| string	| -				| 设备供应商																		|
| device_model				| string	| -				| 设备型号																			|
| device_is_root			| int		| -				| 是否root：1表示root；0表示未root													|
| device_os_name			| string	| -				| 系统名称：用于区别Android和鸿蒙，仅Android支持									|
| device_batt_level			| int		| -				| 设备电池电量：取值范围0-100，仅Android支持										|
| device_batt_temp			| string	| -				| 电池温度，仅Android支持															|
| device_memory_use_size	| int		| -				| 系统已使用内存，单位为Byte，仅Android支持											|
| device_memory_total_size	| int		| -				| 系统总内存，单位为Byte，仅Android支持												|
| device_disk_use_size		| int		| -				| 系统磁盘已使用大小，单位为Byte，仅Android支持										|
| device_disk_total_size	| int		| -				| 系统磁盘总大小，单位为Byte，仅Android支持											|
| device_abis				| string	| -				| 设备支持的CPU架构：多个使用,分割，如arm64-v8a,armeabi-v7a,armeabi，仅Android支持	|
| app_count					| int		| -				| 运行应用的个数																	|
| app_use_memory_size		| int		| -				| APP使用的内存量，单位为Byte														|
| app_webview_count			| int		| -				| 打开Webview窗口的个数																|
| app_use_duration			| int		| -				| APP使用时长：单位为s																|
| app_run_fore				| int		| -				| 是否前台运行：1表示前台运行，0表示后台运行										|
| package_name				| string	| -				| 原生应用包名																		|
| package_version			| string	| -				| Android的apk版本名称；iOS的ipa版本名称											|
| page_url					| string	| -				| 页面url																			|
| error_msg					| string	| -				| 错误信息																			|
| create_time				| timestamp	| -				| 创建时间																			|
