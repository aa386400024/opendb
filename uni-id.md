## 用户表

表名：uni-id-users

| 字段             | 类型      | 必填 | 描述                                        |
| ---------------- | --------- | ---- | ------------------------------------------- |
| \_id             | Object ID | 是   | 存储文档 ID（用户 ID），系统自动生成        |
| username         | String    | 是   | 用户名，不允许重复                          |
| password         | String    | 否   | 密码，加密存储                              |
| nickname         | String    | 否   | 用户昵称                                    |
| gender           | Integer   | 否   | 用户性别：0 未知 1 男性 2 女性              |
| status           | Integer   | 是   | 用户状态：0 正常 1 禁用 2 审核中 3 审核拒绝 |
| mobile           | String    | 否   | 手机号码                                    |
| mobile_confirmed | Integer   | 否   | 手机号验证状态：0 未验证 1 已验证           |
| email            | String    | 否   | 邮箱地址                                    |
| email_confirmed  | Integer   | 否   | 邮箱验证状态：0 未验证 1 已验证             |
| avatar           | String    | 否   | 头像地址                                    |
| wx_unionid       | String    | 否   | 微信unionid                                 |
| wx_openid        | Object    | 否   | 微信各个平台openid                           |
| ali_openid       | String    | 否   | 支付宝平台openid                           |
| comment          | String    | 否   | 备注                                        |
| realname_auth    | Object    | 否   | 实名认证信息                                |
| register_date    | Timestamp | 否   | 注册时间                                    |
| register_ip      | String    | 否   | 注册时 IP 地址                              |
| last_login_date  | Timestamp | 否   | 最后登录时间                                |
| last_login_ip    | String    | 否   | 最后登录时 IP 地址                          |

**realNameAuth 字段定义**

| 字段            | 类型      | 必填 | 描述                                                |
| --------------- | --------- | ---- | --------------------------------------------------- |
| type            | Integer   | 是   | 用户类型：0 个人用户 1 企业用户                     |
| auth_status     | Integer   | 是   | 认证状态：0 未认证 1 等待认证 2 认证通过 3 认证失败 |
| auth_date       | Timestamp | 否   | 认证通过时间                                        |
| real_name       | String    | 否   | 真实姓名/企业名称                                   |
| identity        | String    | 否   | 身份证号码/营业执照号码                             |
| id_card_front   | String    | 否   | 身份证正面照 URL                                    |
| id_card_back    | String    | 否   | 身份证反面照 URL                                    |
| id_card_in_hand | String    | 否   | 手持身份证照片 URL                                  |
| license         | String    | 否   | 营业执照 URL                                        |
| contact_person  | String    | 否   | 联系人姓名                                          |
| contact_mobile  | String    | 否   | 联系人手机号码                                      |
| contact_email   | String    | 否   | 联系人邮箱                                          |

**wx_openid字段定义**

| 字段    | 类型   | 必填 | 描述     |
| ------- | ------ | ---- | -------- |
| app-plus | String | 否   | app平台微信openid |
| mp-weixin| String | 否   | 微信小程序平台openid  |

**job 字段定义**

| 字段    | 类型   | 必填 | 描述     |
| ------- | ------ | ---- | -------- |
| company | String | 否   | 公司名称 |
| title   | String | 否   | 职位     |
