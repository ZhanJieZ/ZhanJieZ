
设备信息
========

# 验证设备

设备验证的作用：检查是否为可激活的设备，并返回设备对象，设备对象包含了可用的sim_phone,sim_phone_type信息，界面可用其填充。 

失败返回非0，失败码定义： 401-无效imei; 402-验证失败; 403-设备已经激活; 500-其它错误

-   地址: /api/device/validate/
-   方法: POST
-   验证方法: Cookie: user
-   响应对象: [device](./object.md#device)
-   请求参数

    | 名称            | 必须 | 类型         | 说明                           |
    | --------------- | ---- | ------------ | ------------------------------ |
    | deviceid        | 是   | string       | 20位设备唯一序号               |

-   请求范例

        curl -v -A CURL -b cookies.txt -d "deviceid=86821900009992614830" http://127.0.0.1:8000/api/device/validate

-   响应范例（成功）

        {
          "success": true
        }

-   响应范例（401）     http://127.0.0.1:8000/api/device/validate?
	{
	    "error_desc":"设备号验证失败！",
	    "error_code":401,
	    "obj":{
		"owner":null,
		"groups":[]
	    },
	    "success":false,
	    "obj_name":""
	}

-   响应范例（402）     http://127.0.0.1:8000/api/device/validate?deviceid=86821900009992697141

	{
	    "error_desc":"设备号验证失败！",
	    "error_code":402,
	    "obj":{
		"owner":null,
		"groups":[]
	    },
	    "success":false,
	    "obj_name":""
	}

-   响应范例（403）      http://127.0.0.1:8000/api/device/validate?deviceid=86821900009992614830

       
	{
	    "error_desc":"设备号验证失败！",
	    "error_code":403,
	    "obj":{
		"owner":"57d6144126425121e8b81864",
		"device_type":"BY102",
		"groups":[
		    "565ba687bf483c7369e5b4a4"
		]
	    },
	    "success":false,
	    "obj_name":""
	}



# 激活设备

设备激活的意义: 将设备的拥有人设置为自己, 使自己可以获取设备的信息。

如果不提供sim_phone，或提供的输入与后台提供的完全一致，表示从后台的数据中直接获得。

注：本接口没有应用在实际场景中。爱牵挂体系中的绑定，并非把设备直接绑定给扫描二维码的app用户，而是由系统自行创建了一个用户，将设备绑给了创建的用户，然后将扫码的app用户和创建的用户归入同一个group，并把app用户设置为该group的管理员，app用户可以对该设备进行管理。

- 地址: /api/person/active
- 方法: POST
- 验证方法: Cookie: user
- 响应对象: 无

__请求参数__

| 名称            | 必须 | 类型         | 说明                           |
| --------------- | ---- | ------------ | ------------------------------ |
| imei	          | 是   | string       | 15位设备唯一序号               |
| sim_phone       | 否   | string       | 腕表的SIM卡手机号              |
| sim_phone_type  | 否   | string       | unicom, cmcc, ctcc             |

__请求范例__
    
    curl -v -A CURL -b cookies.txt -d "deviceid=000030303030303" http://127.0.0.1:8888/api/person/active

    > POST /api/person/active HTTP/1.1
    > User-Agent: CURL
    > Host: 127.0.0.1:8888
    > Accept: */*
    > Cookie: user="2|1:0|10:1408975429|4:user|8:YWRtaW4=|9ffddb70b9d642e1de4649c90dc46dda311f415c8629cf57327badecd2ce41a7"
    > Content-Length: 24
    > Content-Type: application/x-www-form-urlencoded

__响应范例__

    {
      "success": true
    }


# 设备解绑

设备解绑的意义: 将设备的拥有人设置为缺省值。

-   地址: /api/device/[device id]/unactive
-   方法: POST
-   验证方法: Cookie: user
-   响应对象: 无
-   请求范例:
    
        CURL -b cookies.txt http://127.0.0.1:8000/api/device/000000000000001/unactive       l

-   响应范例:

    {
      "success": true
    }


# 查看指定设备

-   地址: /api/device/[device id]
-   方法: GET
-   验证方法: Cookie: user
-   响应对象: [device](./object.md#device)
-   URL参数:  device id
-   请求范例__
    
        curl -v -A CURL -b cookies.txt http://127.0.0.1:8000/api/device/868219000099926

-   响应范例

       {
    "obj":{
        "_id":"868219000099926",
        "alerts":[
            {
                "seqid":1,
                "enable":false,
                "is_medicine":false,
                "name":"",
                "alert_type":1,
                "cycle":1,
                "time":"",
                "media_length":0,
                "file_checksum":0
            },
            {
                "seqid":2,
                "enable":false,
                "is_medicine":false,
                "name":"",
                "alert_type":1,
                "cycle":1,
                "time":"",
                "media_length":0,
                "file_checksum":0
            },
            {
                "seqid":3,
                "enable":false,
                "is_medicine":false,
                "name":"",
                "alert_type":1,
                "cycle":1,
                "time":"",
                "media_length":0,
                "file_checksum":0
            },
            {
                "seqid":4,
                "enable":false,
                "is_medicine":false,
                "name":"",
                "alert_type":1,
                "cycle":1,
                "time":"",
                "media_length":0,
                "file_checksum":0
            },
            {
                "seqid":5,
                "enable":false,
                "is_medicine":false,
                "name":"",
                "alert_type":1,
                "cycle":1,
                "time":"",
                "media_length":0,
                "file_checksum":0
            },
            {
                "seqid":6,
                "enable":false,
                "is_medicine":false,
                "name":"",
                "alert_type":1,
                "cycle":1,
                "time":"",
                "media_length":0,
                "file_checksum":0
            },
            {
                "seqid":7,
                "enable":false,
                "is_medicine":false,
                "name":"",
                "alert_type":1,
                "cycle":1,
                "time":"",
                "media_length":0,
                "file_checksum":0
            },
            {
                "seqid":8,
                "enable":false,
                "is_medicine":false,
                "name":"",
                "alert_type":1,
                "cycle":1,
                "time":"",
                "media_length":0,
                "file_checksum":0
            },
            {
                "seqid":9,
                "enable":false,
                "is_medicine":false,
                "name":"",
                "alert_type":1,
                "cycle":1,
                "time":"",
                "media_length":0,
                "file_checksum":0
            },
            {
                "seqid":10,
                "enable":false,
                "is_medicine":false,
                "name":"",
                "alert_type":1,
                "cycle":1,
                "time":"",
                "media_length":0,
                "file_checksum":0
            }
        ],
        "sos_numbers":[
            {
                "seqid":1,
                "name":"SOS Num1",
                "num":"18680555070",
                "dial_flag":true
            },
            {
                "seqid":2,
                "name":"",
                "num":"",
                "dial_flag":false
            },
            {
                "seqid":3,
                "name":"",
                "num":"",
                "dial_flag":false
            },
            {
                "seqid":4,
                "name":"",
                "num":"",
                "dial_flag":false
            },
            {
                "seqid":5,
                "name":"",
                "num":"",
                "dial_flag":false
            },
            {
                "seqid":6,
                "name":"",
                "num":"",
                "dial_flag":false
            },
            {
                "seqid":7,
                "name":"",
                "num":"",
                "dial_flag":false
            },
            {
                "seqid":8,
                "name":"",
                "num":"",
                "dial_flag":false
            },
            {
                "seqid":9,
                "name":"",
                "num":"",
                "dial_flag":false
            },
            {
                "seqid":10,
                "name":"",
                "num":"",
                "dial_flag":false
            }
        ],
        "tool_numbers":[
            {
                "seqid":1,
                "name":"",
                "num":""
            },
            {
                "seqid":2,
                "name":"",
                "num":""
            },
            {
                "seqid":3,
                "name":"",
                "num":""
            },
            {
                "seqid":4,
                "name":"",
                "num":""
            },
            {
                "seqid":5,
                "name":"",
                "num":""
            }
        ],
        "sos_dial_cycle_times":1,
        "sos_sendmail":false,
        "sos_readmail":false,
        "frequency_location":15,
        "frequency_step":30,
        "frequency_heartrate":60,
        "theshold_heartrate_h":140,
        "theshold_heartrate_l":40,
        "heartrate_enable":true,
        "incoming_restriction":true,
        "bluetooth_enable":false,
        "bluetooth_devices":"",
        "profile":2,
        "sleep_period_begin":"00000000220000",
        "sleep_period_end":"00000000060000",
        "step_objective":3000,
        "theshold_sit":60,
        "theshold_low_battery":20,
        "fall_enable":false,
        "fall_model":0,
        "fences":[
            {
                "seqid":1,
                "freq":true,
                "enable":true,
                "name":"公园",
                "time_begin":71580,
                "time_end":60540,
                "safe_area":{
                    "type":"Polygon",
                    "coordinates":[
                        [
                            [
                                113.453895,
                                23.167357
                            ],
                            [
                                113.459356,
                                23.170405
                            ],
                            [
                                113.461182,
                                23.166135
                            ],
                            [
                                113.456028,
                                23.163558
                            ],
                            [
                                113.453895,
                                23.167357
                            ]
                        ]
                    ]
                }
            },
            {
                "seqid":2,
                "freq":true,
                "enable":false,
                "name":"",
                "time_begin":0,
                "time_end":0
            },
            {
                "seqid":3,
                "freq":true,
                "enable":false,
                "name":"",
                "time_begin":0,
                "time_end":0
            },
            {
                "seqid":4,
                "freq":true,
                "enable":false,
                "name":"",
                "time_begin":0,
                "time_end":0
            },
            {
                "seqid":5,
                "freq":true,
                "enable":false,
                "name":"",
                "time_begin":0,
                "time_end":0
            },
            {
                "seqid":6,
                "freq":true,
                "enable":false,
                "name":"",
                "time_begin":0,
                "time_end":0
            },
            {
                "seqid":7,
                "freq":true,
                "enable":false,
                "name":"",
                "time_begin":0,
                "time_end":0
            },
            {
                "seqid":8,
                "freq":true,
                "enable":false,
                "name":"",
                "time_begin":0,
                "time_end":0
            },
            {
                "seqid":9,
                "freq":true,
                "enable":false,
                "name":"",
                "time_begin":0,
                "time_end":0
            },
            {
                "seqid":10,
                "freq":true,
                "enable":false,
                "name":"",
                "time_begin":0,
                "time_end":0
            }
        ],
        "pedometer_enable":false,
        "sleep_enable":false,
        "track_enable":false,
        "imei":"868219000099926",
        "imsi":"9460040289008130",
        "type":"BY102",
        "sim_phone":"",
        "sim_phone_type":"unicom",
        "owner":{
            "$oid":"57d6144126425121e8b81864"
        },
        "name":"99926",
        "created_at":{
            "$date":1473676304891
        },
        "updated_at":{
            "$date":1473758218830
        },
        "lastlogin_ip":"117.136.43.41",
        "lastlogin_at":{
            "$date":1473758218830
        },
        "active":false,
        "active_at":{
            "$date":1473676482040
        },
        "online":true,
        "location_updated":true,
        "location_updated_at":{
            "$date":1473765727793
        },
        "last_location":{
            "type":"Point",
            "coordinates":[
                113.4567548,
                23.1671913
            ]
        },
        "last_city":"广州市",
        "last_address":"广东省 广州市 黄埔区 观虹路 靠近广州科学城创新大厦C1",
        "wear_flag":0,
        "wear_updated_at":{
            "$date":1473715940071
        },
        "remaining_power":100,
        "remaining_power_updated_at":{
            "$date":1473765961840
        },
        "wifi":[

        ],
        "software_version":"PR_W1_BY102_H_OLED_S2_V05",
        "iccid1":"898602B2011490245130",
        "fence_notification_updated_at":{
            "$date":1473718238194
        },
        "service_number":"",
        "sos_dial_cycle_mode":0,
        "$owner":{
            "_id":{
                "$oid":"57d6144126425121e8b81864"
            },
            "username":"1473647680912",
            "password":"764574f0072695458ee0dc7b5dfb4915dfef4b1c7acae2fcce15308f",
            "nickname":"99926",
            "app":"aiqiangua",
            "devicetokens":[

            ],
            "weight":0,
            "step":0,
            "age":0,
            "height":0,
            "avatar_url":"/media/avatar/200/male.png",
            "role":"user",
            "gender":"male",
            "created_at":{
                "$date":1473676481936
            },
            "updated_at":{
                "$date":1473676481936
            },
            "lastlogin_by":"",
            "enable":false,
            "email_is_checked":false,
            "phone_is_checked":false,
            "push_sos_enable":true,
            "push_fence_enable":true,
            "push_abnormal_enable":true,
            "push_message_enable":true,
            "push_lowpower_enable":true,
            "push_system_enable":true,
            "push_fall_enable":true,
            "push_env_enable":true,
            "auth_updated_at":{
                "$date":1473676481936
            },

            "is_device_owner":true,
            "devices":[
                "868219000099926"
            ],
            "groups":[
                {
                    "$oid":"565ba687bf483c7369e5b4a4"
                }
            ]
        }
    },
    "success":true,
    "obj_name":"device"
}




# 修改设备

- 地址: /api/device/[device oid]/edit
- 方法: POST
- 验证方法: Cookie: user
- 响应对象: [device](./object.md#device)
- URL参数: device oid
- 请求参数: [device](./object.md#device)

__请求范例__
    
    curl -v -A CURL -b cookies.txt -d "name=ABC" http://127.0.0.1:8000/api/device/868219000099926/edit?step_objective=2000

    > POST /api/device/868219000099926/edit?step_objective=2000 HTTP/1.1
    > User-Agent: CURL
    > Host: 120.24.56.48:8889
    > Accept: */*
    > Cookie: "user="2|1:0|10:1473817034|4:user|16:MTg2ODA1NTUwNzA=|2768bb77396815e5a7ca9fe3c65dc8060943c57aeb078c746faf56036533aa12""
    > Content-Length: 8
    > Content-Type: application/x-www-form-urlencoded

__响应范例__

    
    {
      "success": true
    }


# 设置提醒

-   地址: /api/device/[device oid])/alerts/[alert id: 1-10]/
-   方法: POST
-   验证方法: Cookie: user
-   响应对象: 无
-   URL参数: device oid
-   URL参数: alert id(1-10)
-   请求参数: 至少设置一个参数

    | 名称         | 必须 | 类型         | 说明                           |
    | ------------ | ---- | ------------ | ------------------------------ |
    | enable       |  否  | Int          |  0,1                           |
    | name         |  否  | String       |                                |
    | alert_type   |  否  | Int          |                                |
    | cycle        |  否  | Int          |                                |
    | time         |  否  | String       |  alert_type,cycle,time的具体格式见object.md的settingalert  |
    | upfile       |  否  | multipart    | amr文件       |
    | clear        |  否  | any          | 如果指定clear参数，则上述参数全部无意义，全部重设为缺省值    |

-   请求范例
    
         curl -v -A CURL -d 'name=1' -b cookies.txt
	 http://127.0.0.1:8000/api/device/868219000099926/alerts/1?name=1

-   响应范例
    
        {
          "success": true
        }


# 设置亲情号码

-   地址: /api/device/[device oid]/sos_numbers/[id: 1-10]/
-   方法: POST
-   验证方法: Cookie: user
-   响应对象: 无
-   URL参数: device oid
-   URL参数: id(1-10)
-   请求参数: 至少设置一个参数

    | 名称         | 必须 | 类型         | 说明                           |
    | ------------ | ---- | ------------ | ------------------------------ |
    | name         |  否  | String       | 号码昵称                        |
    | num          |  否  | String       | 亲情号码，可以是手机或固话        |
    | dial_flag    |  否  | Int          | 0不设置为紧急呼叫号码,1设置为紧急呼叫号码       |
    | clear        |  否  | any          | 如果指定clear参数，则上述参数全部无意义，全部重设为缺省值    |

-   请求范例
    
         curl -v -A CURL -d 'name=1' -b cookies.txt
	 http://127.0.0.1:8000/api/device/868219000099926/sos_numbers/1?name=1

-   响应范例
    
        {
          "success": true
        }

# 设置安全区域

-   地址: /api/device/[device oid])/fences/[id: 1-10]/
-   方法: POST
-   验证方法: Cookie: user
-   响应对象: 无
-   URL参数: device oid
-   URL参数: id(1-10)
-   请求参数: 至少设置一个参数

    | 名称         | 必须 | 类型         | 说明                           |
    | ------------ | ---- | ------------ | ------------------------------ |
    | enable       |  否  | Int          |  0,1                           |
    | name         |  否  | String       |                                |
    | freq         |  否  | Boolean      |  0，触发一天；1，每日触发        |
    | time_begin   |  否  | Int          |  目标时间与当日0点之间相差的秒数。如8 a.m 8*60*60=28800 |
    | time_end     |  否  | Int          |  同上                        |
    | safe_area    |  否  | String       | x1,y1;x2,y2;xn,yn  一组由';'分隔的坐标，坐标用','分隔。且需要呈闭环，如A,B,C,D4个点，则应该上传的数据为 A;B;C;D;A  |    
    | clear        |  否  | any          | 如果指定clear参数，则上述参数全部无意义，全部重设为缺省值    |

-   请求范例
    
         curl -v -A CURL -d 'name=1' -b cookies.txt 
	http://127.0.0.1:8000/api/device/868219000099926/fences/1?name=1

-   响应范例
    
        {
          "success": true
        }


# 查看设备开关机数据
- 地址: /api/powerdata/?device=[device oid]
- 方法: GET
- 验证方法: Cookie: user
- 响应对象: [powerdata](./object.md#powerdata)
- 请求参数: 

    | 名称            | 必须 | 类型         | 说明                           |
    | --------------- | ---- | ------------ | ------------------------------ |
    | device          | 是   | string       | 15位设备唯一序号              |
    | time_begin      | 否   | string       | YYYYMMDD，查询指定日期的数据  |
    | type            | 否   | string       | 0,1,2,3  |

__请求范例__
    
    curl -v -A CURL -b cookies.txt http://127.0.0.1:8000/api/powerdata/?device=868219000099926&depth=1

    > GET /api/powerdata/?device=868219000099926 HTTP/1.1
    > User-Agent: CURL
    > Host: 127.0.0.1:8888
    > Accept: */*
    > Cookie: "user="2|1:0|10:1473817034|4:user|16:MTg2ODA1NTUwNzA=|2768bb77396815e5a7ca9fe3c65dc8060943c57aeb078c746faf56036533aa12""

__响应范例__


{
    "objs":[
        {
            "_id":{
                "$oid":"57d7538d26425121e67831a1"
            },
            "user":{
                "$oid":"57d6144126425121e8b81864"
            },
            "device":"868219000099926",
            "created_at":{
                "$date":1473758221976
            },
            "time_begin":{
                "$date":1473758219000
            },
            "type":"0",
            "remaining_power":43
        },
        {
            "_id":{
                "$oid":"57d6ae6226425121e6782e6f"
            },
            "user":{
                "$oid":"57d6144126425121e8b81864"
            },
            "device":"868219000099926",
            "created_at":{
                "$date":1473715938349
            },
            "time_begin":{
                "$date":1473715937000
            },
            "type":"2",
            "remaining_power":41
        },
        {
            "_id":{
                "$oid":"57d6a05626425121e6782e1d"
            },
            "user":{
                "$oid":"57d6144126425121e8b81864"
            },
            "device":"868219000099926",
            "created_at":{
                "$date":1473712342228
            },
            "time_begin":{
                "$date":1473712340000
            },
            "type":"2",
            "remaining_power":44
        },
        {
            "_id":{
                "$oid":"57d6924e26425121e6782dcd"
            },
            "user":{
                "$oid":"57d6144126425121e8b81864"
            },
            "device":"868219000099926",
            "created_at":{
                "$date":1473708750566
            },
            "time_begin":{
                "$date":1473708747000
            },
            "type":"2",
            "remaining_power":45
        },
        {
            "_id":{
                "$oid":"57d6762126425121e6782ba3"
            },
            "user":{
                "$oid":"57d6144126425121e8b81864"
            },
            "device":"868219000099926",
            "created_at":{
                "$date":1473701537881
            },
            "time_begin":{
                "$date":1473701536000
            },
            "type":"2",
            "remaining_power":46
        },
        {
            "_id":{
                "$oid":"57d6680e26425121e6782aa6"
            },
            "user":{
                "$oid":"57d6144126425121e8b81864"
            },
            "device":"868219000099926",
            "created_at":{
                "$date":1473697934867
            },
            "time_begin":{
                "$date":1473697933000
            },
            "type":"2",
            "remaining_power":48
        },
        {
            "_id":{
                "$oid":"57d659fe26425121e67828c5"
            },
            "user":{
                "$oid":"57d6144126425121e8b81864"
            },
            "device":"868219000099926",
            "created_at":{
                "$date":1473694334456
            },
            "time_begin":{
                "$date":1473694333000
            },
            "type":"2",
            "remaining_power":55
        },
        {
            "_id":{
                "$oid":"57d64bed26425121e67826db"
            },
            "user":{
                "$oid":"57d6144126425121e8b81864"
            },
            "device":"868219000099926",
            "created_at":{
                "$date":1473690733053
            },
            "time_begin":{
                "$date":1473690731000
            },
            "type":"2",
            "remaining_power":61
        }
    ],
    "page":{
        "page_count":1,
        "rows_per_page":20,
        "total":8,
        "page_current":1
    },
    "success":true,
    "obj_name":"powerdata"
}


# 查看设备定位数据

- 地址: /api/locationdata/?device=[device oid]
- 方法: GET
- 验证方法: Cookie: user
- 响应对象: [locationdata](./object.md#locationdata)
- 请求参数: 

    | 名称            | 必须 | 类型         | 说明                          |
    | --------------- | ---- | ------------ | ------------------------------ |
    | device          | 是   | string       | 15位设备唯一序号              |
    | time_begin      | 否   | string       | YYYYMMDD，查询指定日期的数据  |

__请求范例__
    
    curl -v -A CURL -b cookies.txt http://127.0.0.1:8000/api/locationdata/?device=868219000099926&depth=1&rows_per_page=1

    > GET /api/locationdata/?device=868219000099926 HTTP/1.1
    > User-Agent: CURL
    > Host: 127.0.0.1:8888
    > Accept: */*
    > Cookie: "user="2|1:0|10:1473817034|4:user|16:MTg2ODA1NTUwNzA=|2768bb77396815e5a7ca9fe3c65dc8060943c57aeb078c746faf56036533aa12""

__响应范例__

{
    "objs":[
        {
            "_id":{
                "$oid":"57d785f826425121e678377f"
            },
            "user":{
                "$oid":"57d6144126425121e8b81864"
            },
            "device":"868219000099926",
            "created_at":{
                "$date":1473771128057
            },
            "time_begin":{
                "$date":1473771125000
            },
            "type":"1",
            "is_reply":false,
            "is_track":false,
            "city":"广州市",
            "address":"广东省 广州市 黄埔区 育星路 靠近广州科学城创新大厦C1",
            "point":{
                "type":"Point",
                "coordinates":[
                    113.4574259,
                    23.1670114
                ]
            },
            "cell":[
                {
                    "mcc":"460",
                    "mnc":"0",
                    "lac":9475,
                    "cid":51086,
                    "rssi":5
                },
                {
                    "mcc":"460",
                    "mnc":"0",
                    "lac":9475,
                    "cid":50168,
                    "rssi":-55
                },
                {
                    "mcc":"460",
                    "mnc":"0",
                    "lac":9475,
                    "cid":44588,
                    "rssi":-75
                },
                {
                    "mcc":"460",
                    "mnc":"0",
                    "lac":9475,
                    "cid":43472,
                    "rssi":-81
                },
                {
                    "mcc":"460",
                    "mnc":"0",
                    "lac":9475,
                    "cid":43471,
                    "rssi":-91
                },
                {
                    "mcc":"460",
                    "mnc":"0",
                    "lac":9475,
                    "cid":39506,
                    "rssi":-91
                }
            ],
            "wifi":[
                {
                    "addr":"54:35:30:0c:68:02",
                    "ssid":"HP-HOTSPOT-02-LaserJet M1218",
                    "rssi":-50
                },
                {
                    "addr":"28:c6:8e:39:03:c7",
                    "ssid":"BAIYI0001",
                    "rssi":-52
                },
                {
                    "addr":"00:bd:82:50:25:3d",
                    "ssid":"ChinaNet-a59y",
                    "rssi":-81
                },
                {
                    "addr":"ec:26:ca:ae:37:c6",
                    "ssid":"BiDe_WIFI",
                    "rssi":-84
                },
                {
                    "addr":"c8:3a:35:56:e1:18",
                    "ssid":"gzdiko01",
                    "rssi":-86
                }
            ]
        }
    ],
    "page":{
        "page_count":225,
        "rows_per_page":1,
        "total":225,
        "page_current":1
    },
    "success":true,
    "obj_name":"locationdata"
}


# 查看设备运动数据

- 地址: /api/pedometerdata/?device=[device oid]
- 方法: GET
- 验证方法: Cookie: user
- 响应对象: [pedometerdata](./object.md#pedometerdata)
- 请求参数: 

    | 名称            | 必须 | 类型         | 说明                          |
    | --------------- | ---- | ------------ | ------------------------------ |
    | device          | 是   | string       | 15位设备唯一序号              |
    | time_begin      | 否   | string       | YYYYMMDD，查询指定日期的数据 |

__请求范例__
    
    curl -v -A CURL -b cookies.txt http://127.0.0.1:8888/api/pedometerdata/?device=868219000099926

    > GET /api/pedometerdata/?device=868219000099926 HTTP/1.1
    > User-Agent: CURL
    > Host: 127.0.0.1:8888
    > Accept: */*
    > Cookie: "user="2|1:0|10:1473817034|4:user|16:MTg2ODA1NTUwNzA=|2768bb77396815e5a7ca9fe3c65dc8060943c57aeb078c746faf56036533aa12""

__响应范例__

	   {
	    "objs":[

	    ],
	    "page":{
		"page_count":0,
		"rows_per_page":20,
		"total":0,
		"page_current":1
	    },
	    "success":true,
	    "obj_name":"pedometerdata"
	}

# 查看设备异常数据

# 查看设备心率数据 

- 地址: /api/heartratedata/?device=[device oid]
- 方法: GET
- 验证方法: Cookie: user
- 响应对象: [heartratedata](./object.md#heartratedata)
- 请求参数: 

    | 名称            | 必须 | 类型         | 说明                          |
    | --------------- | ---- | ------------ | ------------------------------ |
    | device          | 是   | string       | 15位设备唯一序号              |
    | time_begin      | 否   | string       | YYYYMMDD，查询指定日期的数据  |

__请求范例__
    
    curl -v -A CURL -b cookies.txt http://127.0.0.1:8888/api/heartratedata/?device=868219000099926&depth=1

    > GET /api/heartratedata/?device=868219000099926 HTTP/1.1
    > User-Agent: CURL
    > Host: 127.0.0.1:8888
    > Accept: */*
    > Cookie: "user="2|1:0|10:1473817034|4:user|16:MTg2ODA1NTUwNzA=|2768bb77396815e5a7ca9fe3c65dc8060943c57aeb078c746faf56036533aa12""

__响应范例__

	{
	    "objs":[
		{
		    "_id":{
			"$oid":"57d6ae6226425121e6782e6e"
		    },
		    "user":{
			"$oid":"57d6144126425121e8b81864"
		    },
		    "device":"868219000099926",
		    "created_at":{
			"$date":1473715938329
		    },
		    "time_begin":{
			"$date":1473715937000
		    },
		    "heartrate":56
		},
		{
		    "_id":{
			"$oid":"57d6a05626425121e6782e1c"
		    },
		    "user":{
			"$oid":"57d6144126425121e8b81864"
		    },
		    "device":"868219000099926",
		    "created_at":{
			"$date":1473712342208
		    },
		    "time_begin":{
			"$date":1473712340000
		    },
		    "heartrate":99
		},
		{
		    "_id":{
			"$oid":"57d6924e26425121e6782dcc"
		    },
		    "user":{
			"$oid":"57d6144126425121e8b81864"
		    },
		    "device":"868219000099926",
		    "created_at":{
			"$date":1473708750514
		    },
		    "time_begin":{
			"$date":1473708747000
		    },
		    "heartrate":94
		},
		{
		    "_id":{
			"$oid":"57d6762126425121e6782ba2"
		    },
		    "user":{
			"$oid":"57d6144126425121e8b81864"
		    },
		    "device":"868219000099926",
		    "created_at":{
			"$date":1473701537864
		    },
		    "time_begin":{
			"$date":1473701536000
		    },
		    "heartrate":55
		},
		{
		    "_id":{
			"$oid":"57d6680e26425121e6782aa5"
		    },
		    "user":{
			"$oid":"57d6144126425121e8b81864"
		    },
		    "device":"868219000099926",
		    "created_at":{
			"$date":1473697934849
		    },
		    "time_begin":{
			"$date":1473697933000
		    },
		    "heartrate":50
		},
		{
		    "_id":{
			"$oid":"57d659fe26425121e67828c4"
		    },
		    "user":{
			"$oid":"57d6144126425121e8b81864"
		    },
		    "device":"868219000099926",
		    "created_at":{
			"$date":1473694334434
		    },
		    "time_begin":{
			"$date":1473694333000
		    },
		    "heartrate":54
		},
		{
		    "_id":{
			"$oid":"57d64bed26425121e67826da"
		    },
		    "user":{
			"$oid":"57d6144126425121e8b81864"
		    },
		    "device":"868219000099926",
		    "created_at":{
			"$date":1473690733030
		    },
		    "time_begin":{
			"$date":1473690731000
		    },
		    "heartrate":68
		}
	    ],
	    "page":{
		"page_count":1,
		"rows_per_page":20,
		"total":7,
		"page_current":1
	    },
	    "success":true,
	    "obj_name":"heartratedata"
	}


# 查看设备睡眠数据

- 地址: /api/sleepdata/?device=[device oid]
- 方法: GET
- 验证方法: Cookie: user
- 响应对象: [sleepdata](./object.md#sleepdata)
- 请求参数: 

    | 名称            | 必须 | 类型         | 说明                          |
    | --------------- | ---- | ------------ | ------------------------------ |
    | device          | 是   | string       | 15位设备唯一序号              |
    | time_begin      | 否   | string       | YYYYMMDD，查询指定日期的数据  |

- 请求范例
    curl -v -A CURL -b cookies.txt 'http://127.0.0.1:8888/api/sleepdata/?device=868219000099926

    > GET /api/sleepdata/?device=868219000099926 HTTP/1.1
    > User-Agent: CURL
    > Host: 127.0.0.1:8888
    > Accept: */*
    > Cookie: "user="2|1:0|10:1473817034|4:user|16:MTg2ODA1NTUwNzA=|2768bb77396815e5a7ca9fe3c65dc8060943c57aeb078c746faf56036533aa12""

__响应范例__
{
    "objs": [
        {
            "_id": {
                "$oid": "596d055d2642510e7ee61311"
            },
            "device": "868219000099988",
            "created_at": {
                "$date": 1500345821546
            },
            "time_begin": {
                "$date": 1500321600000
            },
            "time_end": {
                "$date": 1500357600000
            },
            "interval": 30,
            "total": 20,
            "data": [
                {
                    "turn_over": 255,
                    "state": 0
                },
                {
                    "turn_over": 0,
                    "state": 2
                },
                {
                    "turn_over": 0,
                    "state": 2
                },
                {
                    "turn_over": 0,
                    "state": 2
                },
                {
                    "turn_over": 0,
                    "state": 2
                },
                {
                    "turn_over": 0,
                    "state": 2
                },
                {
                    "turn_over": 0,
                    "state": 2
                },
                {
                    "turn_over": 0,
                    "state": 2
                },
                {
                    "turn_over": 0,
                    "state": 2
                },
                {
                    "turn_over": 0,
                    "state": 2
                },
                {
                    "turn_over": 0,
                    "state": 2
                },
                {
                    "turn_over": 0,
                    "state": 2
                },
                {
                    "turn_over": 0,
                    "state": 2
                },
                {
                    "turn_over": 0,
                    "state": 2
                },
                {
                    "turn_over": 255,
                    "state": 0
                },
                {
                    "turn_over": 255,
                    "state": 0
                },
                {
                    "turn_over": 255,
                    "state": 0
                },
                {
                    "turn_over": 255,
                    "state": 0
                },
                {
                    "turn_over": 255,
                    "state": 0
                },
                {
                    "turn_over": 255,
                    "state": 0
                },
                {
                    "turn_over": 0,
                    "state": 0
                },
                {
                    "turn_over": 0,
                    "state": 0
                },
                {
                    "turn_over": 0,
                    "state": 0
                },
                {
                    "turn_over": 0,
                    "state": 0
                },
                {
                    "turn_over": 0,
                    "state": 0
                },
                {
                    "turn_over": 0,
                    "state": 0
                },
                {
                    "turn_over": 0,
                    "state": 0
                },
                {
                    "turn_over": 0,
                    "state": 0
                },
                {
                    "turn_over": 0,
                    "state": 0
                },
                {
                    "turn_over": 0,
                    "state": 0
                },
                {
                    "turn_over": 0,
                    "state": 0
                },
                {
                    "turn_over": 0,
                    "state": 0
                },
                {
                    "turn_over": 0,
                    "state": 0
                },
                {
                    "turn_over": 0,
                    "state": 0
                },
                {
                    "turn_over": 0,
                    "state": 0
                },
                {
                    "turn_over": 0,
                    "state": 0
                },
                {
                    "turn_over": 0,
                    "state": 0
                },
                {
                    "turn_over": 0,
                    "state": 0
                },
                {
                    "turn_over": 0,
                    "state": 0
                },
                {
                    "turn_over": 0,
                    "state": 0
                },
                {
                    "turn_over": 0,
                    "state": 0
                },
                {
                    "turn_over": 0,
                    "state": 0
                },
                {
                    "turn_over": 0,
                    "state": 0
                },
                {
                    "turn_over": 0,
                    "state": 0
                },
                {
                    "turn_over": 0,
                    "state": 0
                },
                {
                    "turn_over": 0,
                    "state": 0
                },
                {
                    "turn_over": 0,
                    "state": 0
                },
                {
                    "turn_over": 0,
                    "state": 0
                }
            ]
        }
    ],
    "page": {
        "page_count": 48,
        "rows_per_page": 1,
        "total": 48,
        "page_current": 1
    },
    "success": true,
    "obj_name": "sleepdata"
}



# 查看设备血压数据

-   地址:/api/BloodPressureData/?device=[device oid]  
-   方法: GET
-   验证方法: Cookie: user
-   响应对象: [BloodPressureData](./object.md#BloodPressureData)
-   请求参数:
    | 名称            | 必须 | 类型        | 说明                           |
    | --------------- | ---- | ------------| ------------------------------  |
    | device          | 是   | string       | 15位设备唯一序号              |
    | time_begin      | 否   | string       | YYYYMMDD，查询指定日期的数据  |

- 请求范例
    curl -v -A CURL -b cookies.txt 'http://127.0.0.1:8000/api/bloodpressuredata/?device=358551050412329&depth=1&rows_per_page=1'

    > GET /api/BloodPressureData/?device=358551050412329&depth=1&rows_per_page=1 HTTP/1.1
    > User-Agent: CURL
    > Host: 127.0.0.1:8888
    > Accept: */*
    > Cookie: "user='2|1:0|10:1500426685|4:user|12:b3BlcmF0b3I=|00f680f1ea4e9cdf5f175f4bd76cf4c53f953bed74118417b8fc58917f5b926d""
-   响应范例:

{
    "objs": [
        {
            "_id": {
                "$oid": "56905ca8bf483c4658fd8efc"
            },
            "device": "358551050412329",
            "created_at": {
                "$date": 1452330280112
            },
            "time_begin": {
                "$date": 1452330278000
            },
            "dbp": 80,
            "sbp": 115
        }
    ],
    "page": {
        "page_count": 1200,
        "rows_per_page": 1,
        "total": 1200,
        "page_current": 1
    },
    "success": true,
    "obj_name": "bloodpressuredata"
}


# 查看设备紧急呼叫

-   地址: /api/sosdata/?device=[device oid]     跌倒数据 （/api/falldata/?device=[device oid]）
-   方法: GET
-   验证方法: Cookie: user
-   响应对象: [sosdata](./object.md#sosdata)
-   请求参数: 

    | 名称            | 必须 | 类型         | 说明                          |
    | --------------- | ---- | ------------ | ------------------------------ |
    | device          | 是   | string       | 15位设备唯一序号              |
    | time_begin      | 否   | string       | YYYYMMDD，查询指定日期的数据  |

-   请求范例:
    
        curl -v -A CURL -b cookies.txt http://127.0.0.1:8888/api/sosdata/?device=868219000099926

        > GET /api/sosdata/?device=868219000099926 HTTP/1.1
        > User-Agent: CURL
        > Host: 127.0.0.1:8888
        > Accept: */*
        > Cookie: "user="2|1:0|10:1473817034|4:user|16:MTg2ODA1NTUwNzA=|2768bb77396815e5a7ca9fe3c65dc8060943c57aeb078c746faf56036533aa12""

-   响应范例:

	{
	    "objs":[

	    ],
	    "page":{
		"page_count":0,
		"rows_per_page":20,
		"total":0,
		"page_current":1
	    },
	    "success":true,
	    "obj_name":"sosdata"
	}



# 在线设备操作

合法的action如下：

    | action            |  说明                           |
    | ---------------   | ------------------------------ |
    | poweroff          | 关机              |
    | ring              | 响铃              |
    | restart           | 重启              |
    | restore           | 恢复出厂          |
    |record		|环境拾音           |

-   地址: /api/device/[device oid]/[action]
-   方法: POST
-   验证方法: Cookie: user
-   响应对象: 无
-   URL参数: device oid


# 获取在线设备实时数据
合法的action如下：

    | action       |  说明         | 参数及类型 | 返回对象  |
    | --------------- | --------------- | -------- | --------- |
    | get_locationdata    | 获取实时位置    | 无 | 无 |  30秒
    | get_pedometerdata   | 获取计步数据    | 无 | PedometerData |   10秒
    | get_heartratedata   | 获取心率数据    | time(int), interval(int) | HeartRateData |  1分后上服务器取数据

-   地址: /api/device/[device oid]/[action]
-   方法: POST
-   验证方法: Cookie: user
-   响应对象: 见上表
-   URL参数: device oid
-   请求范例:
    
        curl -v -A CURL -b cookies.txt http://127.0.0.1:8000/api/device/868219000099926/get_locationdata

-   响应范例:

        {
	  "success": true
        }


# 获取在线设备WIFI数据

-   地址: /api/device/[device oid]/get_wifi
-   方法: GET/POST
-   验证方法: Cookie: user
-   响应对象: 见上表
-   URL参数: device oid
-   请求范例:
    
        curl -v -A CURL -b cookies.txt http://127.0.0.1:8000/api/device/868219000099926/get_wifi

-   响应范例:

	{
	    "objs":[
		{
		    "addr":"28:c6:8e:39:03:c7",
		    "ssid":"BAIYI0001",
		    "rssi":-50
		},
		{
		    "addr":"54:35:30:0c:68:02",
		    "ssid":"HP-HOTSPOT-02-LaserJet M1218",
		    "rssi":-52
		},
		{
		    "addr":"5c:0e:8b:8d:bf:31",
		    "ssid":"CMCC-FREE",
		    "rssi":-80
		},
		{
		    "addr":"5c:0e:8b:8d:bf:30",
		    "ssid":"CMCC-WEB",
		    "rssi":-82
		}
	    ],
	    "success":true,
	    "obj_name":"wifi"
	}




# 获取设备总览数据

-   地址: /api/device/[device oid]/data/[YYYYMMDD]
-   方法: GET
-   验证方法: Cookie: user
-   响应对象: 返回单个对象，如果对应的数据项有数据，则返回数据对象；如果没有则返回'{}'
-   URL参数: device oid  和 日期YYYYMMDD
-   请求范例:
    
        curl -v -A CURL -b cookies.txt http://127.0.0.1:8000/api/device/868219000099926/data/20160528/

-   响应范例:


	{
	    "obj":{
		"bloodpressuredata":{

		},
		"sleepdata":{

		},
		"pedometerdata":{

		},
		"notification":{
		    "notif_type":"fence",
		    "created_at":{
			"$date":1473718238206
		    },
		    "content":"99926 不在"公园"安全区域",
		    "creater":"868219000099926",
		    "_id":{
			"$oid":"57d6b75e26425121e6782e9e"
		    },
		    "recipient":{
			"$oid":"565ba619bf483c7369e5b4a3"
		    }
		},
		"heartratedata":{

		}
	    },
	    "success":true,
	    "obj_name":""
	}



# 获取设备最新位置数据

-   地址: /api/device/[device oid]/data/locationdata/
-   方法: GET
-   验证方法: Cookie: user
-   响应对象: 返回单个对象，如果对应的数据项有数据，则返回数据对象；如果没有则返回'{}'
-   URL参数: device oid
-   请求参数: 

    | 名称            | 必须 | 类型         | 说明                           |
    | --------------- | ---- | ------------ | ------------------------------ |
    | type            | 否   | string       | 0:Gps定位; 1:基站定位          |

-   请求范例:
    
        curl -v -A CURL -b cookies.txt http://127.0.0.1:8000/api/device/868219000099926/data/locationdata

-   响应范例:

 {
	    "obj":{
		"remaining_power":100,
		"temperature":31,
		"weather":"多云",
		"pm25":32,
		"online":true,
		"locationdata":{
		    "_id":{
			"$oid":"57d78c1426425121e6783862"
		    },
		    "time_begin":{
			"$date":1473772690000
		    },
		    "type":"1",
		    "city":"广州市",
		    "address":"广东省 广州市 黄埔区 观虹路 靠近广州科学城创新大厦C1",
		    "point":{
			"type":"Point",
			"coordinates":[
			    113.4564798,
			    23.167481
			]
		    }
		},
		"wear_flag":0
	    },
	    "success":true,
	    "obj_name":""
	}



# 查看获取失败数据
-   地址: /api/sosdata/getfalidsosdata/
-   方法: GET
-   验证方法: Cookie: user
-   响应对象: 返回单个对象，如果对应的数据项有数据，则返回数据对象；如果没有则返回'{}'
-   权限要求: superuser/operator角色 或 社区成员
-   响应对象: [Community](object.md#community)
-   URL参数: device oid
-   请求参数:
    | 名称            | 必须 | 类型         | 说明                           |
    | --------------- | ---- | ------------ | ------------------------------  |
    | cid             | 否   | string       |机构id                           |
    | statu           | 否   | int          |0未读 1已读 默认为0             |

-   请求范例:
    
        curl -v -A CURL -b cookies.txt http://127.0.0.1:8888/api/sosdata/getfalidsosdata/?cid=58783f74264251579725a840

        > GET api/sosdata/getfalidsosdata/?cid=58783f74264251579725a840 HTTP/1.1
        > User-Agent: CURL
        > Host: 127.0.0.1:8888
        > Accept: */*
        > Cookie: ""2|1:0|10:1502846059|4:user|8:YWRtaW4y|f92dad6929734b005ea153a4585f3c02ea9f7a70432a0410518df8a108030f7d""
-   响应范例:

	{
    "objs": [],
    "page": {
        "page_count": 0,
        "rows_per_page": 20,
        "total": 0,
        "page_current": 1
    },
    "success": true,
    "obj_name": "sosdata"
    }


# 指定数据之前的sos未读数据标记为已读
-   地址: /api/sosdata/readfalidsosdata/
-   方法: GET
-   验证方法: Cookie: user
-   响应对象: 返回单个对象，如果对应的数据项有数据，则返回数据对象；如果没有则返回'{}'
-   权限要求: superuser/operator角色 或 社区成员
-   响应对象: [Community](object.md#community)
-   URL参数: device oid
-   请求参数:
    | 名称            | 必须 | 类型         | 说明                           |
    | --------------- | ---- | ------------ | ------------------------------ |
    | cid             | 否   | string       | 机构id                          |
    | id              | 否   | int          |最后一条已读的SOS数据id         |

-   请求范例:
    
        curl -v -A CURL -b cookies.txt http://127.0.0.1:8888/api/sosdata/readfalidsosdata/?cid=58783f74264251579725a840

        > GET api/sosdata/readfalidsosdata/?cid=58783f74264251579725a840 HTTP/1.1
        > User-Agent: CURL
        > Host: 127.0.0.1:8888
        > Accept: */*
        > Cookie: ""2|1:0|10:1502846059|4:user|8:YWRtaW4y|f92dad6929734b005ea153a4585f3c02ea9f7a70432a0410518df8a108030f7d""
-   响应范例:

	{
	  "success": true
	}


# 通过设备号查找绑定设备的人

-   地址: /api/device/findowner/[device oid]
-   方法: GET
-   验证方法: Cookie: user
-   响应对象: [device](./object.md#device)
-   URL参数:  device oid

-   请求范例:
    
        curl -v -A CURL -b cookies.txt http://127.0.0.1:8888/api/device/findowner/?device=868219000535267

        > GET /api/sosdata/?device=868219000535267 HTTP/1.1
        > User-Agent: CURL
        > Host: 127.0.0.1:8888
        > Accept: */*
        > Cookie: ""2|1:0|10:1502846068|4:user|12:b3BlcmF0b3I=|ed80cacdea72e10579134264bf24e18031772644565c1331545eedd1ed98e12a""

 -   响应范例:

	{
	{
    "obj": {
        "_id": {
            "$oid": "58180d0754625915b6234d02"
        },
        "username": "18302075248",
        "nickname": "测试号",
        "phone": "18302075248",
        "devicetokens": [
            {
                "token_type": "ios",
                "token": "18171adc0301a40e9b1",
                "push_server": "jiguang",
                "is_enable_aliase": false,
                "created_at": {
                    "$date": 1502551136572
                }
            },
            {
                "token_type": "android",
                "token": "100d855909708d3b915",
                "push_server": "jiguang",
                "is_enable_aliase": false,
                "created_at": {
                    "$date": 1502882791029
                }
            }
        ],
        "avatar": "18302075248.png",
        "avatar_url": "/media/avatar/200/18302075248.jpg",
        "gender": "male",
        "devices": [],
        "groups": [
            {
                "$oid": "5911622e546259773f03cb81"
            },
            {
                "$oid": "5971caca546259599dd1ba59"
            }
        ],
        "$community": {},
        "$devices": [],
        "$groups": [
            {
                "_id": {
                    "$oid": "5911622e546259773f03cb81"
                },
                "owner": {
                    "$oid": "58180d0754625915b6234d02"
                },
                "name": "测试号的家"
            },
            {
                "_id": {
                    "$oid": "5971caca546259599dd1ba59"
                },
                "owner": {
                    "$oid": "58180d0754625915b6234d02"
                },
                "name": "我的家"
            }
        ]
    },
    "success": true,
    "obj_name": "person"

	}

    
 

