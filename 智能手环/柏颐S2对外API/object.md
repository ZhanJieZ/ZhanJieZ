
对象定义 
========

__目录__

-  [AbnormalData](#abnormaldata)  异常数据
-  [Advert](#advert)  广告推广
-  [App](#app)  应用
-  [Auth](#auth)  第三方认证信息
-  [BloodPressureData](#bloodpressuredata)  血压数据
-  [CELL](#cell)  基站标识
-  [CasePage](#casepage)  用户病例
-  [Community](#community)  社区
-  [CommunityInviteMessage](#communityinvitemessage)  社区邀请消息
-  [CommunityJoinMessage](#communityjoinmessage)  社区加入申请
-  [CommunityLeaveMessage](#communityleavemessage)  社区离开申请
-  [CommunityMessage](#communitymessage)  社区系统消息
-  [CommunityNotification](#communitynotification)  社区通知
-  [Device](#device)  设备信息
-  [DeviceToken](#devicetoken)  终端标识
-  [EmailConfirm](#emailconfirm)  Email确认
-  [ExpertPage](#expertpage)  专家资源
-  [Group](#group)  分组
-  [GroupInviteCode](#groupinvitecode)  小组邀请消息
-  [GroupNotification](#groupnotification)  家庭圈通知
-  [HeartRateData](#heartratedata)  心率数据
-  [HeartRateNotification](#heartratenotification)  心率异常通知消息
-  [Imei](#imei)  IMEI号码
-  [LocationCache](#locationcache)  坐标位置缓存
-  [LocationData](#locationdata)  定位数据
-  [LocationNotification](#locationnotification)  位置异常通知消息
-  [MediaData](#mediadata)  通过upload上传的媒体数据
-  [MediaMessage](#mediamessage)  媒体消息
-  [MediaPage](#mediapage)  媒体资源
-  [Member](#member)  小组成员
-  [Message](#message)  好友消息
-  [MsgNotification](#msgnotification)  Message通知消息
-  [Notification](#notification)  推送通知
-  [NotificationService](#notificationservice)  推送服务
-  [Page](#page)  资源分享
-  [PageComment](#pagecomment)  评论
-  [PageStar](#pagestar)  点赞
-  [PasswordResetNotify](#passwordresetnotify)  Email口令重设通知
-  [PasswordResetRequest](#passwordresetrequest)  Email口令重设确认
-  [PedometerData](#pedometerdata)  计步数据
-  [Person](#person)  人员信息
-  [PostureData](#posturedata)  姿势数据
-  [PowerData](#powerdata)  开机数据
-  [PowerNotification](#powernotification)  低电通知
-  [RegisterRequest](#registerrequest)  Email注册确认
-  [RfidData](#rfiddata)  到家数据
-  [SedentaryData](#sedentarydata)  久坐数据
-  [ServicePage](#servicepage)  用户服务
-  [SettingAlert](#settingalert)  事件提醒
-  [SettingFence](#settingfence)  围栏
-  [SettingSosNumber](#settingsosnumber)  亲情号码
-  [ShortMessage](#shortmessage)  短信发送任务
-  [ShortMessageChecksum](#shortmessagechecksum)  短信验证码发送任务
-  [ShortMessageSos](#shortmessagesos)  呼救短信发送任务
-  [SimPhone](#simphone)  SIM号码
-  [SleepData](#sleepdata)  睡眠数据
-  [SleepDataSleep](#sleepdatasleep)  数据
-  [SosData](#sosdata)  呼叫数据
-  [SosNotification](#sosnotification)  Sos通知消息
-  [SysMessage](#sysmessage)  系统消息
-  [TextMessage](#textmessage)  文本消息
-  [TextPage](#textpage)  文本资源
-  [UploadFile](#uploadfile)  文件管理
-  [WIFI](#wifi)  基站标识
-  [WearData](#weardata)  佩戴数据
-  [WeatherCache](#weathercache)  天气缓存



# abnormaldata

异常数据(暂时废弃)

| 字段名 | 说明 | 类型 | 最小长度 | 最大长度 | 必填字段 | 缺省值 | 备注 |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| user | 用户 | Reference: [Person](#person) |  |  | False | None |  |
| device | 设备 | Reference: [Device](#device) |  |  | False | None |  |
| created_at | 记录时间 | DateTime |  |  | False | now() |  |
| time_begin | 发生时间 | DateTime |  |  | False | None |  |
| abnormal_type | 异常类型 | Int |  |  | False | 0 |  |
| abnormal_code | 异常编号 | Int |  |  | False | 0 |  |


# advert

广告推广

| 字段名 | 说明 | 类型 | 最小长度 | 最大长度 | 必填字段 | 缺省值 | 备注 |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| text | 内容 | String | 1 | 200 | True |  |  |
| communitys | 投放社区 | List: Reference [Community](#community) |  |  | False |  |  |
| created_at | 创建时间 | DateTime |  |  | True | now() |  |


# app

应用

| 字段名 | 说明 | 类型 | 最小长度 | 最大长度 | 必填字段 | 缺省值 | 备注 |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| name | 名称 | String |  |  | True | None |  |
| cname | 中文名 | String |  |  | False |  |  |
| company | 公司名 | String |  |  | False |  |  |
| ios_aid | 信鸽 IOS accessid | Int |  |  | False | 0 |  |
| ios_skey | 信鸽 IOS secretkey | String |  |  | False |  |  |
| android_aid | 信鸽 Android accessid | Int |  |  | False | 0 |  |
| android_skey | 信鸽 Android secretkey | String |  |  | False |  |  |
| sos_message_enable | Sos短信发送 | Boolean |  |  | False | False |  |
| created_at | 创建时间 | DateTime |  |  | True | now() |  |


# auth

第三方认证信息  -- 内嵌对象

| 字段名 | 说明 | 类型 | 最小长度 | 最大长度 | 必填字段 | 缺省值 | 备注 |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |


# bloodpressuredata

血压数据

| 字段名 | 说明 | 类型 | 最小长度 | 最大长度 | 必填字段 | 缺省值 | 备注 |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| user | 用户 | Reference: [Person](#person) |  |  | False | None |  |
| device | 设备 | Reference: [Device](#device) |  |  | False | None |  |
| created_at | 记录时间 | DateTime |  |  | False | now() |  |
| time_begin | 发生时间 | DateTime |  |  | False | None |  |
| dbp | 收缩压 | Int |  |  | False | 0 |  |
| sbp | 舒张压 | Int |  |  | False | 0 |  |


# cell

基站标识  -- 内嵌对象

| 字段名 | 说明 | 类型 | 最小长度 | 最大长度 | 必填字段 | 缺省值 | 备注 |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| mcc | MCC | String |  | 3 | False | 000 |  |
| mnc | MNC | String |  | 3 | False | 000 |  |
| lac | LAC | Int |  |  | False | 0 |  |
| cid | CELLID | Int |  |  | False | 0 |  |
| rssi | RSSI | Int |  |  | False | 0 |  |


# casepage

用户病例(暂时废弃)

| 字段名 | 说明 | 类型 | 最小长度 | 最大长度 | 必填字段 | 缺省值 | 备注 |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| group | 拥有组 | Reference: [Group](#group) |  |  | False | None |  |
| created_by | 创建人 | Reference: [Person](#person) |  |  | False | None |  |
| created_at | 创建时间 | DateTime |  |  | True | now() |  |
| updated_at | 更新时间 | DateTime |  |  | True | now() |  |
| subject | 标题 | String |  | 64 | False |  |  |
| type | 资源类型(新增) | String |  |  | True | text | text:text; photo:photo; voice:voice; other:other |
| comments | 评论 | List: Embedded [PageComment](#pagecomment) |  |  | False |  |  |
| stars | 赞 | List: Embedded [PageStar](#pagestar) |  |  | False |  |  |
| user | 病历用户 | Reference: [Person](#person) |  |  | False | None |  |
| happen_at | 发生时间 | DateTime |  |  | True | now() |  |
| body | 病历内容 | String |  | 4096 | False | None |  |


# community

社区

| 字段名 | 说明 | 类型 | 最小长度 | 最大长度 | 必填字段 | 缺省值 | 备注 |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| name | 社区名称 | String |  |  | True | None |  |
| email | 企业邮箱 | Email |  | 64 | True | None |  |
| telephone | 客服电话 | String |  | 15 | False |  |  |
| administrators | 社区管理员 | List: Reference [Person](#person) |  |  | False |  |  |
| created_at | 创建时间 | DateTime |  |  | False | now() |  |


# communityinvitemessage

社区邀请消息

| 字段名 | 说明 | 类型 | 最小长度 | 最大长度 | 必填字段 | 缺省值 | 备注 |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| subject | 标题 | String |  | 128 | False |  |  |
| type | 消息类型 | String |  | 16 | False | open | community_invite:邀请加入社区; community_join:申请加入社区; community_leave:申请退出社区 |
| sender | 发起用户 | Reference: [Person](#person) |  |  | False | None |  |
| sender_note | 发起留言 | String |  |  | False |  |  |
| recipient | 接收用户 | Reference: [Person](#person) |  |  | False | None |  |
| created_at | 发起时间 | DateTime |  |  | False | now() |  |
| result | 处理结果 | String |  | 16 | False | open | open:待处理; expired:过期; cancel:取消; accept:接受; reject:拒绝; close:结束 |
| accept_at | 结束时间 | DateTime |  |  | False | None |  |
| recipient_note | 接收人留言 | String |  |  | False |  |  |
| community | 社区 | Reference: [Community](#community) |  |  | False | None |  |


# communityjoinmessage

社区加入申请

| 字段名 | 说明 | 类型 | 最小长度 | 最大长度 | 必填字段 | 缺省值 | 备注 |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| subject | 标题 | String |  | 128 | False |  |  |
| type | 消息类型 | String |  | 16 | False | open | community_invite:邀请加入社区; community_join:申请加入社区; community_leave:申请退出社区 |
| sender | 发起用户 | Reference: [Person](#person) |  |  | False | None |  |
| sender_note | 发起留言 | String |  |  | False |  |  |
| recipient | 接收用户 | Reference: [Person](#person) |  |  | False | None |  |
| created_at | 发起时间 | DateTime |  |  | False | now() |  |
| result | 处理结果 | String |  | 16 | False | open | open:待处理; expired:过期; cancel:取消; accept:接受; reject:拒绝; close:结束 |
| accept_at | 结束时间 | DateTime |  |  | False | None |  |
| recipient_note | 接收人留言 | String |  |  | False |  |  |
| community | 社区 | Reference: [Community](#community) |  |  | False | None |  |


# communityleavemessage

社区离开申请

| 字段名 | 说明 | 类型 | 最小长度 | 最大长度 | 必填字段 | 缺省值 | 备注 |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| subject | 标题 | String |  | 128 | False |  |  |
| type | 消息类型 | String |  | 16 | False | open | community_invite:邀请加入社区; community_join:申请加入社区; community_leave:申请退出社区 |
| sender | 发起用户 | Reference: [Person](#person) |  |  | False | None |  |
| sender_note | 发起留言 | String |  |  | False |  |  |
| recipient | 接收用户 | Reference: [Person](#person) |  |  | False | None |  |
| created_at | 发起时间 | DateTime |  |  | False | now() |  |
| result | 处理结果 | String |  | 16 | False | open | open:待处理; expired:过期; cancel:取消; accept:接受; reject:拒绝; close:结束 |
| accept_at | 结束时间 | DateTime |  |  | False | None |  |
| recipient_note | 接收人留言 | String |  |  | False |  |  |
| community | 社区 | Reference: [Community](#community) |  |  | False | None |  |


# communitymessage

社区系统消息

| 字段名 | 说明 | 类型 | 最小长度 | 最大长度 | 必填字段 | 缺省值 | 备注 |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| subject | 标题 | String |  | 128 | False |  |  |
| type | 消息类型 | String |  | 16 | False | open | community_invite:邀请加入社区; community_join:申请加入社区; community_leave:申请退出社区 |
| sender | 发起用户 | Reference: [Person](#person) |  |  | False | None |  |
| sender_note | 发起留言 | String |  |  | False |  |  |
| recipient | 接收用户 | Reference: [Person](#person) |  |  | False | None |  |
| created_at | 发起时间 | DateTime |  |  | False | now() |  |
| result | 处理结果 | String |  | 16 | False | open | open:待处理; expired:过期; cancel:取消; accept:接受; reject:拒绝; close:结束 |
| accept_at | 结束时间 | DateTime |  |  | False | None |  |
| recipient_note | 接收人留言 | String |  |  | False |  |  |
| community | 社区 | Reference: [Community](#community) |  |  | False | None |  |


# communitynotification

社区通知

| 字段名 | 说明 | 类型 | 最小长度 | 最大长度 | 必填字段 | 缺省值 | 备注 |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| token_type | 终端类型 | String |  | 16 | True | ios | ios:ios; android:android |
| token | 设备标识 | String |  | 128 | False | None |  |
| title | 标题 | String |  | 16 | True | None |  |
| content | 内容 | String |  | 256 | True | None |  |
| group | 关键组 | Reference: [Group](#group) |  |  | False | None |  |
| recipient | 接收人 | Reference: [Person](#person) |  |  | True | None |  |
| created_at | 提交时间 | DateTime |  |  | True | now() |  |
| updated_at | 更新时间 | DateTime |  |  | True | now() |  |
| expired_at | 过期时间 | DateTime |  |  | True |  |  |
| sched_send_at | 预期发送时间 | DateTime |  |  | True | now() |  |
| error_code | 返回码 | Int |  |  | False | None |  |
| error_info | 返回信息 | String |  |  | False | None |  |
| is_completed | 已完成 | Boolean |  |  | True | False |  |
| is_cleared | 已清除 | Boolean |  |  | True | False |  |


# device

设备信息

| 字段名 | 说明 | 类型 | 最小长度 | 最大长度 | 必填字段 | 缺省值 | 备注 |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| did | 设备编号 | String |  | 64 | True | None |  |
| alerts | 提醒 | List: Embedded [SettingAlert](#settingalert) |  |  | False |  |  |
| sos_numbers | 亲情号码 | List: Embedded [SettingSosNumber](#settingsosnumber) |  |  | False |  |  |
| sos_dial_cycle_times | 轮播次数1-9 | Int |  |  | True | 1 | SOS出发以后拨打SOS号码的循环次数,9是无限循环 |
| sos_sendmail | 紧急呼叫是否发送短信 | Boolean |  |  | True | False | 废弃 |
| sos_readmail | 紧急呼叫短信是否自动弹出 | Boolean |  |  | True | False | 废弃 |
| sos_dial_cycle_mode | 轮播模式 | Int |  |  | True | 0 | 0，仅拨打SOS号码，1先打SOS再打服务号，2先拨打服务号再拨打SOS，3仅拨打服务号 |
| frequency_location | 位置上报频率 | Int |  |  | True | 30 | 单位分钟，不建议低于10min |
| frequency_step | 记步上报频率 | Int |  |  | True | 30 | 单位分钟，不建议低于10mi |
| frequency_heartrate | 心率上报频率 | Int |  |  | True | 30 | 单位分钟，不建议低于10mi |
| theshold_heartrate_h | 心率上限 | Int |  |  | True | 140 |  |
| theshold_heartrate_l | 心率下限 | Int |  |  | True | 40 |  |
| incoming_restriction | 呼入限制 | Boolean |  |  | True | False |  |
| bluetooth_enable | 蓝牙开关 | Boolean |  |  | True | False | 仅在适配好的血压计同步功能上有用 |
| bluetooth_devices | 蓝牙设备 | String |  | 256 | True |  | 暂时废弃 |
| profile | 情景模式 | Int |  |  | True | 0 | 0铃声，1震动，2震动+铃声，3无震无声；S2系列无震动，曲奇有 |
| sleep_period_begin | 睡眠开始时间 | String |  | 14 | True |  | 格式YYYYMMDDHHMMSS，其中YYYYMMDD都用0填充，实例00000000083000,8点30am |
| sleep_period_end | 睡眠结束时间 | String |  | 14 | True |  | 同上 |
| step_objective | 计步目标 | Int |  |  | True | 3000 |  |
| theshold_sit | 久坐门限 | Int |  |  | True | 60 |  |
| theshold_low_battery | 低电门限 | Int |  |  | True | 20 |  |
| fences | 电子围栏 | List: Embedded [SettingFence](#settingfence) |  |  | False |  |  |
| pedometer_enable | 计步数据开关 | Boolean |  |  | False | False |  |
| sleep_enable | 睡眠数据开关 | Boolean |  |  | False | False |  |
| imei | 移动设备识别码 | String |  | 16 | False |  |  |
| imsi | 移动用户识别码 | String |  | 16 | False |  |  |
| type | 设备类型 | String |  | 20 | False | BY102 |  |
| sim_phone | 移动用户卡号 | String |  | 16 | False |  |  |
| sim_phone_type | 移动用户卡类型 | String |  | 8 | False | unicom | unicom:中国联通; cmcc:中国移动; ctcc:中国电信 |
| owner | 拥有人 | Reference: [Person](#person) |  |  | False | None |  |
| name | 设备名称 | String |  | 32 | False |  |  |
| created_at | 创建时间 | DateTime |  |  | True | now() |  |
| updated_at | 更新时间 | DateTime |  |  | True | now() |  |
| lastlogin_ip | 最近联网地址 | String |  | 16 | False |  |  |
| lastlogin_at | 最近联网时间 | DateTime |  |  | False | now() |  |
| active | 激活状态 | Boolean |  |  | True | False |  |
| active_at | 首次激活时间 | DateTime |  |  | False | None |  |
| online | 联网状态 | Boolean |  |  | True | False |  |
| location_updated | 坐标更新 | Boolean |  |  | True | False |  |
| location_updated_at | 坐标更新时间 | DateTime |  |  | True |  |  |
| last_location | 最新坐标 | Point |  |  | True |  |  |
| last_city | 城市 | String |  |  | True |  |  |
| last_address | 地址 | String |  |  | True |  |  |
| wear_flag | 佩戴状态 | Int |  |  | False | None |  |
| wear_updated_at | 佩戴状态更新时间 | DateTime |  |  | False | None | 0未佩戴，1已佩戴，仅在测量心率的时候更新状态，终端自己测量不会更新 |
| remaining_power | 剩余电量(%） | Int |  |  | False | 0 |  |
| remaining_power_updated_at | 电量状态更新时间 | DateTime |  |  | False | None |  |
| wifi | WIFI | List: Embedded [WIFI](#wifi) |  |  | False |  |  |
| wifi_updated_at | WIFI更新时间 | DateTime |  |  | False | None |  |
| software_version | 软件版本 | String |  | 48 | False |  |  |
| iccid1 | 移动用户iccid号1 | String |  | 21 | False | None |  |
| iccid2 | 移动用户iccid号2 | String |  | 21 | False | None |  |
| fence_notification_updated_at | 围栏通知更新时间 | DateTime |  |  | False | None |  |
| service_number | 服务号 | String |  | 32 | False | None | 暂时废弃 |
| fall_model | 跌倒模式设置 | String |  |  | False | 0 | 0无短信、电话 1仅短信 2仅电话 3短信+电话，跌倒仅曲奇手机有 |
| fall_enable | 跌倒判断开关 | Boolean |  |  | False | 0 | 跌倒仅曲奇手机有 |
| track_enable | 轨迹开关 | Boolean |  |  | False | 0 | 曲奇和S2纯定位版有 |



# devicetoken

终端标识  -- 内嵌对象

| 字段名 | 说明 | 类型 | 最小长度 | 最大长度 | 必填字段 | 缺省值 | 备注 |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| token_type | 设备类型 | String |  | 10 | True | ios | ios:ios; android:android |
| token | 设备标识 | String |  | 128 | True | None |  |
| is_enable_aliase | 别名是否可用 | Boolean |  |  | True | False |  |
| created_at | 创建时间 | DateTime |  |  | True | now() |  |


# emailconfirm

Email确认

| 字段名 | 说明 | 类型 | 最小长度 | 最大长度 | 必填字段 | 缺省值 | 备注 |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| person | 发送用户 | Reference: [Person](#person) |  |  | False | None |  |
| email | 注册邮箱 | Email |  | 64 | True | None |  |
| created_at | 申请时间 | DateTime |  |  | False | now() |  |
| send_at | 发送时间 | DateTime |  |  | False | None |  |
| send_ok | 发送结果 | Boolean |  |  | False | None |  |
| send_error | 失败信息 | String |  |  | False | None |  |
| accept_at | 确认时间 | DateTime |  |  | False | None |  |


# expertpage

专家资源

| 字段名 | 说明 | 类型 | 最小长度 | 最大长度 | 必填字段 | 缺省值 | 备注 |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| group | 拥有组 | Reference: [Group](#group) |  |  | False | None |  |
| created_by | 创建人 | Reference: [Person](#person) |  |  | False | None |  |
| created_at | 创建时间 | DateTime |  |  | True | now() |  |
| updated_at | 更新时间 | DateTime |  |  | True | now() |  |
| subject | 标题 | String |  | 64 | False |  |  |
| type | 资源类型(新增) | String |  |  | True | text | text:text; photo:photo; voice:voice; other:other |
| comments | 评论 | List: Embedded [PageComment](#pagecomment) |  |  | False |  |  |
| stars | 赞 | List: Embedded [PageStar](#pagestar) |  |  | False |  |  |
| is_published | 是否发布 | Boolean |  |  | False | True |  |
| body | 文章内容 | String |  | 4096 | False | None |  |
| filename | 图片文件名 | String |  | 64 | False | None |  |
| media_length | 文件长度 | Int |  |  | False | 0 |  |
| url | 图片下载地址 | String |  | 128 | False | None |  |
| thumb_url | 缩略图下载地址 | String |  | 128 | False | None |  |


# group

分组

| 字段名 | 说明 | 类型 | 最小长度 | 最大长度 | 必填字段 | 缺省值 | 备注 |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| owner | 拥有人 | Reference: [Person](#person) |  |  | True | None |  |
| name | 组名称 | String |  |  | True |  |  |
| community | 社区 | Reference: [Community](#community) |  |  | False | None |  |
| created_at | 创建时间 | DateTime |  |  | False | now() |  |
| is_public | 是否公开 | Boolean |  |  | False | False |  |
| members | 成员列表 | List: [Member](#member) |  |  | |  |  |


# groupinvitecode

小组邀请消息

| 字段名 | 说明 | 类型 | 最小长度 | 最大长度 | 必填字段 | 缺省值 | 备注 |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| date | 日期 | String |  | 16 | True |  |  |
| code | 邀请码 | String |  | 6 | True |  |  |
| target | 目标用户 | String |  |  | False | None |  |
| group | 邀请组 | Reference: [Group](#group) |  |  | False | None |  |
| created_by | 邀请人 | Reference: [Person](#person) |  |  | False | None |  |
| created_at | 提交时间 | DateTime |  |  | True | now() |  |
| updated_at | 更新时间 | DateTime |  |  | True | now() |  |
| expired_at | 过期时间 | DateTime |  |  | True |  |  |
| is_confirmed | 已确认 | Boolean |  |  | True | False |  |
| confirmed_by | 确认用户 | Reference: [Person](#person) |  |  | False | None |  |
| confirmed_at | 确认时间 | DateTime |  |  | False | None |  |


# groupnotification

家庭圈通知

| 字段名 | 说明 | 类型 | 最小长度 | 最大长度 | 必填字段 | 缺省值 | 备注 |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| token_type | 终端类型 | String |  | 16 | True | ios | ios:ios; android:android |
| token | 设备标识 | String |  | 128 | False | None |  |
| title | 标题 | String |  | 16 | True | None |  |
| content | 内容 | String |  | 256 | True | None |  |
| group | 关键组 | Reference: [Group](#group) |  |  | False | None |  |
| recipient | 接收人 | Reference: [Person](#person) |  |  | True | None |  |
| created_at | 提交时间 | DateTime |  |  | True | now() |  |
| updated_at | 更新时间 | DateTime |  |  | True | now() |  |
| expired_at | 过期时间 | DateTime |  |  | True |  |  |
| sched_send_at | 预期发送时间 | DateTime |  |  | True | now() |  |
| error_code | 返回码 | Int |  |  | False | None |  |
| error_info | 返回信息 | String |  |  | False | None |  |
| is_completed | 已完成 | Boolean |  |  | True | False |  |
| is_cleared | 已清除 | Boolean |  |  | True | False |  |
| member | 成员 | Reference: [Person](#person) |  |  | False | None |  |
| action | 事件 | String |  |  | True |  |  |


# heartratedata

心率数据

| 字段名 | 说明 | 类型 | 最小长度 | 最大长度 | 必填字段 | 缺省值 | 备注 |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| user | 用户 | Reference: [Person](#person) |  |  | False | None |  |
| device | 设备 | Reference: [Device](#device) |  |  | False | None |  |
| created_at | 记录时间 | DateTime |  |  | False | now() |  |
| time_begin | 发生时间 | DateTime |  |  | False | None |  |
| heartrate | 心率 | Int |  |  | False | 0 |  |


# heartratenotification

心率异常通知消息

| 字段名 | 说明 | 类型 | 最小长度 | 最大长度 | 必填字段 | 缺省值 | 备注 |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| token_type | 终端类型 | String |  | 16 | True | ios | ios:ios; android:android |
| token | 设备标识 | String |  | 128 | False | None |  |
| title | 标题 | String |  | 16 | True | None |  |
| content | 内容 | String |  | 256 | True | None |  |
| group | 关键组 | Reference: [Group](#group) |  |  | False | None |  |
| recipient | 接收人 | Reference: [Person](#person) |  |  | True | None |  |
| created_at | 提交时间 | DateTime |  |  | True | now() |  |
| updated_at | 更新时间 | DateTime |  |  | True | now() |  |
| expired_at | 过期时间 | DateTime |  |  | True |  |  |
| sched_send_at | 预期发送时间 | DateTime |  |  | True | now() |  |
| error_code | 返回码 | Int |  |  | False | None |  |
| error_info | 返回信息 | String |  |  | False | None |  |
| is_completed | 已完成 | Boolean |  |  | True | False |  |
| is_cleared | 已清除 | Boolean |  |  | True | False |  |
| data | 心率 | Reference: [HeartRateData](#heartratedata) |  |  | True | None |  |


# imei

IMEI号码

| 字段名 | 说明 | 类型 | 最小长度 | 最大长度 | 必填字段 | 缺省值 | 备注 |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| imei | 移动设备识别码 | String |  | 15 | True | None |  |
| deviceid | 设备序列号 | String |  | 20 | False | None |  |
| iccid | 移动用户iccid号 | String |  | 64 | False | None |  |
| update_at | 处理时间 | DateTime |  |  | False | now() |  |


# locationcache

坐标位置缓存

| 字段名 | 说明 | 类型 | 最小长度 | 最大长度 | 必填字段 | 缺省值 | 备注 |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| _id | id | String |  | 64 | True | None |  |
| cells | 地址 | String |  | 2048 | False | None |  |
| country | 国家 | String |  | 32 | False | None |  |
| region | 省份 | String |  | 32 | False | None |  |
| city | 城市 | String |  | 32 | False | None |  |
| county | 区域 | String |  | 32 | False | None |  |
| street | 街道 | String |  | 32 | False | None |  |
| street_number | 街道号 | String |  | 32 | False | None |  |
| address | 地址 | String |  | 512 | False | None |  |
| point | 坐标 | Point |  |  | False | None |  |
| accuracy | 精度 | Int |  |  | False | None |  |
| created_at | 创建时间 | DateTime |  |  | False | now() |  |


# locationdata

定位数据

| 字段名 | 说明 | 类型 | 最小长度 | 最大长度 | 必填字段 | 缺省值 | 备注 |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| user | 用户 | Reference: [Person](#person) |  |  | False | None |  |
| device | 设备 | Reference: [Device](#device) |  |  | False | None |  |
| created_at | 记录时间 | DateTime |  |  | False | now() |  |
| time_begin | 发生时间 | DateTime |  |  | False | None |  |
| type | 类型 | String |  |  | False | 0 | 0:Gps定位; 1:基站定位 |
| is_reply | 是否为响应 | Boolean |  |  | False | False |  |
| city | 城市 | String |  | 16 | False |  |  |
| address | 地址 | String |  | 128 | False |  |  |
| point | 坐标 | Point |  |  | False | None |  |
| cell | CELL | List: Embedded [CELL](#cell) |  |  | False |  |  |
| wifi | WIFI | List: Embedded [WIFI](#wifi) |  |  | False |  |  |


# locationnotification

位置异常通知消息

| 字段名 | 说明 | 类型 | 最小长度 | 最大长度 | 必填字段 | 缺省值 | 备注 |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| token_type | 终端类型 | String |  | 16 | True | ios | ios:ios; android:android |
| token | 设备标识 | String |  | 128 | False | None |  |
| title | 标题 | String |  | 16 | True | None |  |
| content | 内容 | String |  | 256 | True | None |  |
| group | 关键组 | Reference: [Group](#group) |  |  | False | None |  |
| recipient | 接收人 | Reference: [Person](#person) |  |  | True | None |  |
| created_at | 提交时间 | DateTime |  |  | True | now() |  |
| updated_at | 更新时间 | DateTime |  |  | True | now() |  |
| expired_at | 过期时间 | DateTime |  |  | True |  |  |
| sched_send_at | 预期发送时间 | DateTime |  |  | True | now() |  |
| error_code | 返回码 | Int |  |  | False | None |  |
| error_info | 返回信息 | String |  |  | False | None |  |
| is_completed | 已完成 | Boolean |  |  | True | False |  |
| is_cleared | 已清除 | Boolean |  |  | True | False |  |
| data | 位置 | Reference: [LocationData](#locationdata) |  |  | True | None |  |


# mediadata

通过upload上传的媒体数据

| 字段名 | 说明 | 类型 | 最小长度 | 最大长度 | 必填字段 | 缺省值 | 备注 |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| user | 用户 | Reference: [Person](#person) |  |  | False | None |  |
| device | 设备 | Reference: [Device](#device) |  |  | False | None |  |
| created_at | 记录时间 | DateTime |  |  | False | now() |  |
| time_begin | 发生时间 | DateTime |  |  | False | None |  |
| media_id | 媒体编号 | Int |  |  | False | 0 |  |
| media_type | 媒体类型 | Int |  |  | False | 0 |  |
| media_dest | 目标 | Int |  |  | False | 0 |  |
| media_length | 长度 | Int |  |  | False | 0 |  |
| media_file | 文件名 | String |  |  | False |  |  |


# mediamessage

媒体消息

| 字段名 | 说明 | 类型 | 最小长度 | 最大长度 | 必填字段 | 缺省值 | 备注 |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| subject | 标题 | String |  | 64 | False |  |  |
| sender | 发送用户 | Reference: [Person](#person) |  |  | False | None |  |
| recipient | 接收用户 | Reference: [Person](#person) |  |  | False | None |  |
| created_at | 记录时间 | DateTime |  |  | False | now() |  |
| send_at | 发送时间 | DateTime |  |  | False | now() |  |
| send_by | 发送终端 | String |  | 64 | False |  |  |
| read_at | 读取时间 | DateTime |  |  | False | None |  |
| sender_deleted | 发送者删除 | Boolean |  |  | False | False |  |
| sender_deleted_at | 发送者删除时间 | DateTime |  |  | False | None |  |
| recipient_deleted | 接收者删除 | Boolean |  |  | False | False |  |
| recipient_deleted_at | 接收者删除时间 | DateTime |  |  | False | None |  |
| media_type | 类型 | Int |  |  | False | 0 |  |
| media_length | 长度 | Int |  |  | False | 0 |  |
| filename | 文件名 | String |  | 64 | False | None |  |
| url | 下载地址 | String |  | 128 | False | None |  |


# mediapage

媒体资源

| 字段名 | 说明 | 类型 | 最小长度 | 最大长度 | 必填字段 | 缺省值 | 备注 |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| group | 拥有组 | Reference: [Group](#group) |  |  | False | None |  |
| created_by | 创建人 | Reference: [Person](#person) |  |  | False | None |  |
| created_at | 创建时间 | DateTime |  |  | True | now() |  |
| updated_at | 更新时间 | DateTime |  |  | True | now() |  |
| subject | 标题 | String |  | 64 | False |  |  |
| type | 资源类型(新增) | String |  |  | True | text | text:text; photo:photo; voice:voice; other:other |
| comments | 评论 | List: Embedded [PageComment](#pagecomment) |  |  | False |  |  |
| stars | 赞 | List: Embedded [PageStar](#pagestar) |  |  | False |  |  |
| media_length | 长度 | Int |  |  | False | 0 |  |
| filename | 文件名 | String |  | 64 | False | None |  |
| url | 下载地址 | String |  | 128 | False | None |  |
| thumb_url | 缩略图下载地址 | String |  | 128 | False | None |  |
| upload_type | 上传类型 | Int |  |  | False | 0 |  |
| devices | 待发送设备列表 | List: Reference [Device](#device) |  |  | False |  |  |
| devices_finished | 已发送设备列表 | List: Reference [Device](#device) |  |  | False |  |  |


# member

小组成员

| 字段名 | 说明 | 类型 | 最小长度 | 最大长度 | 必填字段 | 缺省值 | 备注 |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| group | 组 | Reference: [Group](#group) |  |  | True | None |  |
| person | 成员 | Reference: [Person](#person) |  |  | True | None |  |
| member_name | 关系 | String |  |  | False |  |  |
| is_default | 是缺省组 | Int |  |  | False | 0 |  |


# message

好友消息

| 字段名 | 说明 | 类型 | 最小长度 | 最大长度 | 必填字段 | 缺省值 | 备注 |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| subject | 标题 | String |  | 64 | False |  |  |
| sender | 发送用户 | Reference: [Person](#person) |  |  | False | None |  |
| recipient | 接收用户 | Reference: [Person](#person) |  |  | False | None |  |
| created_at | 记录时间 | DateTime |  |  | False | now() |  |
| send_at | 发送时间 | DateTime |  |  | False | now() |  |
| send_by | 发送终端 | String |  | 64 | False |  |  |
| read_at | 读取时间 | DateTime |  |  | False | None |  |
| sender_deleted | 发送者删除 | Boolean |  |  | False | False |  |
| sender_deleted_at | 发送者删除时间 | DateTime |  |  | False | None |  |
| recipient_deleted | 接收者删除 | Boolean |  |  | False | False |  |
| recipient_deleted_at | 接收者删除时间 | DateTime |  |  | False | None |  |


# msgnotification

Message通知消息

| 字段名 | 说明 | 类型 | 最小长度 | 最大长度 | 必填字段 | 缺省值 | 备注 |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| token_type | 终端类型 | String |  | 16 | True | ios | ios:ios; android:android |
| token | 设备标识 | String |  | 128 | False | None |  |
| title | 标题 | String |  | 16 | True | None |  |
| content | 内容 | String |  | 256 | True | None |  |
| group | 关键组 | Reference: [Group](#group) |  |  | False | None |  |
| recipient | 接收人 | Reference: [Person](#person) |  |  | True | None |  |
| created_at | 提交时间 | DateTime |  |  | True | now() |  |
| updated_at | 更新时间 | DateTime |  |  | True | now() |  |
| expired_at | 过期时间 | DateTime |  |  | True |  |  |
| sched_send_at | 预期发送时间 | DateTime |  |  | True | now() |  |
| error_code | 返回码 | Int |  |  | False | None |  |
| error_info | 返回信息 | String |  |  | False | None |  |
| is_completed | 已完成 | Boolean |  |  | True | False |  |
| is_cleared | 已清除 | Boolean |  |  | True | False |  |
| page | Page | Reference: [MediaPage](#mediapage) |  |  | True | None |  |


# notification

推送通知

| 字段名 | 说明 | 类型 | 最小长度 | 最大长度 | 必填字段 | 缺省值 | 备注 |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| token_type | 终端类型 | String |  | 16 | True | ios | ios:ios; android:android |
| token | 设备标识 | String |  | 128 | False | None |  |
| title | 标题 | String |  | 16 | True | None |  |
| content | 内容 | String |  | 256 | True | None |  |
| group | 关键组 | Reference: [Group](#group) |  |  | False | None |  |
| recipient | 接收人 | Reference: [Person](#person) |  |  | True | None |  |
| created_at | 提交时间 | DateTime |  |  | True | now() |  |
| updated_at | 更新时间 | DateTime |  |  | True | now() |  |
| expired_at | 过期时间 | DateTime |  |  | True |  |  |
| sched_send_at | 预期发送时间 | DateTime |  |  | True | now() |  |
| error_code | 返回码 | Int |  |  | False | None |  |
| error_info | 返回信息 | String |  |  | False | None |  |
| is_completed | 已完成 | Boolean |  |  | True | False |  |
| is_cleared | 已清除 | Boolean |  |  | True | False |  |


# notificationservice

推送服务

| 字段名 | 说明 | 类型 | 最小长度 | 最大长度 | 必填字段 | 缺省值 | 备注 |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| type | 终端类型 | String |  | 16 | True | ios | ios:ios; android:android |
| name | 服务名 | String |  | 16 | True | aiqiangua |  |
| accessid | accessid | Int |  |  | True | 0 |  |
| secretkey | secretkey | String |  |  | True |  |  |


# page

资源分享

| 字段名 | 说明 | 类型 | 最小长度 | 最大长度 | 必填字段 | 缺省值 | 备注 |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| group | 拥有组 | Reference: [Group](#group) |  |  | False | None |  |
| created_by | 创建人 | Reference: [Person](#person) |  |  | False | None |  |
| created_at | 创建时间 | DateTime |  |  | True | now() |  |
| updated_at | 更新时间 | DateTime |  |  | True | now() |  |
| subject | 标题 | String |  | 64 | False |  |  |
| type | 资源类型(新增) | String |  |  | True | text | text:text; photo:photo; voice:voice; other:other |
| comments | 评论 | List: Embedded [PageComment](#pagecomment) |  |  | False |  |  |
| stars | 赞 | List: Embedded [PageStar](#pagestar) |  |  | False |  |  |


# pagecomment

评论  -- 内嵌对象

| 字段名 | 说明 | 类型 | 最小长度 | 最大长度 | 必填字段 | 缺省值 | 备注 |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| created_by | 创建人 | Reference: [Person](#person) |  |  | False | None |  |
| created_at | 创建时间 | DateTime |  |  | True | now() |  |
| comment_id | 内部编号 | String |  |  | False | None |  |
| content | 回复 | String |  | 256 | False |  |  |


# pagestar

点赞  -- 内嵌对象

| 字段名 | 说明 | 类型 | 最小长度 | 最大长度 | 必填字段 | 缺省值 | 备注 |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| created_by | 创建人 | Reference: [Person](#person) |  |  | True | None |  |
| created_at | 创建时间 | DateTime |  |  | True | now() |  |


# passwordresetnotify

Email口令重设通知

| 字段名 | 说明 | 类型 | 最小长度 | 最大长度 | 必填字段 | 缺省值 | 备注 |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| person | 发送用户 | Reference: [Person](#person) |  |  | False | None |  |
| email | 注册邮箱 | Email |  | 64 | True | None |  |
| created_at | 申请时间 | DateTime |  |  | False | now() |  |
| send_at | 发送时间 | DateTime |  |  | False | None |  |
| send_ok | 发送结果 | Boolean |  |  | False | None |  |
| send_error | 失败信息 | String |  |  | False | None |  |
| accept_at | 确认时间 | DateTime |  |  | False | None |  |
| password | 用户口令 | String |  | 64 | True | None |  |


# passwordresetrequest

Email口令重设确认

| 字段名 | 说明 | 类型 | 最小长度 | 最大长度 | 必填字段 | 缺省值 | 备注 |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| person | 发送用户 | Reference: [Person](#person) |  |  | False | None |  |
| email | 注册邮箱 | Email |  | 64 | True | None |  |
| created_at | 申请时间 | DateTime |  |  | False | now() |  |
| send_at | 发送时间 | DateTime |  |  | False | None |  |
| send_ok | 发送结果 | Boolean |  |  | False | None |  |
| send_error | 失败信息 | String |  |  | False | None |  |
| accept_at | 确认时间 | DateTime |  |  | False | None |  |


# pedometerdata

计步数据

| 字段名 | 说明 | 类型 | 最小长度 | 最大长度 | 必填字段 | 缺省值 | 备注 |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| user | 用户 | Reference: [Person](#person) |  |  | False | None |  |
| device | 设备 | Reference: [Device](#device) |  |  | False | None |  |
| created_at | 记录时间 | DateTime |  |  | False | now() |  |
| time_begin | 发生时间 | DateTime |  |  | False | None |  |
| value | 累计步数 | Int |  |  | False | 0 |  |


# person

人员信息

| 字段名 | 说明 | 类型 | 最小长度 | 最大长度 | 必填字段 | 缺省值 | 备注 |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| username | 用户名 | String |  | 16 | True | None |  |
| password | 用户口令 | String |  | 64 | True | None |  |
| email | 注册邮箱 | Email |  | 64 | False | None |  |
| nickname | 别名 | String |  | 64 | False | None |  |
| phone | 手机号码 | String |  | 15 | False | None |  |
| telephone | 电话号码 | String |  | 15 | False | None |  |
| app | 服务名 | String |  | 30 | True | aiqiangua | 标识登陆的app |
| devicetokens | 终端标识列表 | List: Embedded [DeviceToken](#devicetoken) |  |  | False |  |  |
| weight | 体重（KG） | Int |  |  | False | 0 |  |
| step | 步长（CM） | Int |  |  | False | 0 |  |
| age | 年龄（岁） | Int |  |  | False | 0 |  |
| height | 身高（CM） | Int |  |  | False | 0 |  |
| avatar | 头像文件 | String |  |  | False | None |  |
| avatar_url | 头像 | String |  |  | False | /media/avatar/200/male.png |  |
| community | 社区 | Reference: [Community](#community) |  |  | False | None |  |
| role | 角色 | String |  | 10 | True | user | user:用户; operator:操作员; superuser:超级管理员 |
| gender | 性别 | String |  | 10 | True | male | male:男 ; female:女 |
| address | 地址 | String |  | 64 | False | None |  |
| created_at | 创建时间 | DateTime |  |  | True | now() |  |
| updated_at | 更新时间 | DateTime |  |  | True | now() |  |
| lastlogin_ip | 最近登录地址 | String |  | 16 | False | None |  |
| lastlogin_at | 最近登录时间 | DateTime |  |  | False | None |  |
| lastlogin_by | 登录设备 | String |  |  | True |  |  |
| enable | 启用 | Boolean |  |  | False | False | 暂时没有使用 |
| email_is_checked | 邮箱已验证 | Boolean |  |  | False | False |  |
| phone_is_checked | 手机已验证 | Boolean |  |  | False | False |  |
| push_sos_enable | 允许SOS推送 | Boolean |  |  | False | False |  |
| push_fence_enable | 允许电子围栏推送 | Boolean |  |  | False | False |  |
| push_abnormal_enable | 允许健康数据推送 | Boolean |  |  | False | False |  |
| push_message_enable | 允许家庭圈消息推送 | Boolean |  |  | False | False |  |
| push_lowpower_enable | 允许低电推送 | Boolean |  |  | False | False |  |
| push_system_enable | 允许系统消息推送 | Boolean |  |  | False | False |  |
| auth_type | 授权类型 | String |  | 10 | False | None | weibo:weibo; qq:qq; weixin:weixin |
| auth_uid | 授权唯一标识 | String |  | 256 | False | None |  |
| auth_updated_at | 更新时间 | DateTime |  |  | True | now() |  |
| home | Home | String |  |  | False | None |  |
| home_wifi | Home Wifi | String |  | 32 | False | None |  |
| devices | 设备列表 | List: [Device](#device) |  |  | |  |  |
| groups | 小组列表 | List: [Group](#group) |  |  | |  |  |


# posturedata

姿势数据(废弃)

| 字段名 | 说明 | 类型 | 最小长度 | 最大长度 | 必填字段 | 缺省值 | 备注 |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| user | 用户 | Reference: [Person](#person) |  |  | False | None |  |
| device | 设备 | Reference: [Device](#device) |  |  | False | None |  |
| created_at | 记录时间 | DateTime |  |  | False | now() |  |
| time_begin | 发生时间 | DateTime |  |  | False | None |  |
| posture_type | 姿势类型 | Int |  |  | False | 0 |  |
| abnormal_count | 异常步数 | Int |  |  | False | 0 |  |
| count | 步数 | Int |  |  | False | 0 |  |
| calorie | 消耗卡路里 | Int |  |  | False | 0 |  |


# powerdata

开机数据

| 字段名 | 说明 | 类型 | 最小长度 | 最大长度 | 必填字段 | 缺省值 | 备注 |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| user | 用户 | Reference: [Person](#person) |  |  | False | None |  |
| device | 设备 | Reference: [Device](#device) |  |  | False | None |  |
| created_at | 记录时间 | DateTime |  |  | False | now() |  |
| time_begin | 发生时间 | DateTime |  |  | False | None |  |
| type | 开/关机类型 | String |  |  | False | 0 | 0:开机; 1:关机; 2:电量上报; 3:低电通知 |
| remaining_power | 剩余电量(%） | Int |  |  | False | 0 |  |
| location | 低电时位置 | Reference: [LocationData](#locationdata) |  |  | False | None |  |


# powernotification

低电通知

| 字段名 | 说明 | 类型 | 最小长度 | 最大长度 | 必填字段 | 缺省值 | 备注 |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| token_type | 终端类型 | String |  | 16 | True | ios | ios:ios; android:android |
| token | 设备标识 | String |  | 128 | False | None |  |
| title | 标题 | String |  | 16 | True | None |  |
| content | 内容 | String |  | 256 | True | None |  |
| group | 关键组 | Reference: [Group](#group) |  |  | False | None |  |
| recipient | 接收人 | Reference: [Person](#person) |  |  | True | None |  |
| created_at | 提交时间 | DateTime |  |  | True | now() |  |
| updated_at | 更新时间 | DateTime |  |  | True | now() |  |
| expired_at | 过期时间 | DateTime |  |  | True |  |  |
| sched_send_at | 预期发送时间 | DateTime |  |  | True | now() |  |
| error_code | 返回码 | Int |  |  | False | None |  |
| error_info | 返回信息 | String |  |  | False | None |  |
| is_completed | 已完成 | Boolean |  |  | True | False |  |
| is_cleared | 已清除 | Boolean |  |  | True | False |  |
| data | 电源数据 | Reference: [PowerData](#powerdata) |  |  | True | None |  |


# registerrequest

Email注册确认

| 字段名 | 说明 | 类型 | 最小长度 | 最大长度 | 必填字段 | 缺省值 | 备注 |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| person | 发送用户 | Reference: [Person](#person) |  |  | False | None |  |
| email | 注册邮箱 | Email |  | 64 | True | None |  |
| created_at | 申请时间 | DateTime |  |  | False | now() |  |
| send_at | 发送时间 | DateTime |  |  | False | None |  |
| send_ok | 发送结果 | Boolean |  |  | False | None |  |
| send_error | 失败信息 | String |  |  | False | None |  |
| accept_at | 确认时间 | DateTime |  |  | False | None |  |


# rfiddata

到家数据(废弃)

| 字段名 | 说明 | 类型 | 最小长度 | 最大长度 | 必填字段 | 缺省值 | 备注 |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| user | 用户 | Reference: [Person](#person) |  |  | False | None |  |
| device | 设备 | Reference: [Device](#device) |  |  | False | None |  |
| created_at | 记录时间 | DateTime |  |  | False | now() |  |
| time_begin | 发生时间 | DateTime |  |  | False | None |  |
| state | 到家 | Int |  |  | False | 0 |  |


# sedentarydata

久坐数据(废弃)

| 字段名 | 说明 | 类型 | 最小长度 | 最大长度 | 必填字段 | 缺省值 | 备注 |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| user | 用户 | Reference: [Person](#person) |  |  | False | None |  |
| device | 设备 | Reference: [Device](#device) |  |  | False | None |  |
| created_at | 记录时间 | DateTime |  |  | False | now() |  |
| time_begin | 发生时间 | DateTime |  |  | False | None |  |
| value | 久坐时长 | Int |  |  | False | 0 |  |


# servicepage

用户服务

| 字段名 | 说明 | 类型 | 最小长度 | 最大长度 | 必填字段 | 缺省值 | 备注 |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| group | 拥有组 | Reference: [Group](#group) |  |  | False | None |  |
| created_by | 创建人 | Reference: [Person](#person) |  |  | False | None |  |
| created_at | 创建时间 | DateTime |  |  | True | now() |  |
| updated_at | 更新时间 | DateTime |  |  | True | now() |  |
| subject | 标题 | String |  | 64 | False |  |  |
| type | 资源类型(新增) | String |  |  | True | text | text:text; photo:photo; voice:voice; other:other |
| comments | 评论 | List: Embedded [PageComment](#pagecomment) |  |  | False |  |  |
| stars | 赞 | List: Embedded [PageStar](#pagestar) |  |  | False |  |  |
| user | 反馈用户 | Reference: [Person](#person) |  |  | False | None |  |
| body | 反馈内容 | String |  | 4096 | False | None |  |
| is_closed | 是否关闭 | Boolean |  |  | False | False |  |


# settingalert

事件提醒  -- 内嵌对象

| 字段名 | 说明 | 类型 | 最小长度 | 最大长度 | 必填字段 | 缺省值 | 备注 |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| seqid | 序号 | Int |  |  | True | None |  |
| enable | 启用 | Boolean |  |  | True | False |  |
| is_medicine | 用药 | Boolean |  |  | True | False | 仅用于app标识，无实际意义 |
| name | 名称 | String |  | 40 | True |  |  |
| alert_type | 提醒类型 | Int |  |  | True | 1 | 0、周期性提醒，类似手机工作日闹钟类型 1、一次性提醒，设定日期 |
| cycle | 周期 | Int |  |  | True | 1 | 1、以星期为周期，对应上面的0,2、以日期为周期，对应上面的1 |
| time | 时间 | String |  | 14 | False |  | 当alert_type=0时，格式为 1001101+21+30+ ，意义：前7位对应周日、周一……周六，需要提醒的那些天，后面是HHMM，中间用+号分割和结尾；当alert_type=1时，格式为YYYYMMDDHHMMSS 20150313213000 |
| media_length | 语音文件长度 | Int |  |  | False | 0 | 上传前需检查文件大小，最大不得超过10KB，建议在5K~8K之间，否则会报错，不需要传递这个参数，服务器计算 |
| file_checksum | 语音文件（校验和） | Int |  |  | False | 0 | 服务器产生 |
| filename | 语音文件名 | String |  | 64 | False | None |  |
| url | 下载地址 | String |  | 128 | False | None | 服务器产生 |
| created_at | 创建时间 | DateTime |  |  | False | None |  |


# settingfence

围栏  -- 内嵌对象

| 字段名 | 说明 | 类型 | 最小长度 | 最大长度 | 必填字段 | 缺省值 | 备注 |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| seqid | 序号 | Int |  |  | True | None |  |
| freq | 每天 | Boolean |  |  | False | True |  |
| enable | 启用 | Boolean |  |  | True | False |  |
| name | 名称 | String |  | 40 | True |  |  |
| time_begin | 起始时间 | Int |  |  | True | 0 |  |
| time_end | 终止时间 | Int |  |  | True | 0 |  |
| safe_area | 安全区域 | Polygon |  |  | False | None |  |


# settingsosnumber

亲情号码  -- 内嵌对象

| 字段名 | 说明 | 类型 | 最小长度 | 最大长度 | 必填字段 | 缺省值 | 备注 |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| seqid | 序号 | Int |  |  | True | None |  |
| name | 名称 | String |  | 32 | True |  |  |
| num | 号码 | String |  | 16 | True |  |  |
| dial_flag | 是否呼叫 | Boolean |  |  | True | False | 是否将亲情号码设置为SOS号码，即在设备SOS时加入拨打循环 |


# shortmessage

短信发送任务

| 字段名 | 说明 | 类型 | 最小长度 | 最大长度 | 必填字段 | 缺省值 | 备注 |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| created_at | 提交时间 | DateTime |  |  | True | now() |  |
| updated_at | 更新时间 | DateTime |  |  | True | now() |  |
| expired_at | 过期时间 | DateTime |  |  | True |  |  |
| sched_send_at | 预期发送时间 | DateTime |  |  | True | now() |  |
| error_code | 返回码 | Int |  |  | False | None |  |
| error_info | 返回信息 | String |  |  | False | None |  |
| is_completed | 已完成 | Boolean |  |  | True | False |  |
| is_confirmed | 已确认 | Boolean |  |  | True | False |  |
| phone | 手机号码 | String | 11 | 11 | True | None |  |
| content | 发送内容 | String |  | 160 | True | None |  |


# shortmessagechecksum

短信验证码发送任务

| 字段名 | 说明 | 类型 | 最小长度 | 最大长度 | 必填字段 | 缺省值 | 备注 |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| created_at | 提交时间 | DateTime |  |  | True | now() |  |
| updated_at | 更新时间 | DateTime |  |  | True | now() |  |
| expired_at | 过期时间 | DateTime |  |  | True |  |  |
| sched_send_at | 预期发送时间 | DateTime |  |  | True | now() |  |
| error_code | 返回码 | Int |  |  | False | None |  |
| error_info | 返回信息 | String |  |  | False | None |  |
| is_completed | 已完成 | Boolean |  |  | True | False |  |
| is_confirmed | 已确认 | Boolean |  |  | True | False |  |
| phone | 手机号码 | String | 11 | 11 | True | None |  |
| content | 发送内容 | String |  | 160 | True | None |  |
| purpose | 用途 | String |  | 16 | True | login | login:动态密码; reset:重设密码; register:注册; password:已废弃 |
| host_ip | 申请IP | String |  | 16 | True |  |  |
| checksum | 验证码 | String |  | 6 | True | None |  |


# shortmessagesos

呼救短信发送任务

| 字段名 | 说明 | 类型 | 最小长度 | 最大长度 | 必填字段 | 缺省值 | 备注 |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| created_at | 提交时间 | DateTime |  |  | True | now() |  |
| updated_at | 更新时间 | DateTime |  |  | True | now() |  |
| expired_at | 过期时间 | DateTime |  |  | True |  |  |
| sched_send_at | 预期发送时间 | DateTime |  |  | True | now() |  |
| error_code | 返回码 | Int |  |  | False | None |  |
| error_info | 返回信息 | String |  |  | False | None |  |
| is_completed | 已完成 | Boolean |  |  | True | False |  |
| is_confirmed | 已确认 | Boolean |  |  | True | False |  |
| phone | 手机号码 | String | 11 | 11 | True | None |  |
| content | 发送内容 | String |  | 160 | True | None |  |


# simphone

SIM号码

| 字段名 | 说明 | 类型 | 最小长度 | 最大长度 | 必填字段 | 缺省值 | 备注 |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| iccid | 移动用户iccid号 | String |  | 64 | True | None |  |
| sim_phone | 移动用户卡号 | String |  | 16 | False | None |  |
| sim_phone_type | 移动用户卡类型 | String |  | 8 | False | unicom | unicom:中国联通; cmcc:中国移动; ctcc:中国电信 |
| update_at | 处理时间 | DateTime |  |  | False | now() |  |


# sleepdata

睡眠数据

| 字段名 | 说明 | 类型 | 最小长度 | 最大长度 | 必填字段 | 缺省值 | 备注 |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| user | 用户 | Reference: [Person](#person) |  |  | False | None |  |
| device | 设备 | Reference: [Device](#device) |  |  | False | None |  |
| created_at | 记录时间 | DateTime |  |  | False | now() |  |
| time_begin | 发生时间 | DateTime |  |  | False | None |  |
| time_end | 截止时间 | DateTime |  |  | False | None |  |
| interval | 检测间隔 | Int |  |  | False | 30 |  |
| total | 检测次数 | Int |  |  | False | 0 |  |
| data | 睡眠数据 | List: Embedded [SleepDataSleep](#sleepdatasleep) |  |  | False |  | 共48组，半小时1组，(0,0)的属于填充数据，第一组数据的开始时间是time_begin |


# sleepdatasleep

数据  -- 内嵌对象

| 字段名 | 说明 | 类型 | 最小长度 | 最大长度 | 必填字段 | 缺省值 | 备注 |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| turn_over | 活动次数 | Int |  |  | False | 0 | 出现255，且state为0时，清醒；turn_over=0,state=2，连续出现大于或等于3个时，视作非睡眠状态 |
| state | 睡眠质量 | Int |  |  | False | 0 | state=0，浅睡； 1 中度睡眠； 2 深度睡眠 |

# sosdata

呼叫数据

| 字段名 | 说明 | 类型 | 最小长度 | 最大长度 | 必填字段 | 缺省值 | 备注 |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| user | 用户 | Reference: [Person](#person) |  |  | False | None |  |
| device | 设备 | Reference: [Device](#device) |  |  | False | None |  |
| created_at | 记录时间 | DateTime |  |  | False | now() |  |
| time_begin | 发生时间 | DateTime |  |  | False | None |  |
| type | 类型 | String |  |  | False | 0 | 0:Gps定位; 1:基站定位 |
| city | 城市 | String |  | 16 | False |  |  |
| address | 地址 | String |  | 128 | False |  |  |
| point | 坐标 | Point |  |  | False | None |  |
| cell | CELL | List: Embedded [CELL](#cell) |  |  | False |  |  |
| wifi | WIFI | List: Embedded [WIFI](#wifi) |  |  | False |  |  |
| heartrate | 心率值 | Int |  |  | False | None |  |
| is_removed | 是否消除 | Boolean |  |  | False | False |  |


# sosnotification

Sos通知消息

| 字段名 | 说明 | 类型 | 最小长度 | 最大长度 | 必填字段 | 缺省值 | 备注 |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| token_type | 终端类型 | String |  | 16 | True | ios | ios:ios; android:android |
| token | 设备标识 | String |  | 128 | False | None |  |
| title | 标题 | String |  | 16 | True | None |  |
| content | 内容 | String |  | 256 | True | None |  |
| group | 关键组 | Reference: [Group](#group) |  |  | False | None |  |
| recipient | 接收人 | Reference: [Person](#person) |  |  | True | None |  |
| created_at | 提交时间 | DateTime |  |  | True | now() |  |
| updated_at | 更新时间 | DateTime |  |  | True | now() |  |
| expired_at | 过期时间 | DateTime |  |  | True |  |  |
| sched_send_at | 预期发送时间 | DateTime |  |  | True | now() |  |
| error_code | 返回码 | Int |  |  | False | None |  |
| error_info | 返回信息 | String |  |  | False | None |  |
| is_completed | 已完成 | Boolean |  |  | True | False |  |
| is_cleared | 已清除 | Boolean |  |  | True | False |  |
| data | SOS | Reference: [SosData](#sosdata) |  |  | True | None |  |


# sysmessage

系统消息

| 字段名 | 说明 | 类型 | 最小长度 | 最大长度 | 必填字段 | 缺省值 | 备注 |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| subject | 标题 | String |  | 128 | False |  |  |
| type | 消息类型 | String |  | 16 | False | open | community_invite:邀请加入社区; community_join:申请加入社区; community_leave:申请退出社区 |
| sender | 发起用户 | Reference: [Person](#person) |  |  | False | None |  |
| sender_note | 发起留言 | String |  |  | False |  |  |
| recipient | 接收用户 | Reference: [Person](#person) |  |  | False | None |  |
| created_at | 发起时间 | DateTime |  |  | False | now() |  |
| result | 处理结果 | String |  | 16 | False | open | open:待处理; expired:过期; cancel:取消; accept:接受; reject:拒绝; close:结束 |
| accept_at | 结束时间 | DateTime |  |  | False | None |  |
| recipient_note | 接收人留言 | String |  |  | False |  |  |


# textmessage

文本消息

| 字段名 | 说明 | 类型 | 最小长度 | 最大长度 | 必填字段 | 缺省值 | 备注 |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| subject | 标题 | String |  | 64 | False |  |  |
| sender | 发送用户 | Reference: [Person](#person) |  |  | False | None |  |
| recipient | 接收用户 | Reference: [Person](#person) |  |  | False | None |  |
| created_at | 记录时间 | DateTime |  |  | False | now() |  |
| send_at | 发送时间 | DateTime |  |  | False | now() |  |
| send_by | 发送终端 | String |  | 64 | False |  |  |
| read_at | 读取时间 | DateTime |  |  | False | None |  |
| sender_deleted | 发送者删除 | Boolean |  |  | False | False |  |
| sender_deleted_at | 发送者删除时间 | DateTime |  |  | False | None |  |
| recipient_deleted | 接收者删除 | Boolean |  |  | False | False |  |
| recipient_deleted_at | 接收者删除时间 | DateTime |  |  | False | None |  |
| body | 内容 | String |  | 256 | False | None |  |


# textpage

文本资源

| 字段名 | 说明 | 类型 | 最小长度 | 最大长度 | 必填字段 | 缺省值 | 备注 |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| group | 拥有组 | Reference: [Group](#group) |  |  | False | None |  |
| created_by | 创建人 | Reference: [Person](#person) |  |  | False | None |  |
| created_at | 创建时间 | DateTime |  |  | True | now() |  |
| updated_at | 更新时间 | DateTime |  |  | True | now() |  |
| subject | 标题 | String |  | 64 | False |  |  |
| type | 资源类型(新增) | String |  |  | True | text | text:text; photo:photo; voice:voice; other:other |
| comments | 评论 | List: Embedded [PageComment](#pagecomment) |  |  | False |  |  |
| stars | 赞 | List: Embedded [PageStar](#pagestar) |  |  | False |  |  |
| body | 内容 | String |  | 4096 | False | None |  |


# uploadfile

文件管理

| 字段名 | 说明 | 类型 | 最小长度 | 最大长度 | 必填字段 | 缺省值 | 备注 |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| notes | 备注 | String |  |  | False | None |  |
| type | 类型 | String |  |  | False | None |  |
| url | 下载地址 | String |  | 128 | False | None |  |
| created_at | 处理时间 | DateTime |  |  | False | now() |  |
| result | 处理结果 | String |  |  | False | None |  |
| detail | 异常情况 | String |  |  | False | None |  |
| filename | 文件名 | String |  | 64 | False | None |  |


# wifi

基站标识  -- 内嵌对象

| 字段名 | 说明 | 类型 | 最小长度 | 最大长度 | 必填字段 | 缺省值 | 备注 |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| addr | ADDR | String |  | 32 | False |  |  |
| ssid | SSID | String |  | 32 | False |  |  |
| rssi | RSSI | Int |  |  | False | 0 |  |


# weardata

佩戴数据

| 字段名 | 说明 | 类型 | 最小长度 | 最大长度 | 必填字段 | 缺省值 | 备注 |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| user | 用户 | Reference: [Person](#person) |  |  | False | None |  |
| device | 设备 | Reference: [Device](#device) |  |  | False | None |  |
| created_at | 记录时间 | DateTime |  |  | False | now() |  |
| time_begin | 发生时间 | DateTime |  |  | False | None |  |
| flag | 状态 | Int |  |  | False | 0 |  |


# weathercache

天气缓存

| 字段名 | 说明 | 类型 | 最小长度 | 最大长度 | 必填字段 | 缺省值 | 备注 |
|------- | ---- | ---- | -------- | -------- | -------- | ------ | ---- |
| id |  | ObjectId |  |  | False | None |  |
| key | key | String |  | 64 | True | None |  |
| city | 城市 | String |  | 16 | False | None |  |
| date | 日期 | String |  | 16 | False | None |  |
| weather_id | 天气编号 | Int |  |  | False | 0 |  |
| weather_desc | 天气描述 | String |  | 24 | False |  |  |
| pm25 | 当前ph25值 | Int |  |  | False | 25 |  |
| temp_now | 当前温度 | Int |  |  | False | 25 |  |
| temp_low | 今天低温 | Int |  |  | False | 25 |  |
| temp_high | 今天高温 | Int |  |  | False | 25 |  |
| t_weather_id | 明天天气编号 | Int |  |  | False | 0 |  |
| t_weather_desc | 明天天气描述 | String |  | 24 | False |  |  |
| t_temp_low | 明天低温 | Int |  |  | False | 25 |  |
| t_temp_high | 明天低温 | Int |  |  | False | 25 |  |
| advice | 穿衣建议 | String |  | 256 | False | None |  |
| created_at | 创建时间 | DateTime |  |  | True | now() |  |
| updated_at | 更新时间 | DateTime |  |  | True | now() |  |