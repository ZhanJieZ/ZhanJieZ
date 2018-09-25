数据发送：机构给出接口，我们主动调用，POST请求表单提交数据。


位置数据发送

- 地址: http://xxxxx/
- 方法: post
-   参数规范

    | 名称            | 必须 | 类型         | 说明                               |
    | --------------- | ---- | ------------ | ---------------------------------- |
    | imei            |  是  | String       | 15位设备唯一序号                   |
    | time_begin      |  是  | String       | 发生时间YYYY-MM-DD HH:mm:SS.xxxxxx |
    | is_reply        |  是  | Boolean      | 是否为响应                         |
    | is_track        |  是  | Boolean      | 是否轨迹                           |
    | city            |  是  | String       | 城市                               |
    | address         |  是  | String       | 地址                               |
    | lon             |  是  | double       | 经度                               |
    | lat             |  是  | double       | 纬度                               |
    | type            |  是  | String       | 类型   0:Gps定位; 1:基站定位       |
           



SOS数据发送

- 地址: http://xxxxx/
- 方法: post
-   参数规范

    | 名称            | 必须 | 类型         | 说明                               |
    | --------------- | ---- | ------------ | ---------------------------------- |
    | imei            |  是  | String       | 15位设备唯一序号                   |
    | time_begin      |  是  | String       | 发生时间YYYY-MM-DD HH:mm:SS.xxxxxx |
    | heartrate       |  是  | Int          | 心率                               |
    | city            |  是  | String       | 城市                               |
    | address         |  是  | String       | 地址                               |
    | lon             |  是  | double       | 经度                               |
    | lat             |  是  | double       | 纬度                               |
    | type            |  是  | String       | 类型   0:Gps定位; 1:基站定位       |


心率数据发送

- 地址: http://xxxxx/
- 方法: post
-   参数规范

    | 名称            | 必须 | 类型         | 说明                               |
    | --------------- | ---- | ------------ | ---------------------------------- |
    | imei            |  是  | String       | 15位设备唯一序号                   |
    | time_begin      |  是  | String       | 发生时间YYYY-MM-DD HH:mm:SS.xxxxxx |
    | heartrate       |  是  | Int          | 心率                               |




计步数据发送

- 地址: http://xxxxx/
- 方法: post
-   参数规范

    | 名称            | 必须 | 类型         | 说明                               |
    | --------------- | ---- | ------------ | ---------------------------------- |
    | imei            |  是  | String       | 15位设备唯一序号                   |
    | time_begin      |  是  | String       | 发生时间YYYY-MM-DD HH:mm:SS.xxxxxx |
    | value           |  是  | Int          | 步数                               |



睡眠数据发送


- 地址: http://xxxxx/
- 方法: post
-   参数规范

    | 名称            | 必须 | 类型         | 说明                               |
    | --------------- | ---- | ------------ | ---------------------------------- |
    | imei            |  是  | String       | 15位设备唯一序号                   |
    | time_begin      |  是  | String       | 发生时间YYYY-MM-DD HH:mm:SS.xxxxxx |
    | time_end        |  是  | String       | 结束时间YYYY-MM-DD HH:mm:SS.xxxxxx |
    | interval        |  是  | Int          | 固定30分钟                         |
    | total           |  是  | Int          | 检测次数                           |
    | data            |  是  | Sting        | 样例截取   睡眠数据                |


开关机数据发送

- 地址: http://xxxxx/
- 方法: post
-   参数规范

    | 名称            | 必须 | 类型         | 说明                               |
    | --------------- | ---- | ------------ | ---------------------------------- |
    | imei            |  是  | String       | 15位设备唯一序号                   |
    | time_begin      |  是  | String       | 发生时间YYYY-MM-DD HH:mm:SS.xxxxxx |
    | type            |  是  | String       | 开/关机类型  0开机 2普通  3低电    |
    | remaining_power |  是  | Int          | 剩余电量(%）                       |




跌倒数据发送


- 地址: http://xxxxx/
- 方法: post
-   参数规范

    | 名称            | 必须 | 类型         | 说明                               |
    | --------------- | ---- | ------------ | ---------------------------------- |
    | imei            |  是  | String       | 15位设备唯一序号                   |
    | time_begin      |  是  | String       | 发生时间YYYY-MM-DD HH:mm:SS.xxxxxx |
    | city            |  是  | String       | 城市                               |
    | address         |  是  | String       | 地址                               |
    | lon             |  是  | double       | 经度                               |
    | lat             |  是  | double       | 纬度                               |
    | type            |  是  | String       | 类型   0:Gps定位; 1:基站定位       |



消息通知
- 地址: http://xxxxx/
- 方法: get
-   参数规范

    | 名称            | 必须 | 类型         | 说明                           |
    | --------------- | ---- | ------------ | ------------------------------ |
    | type            |  是  | int          | type=1 SOS，type=2 fall，type=3 new 新成员加入 ，type=4 电子围栏触发， type=5 设备低电，type=6 环境音 '''
    | deviceid        |  是  | String       | 15位设备唯一序号               |
    | communityid     |  是  | String       | 机构ID                         |
    | url             |  是  | String       | 下载地址                       |
  根据type来定义给用户推送提示  type=1 SOS，type=2 fall，type=3 new 新成员加入 ，type=4 电子围栏触发， type=5 设备低电，type=6 环境音'''














