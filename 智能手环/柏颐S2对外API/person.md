
用户信息
========

# 查看账号信息
-   地址: /api/person/self 或 /api/person/[person oid]
-   方法: GET
-   验证方法: Cookie: user
-   响应对象: [person](./object.md#person)
-   URL参数: person oid
-   请求范例
    
        curl -v -A CURL -b cookies.txt http://127.0.0.1:8888/api/person/self

        > GET /api/person/self HTTP/1.1
        > User-Agent: CURL
        > Host: 127.0.0.1:8888
        > Accept: */*
        > Cookie: "user="2|1:0|10:1473817034|4:user|16:MTg2ODA1NTUwNzA=|2768bb77396815e5a7ca9fe3c65dc8060943c57aeb078c746faf56036533aa12""

-   响应范例

	{
	    "obj":{
		"_id":{
		    "$oid":"565ba619bf483c7369e5b4a3"
		},
		"username":"18680555070",
		"password":"f8cdb04495ded47615258f9dc6a3f4707fd2405434fefc3cbf4ef4e6",
		"nickname":"2222",
		"phone":"18680555070",
		"telephone":"",
		"app":"aiqiangua2.0",
		"devicetokens":[
		    {
			"token_type":"ios",
			"token":"9dc0aa1154ad3c10d28bcbd21dbaa26d0fbc2135b1a6e2a2844517eb5fe5468b",
			"is_enable_aliase":false,
			"created_at":{
			    "$date":1473671277244
			}
		    },
		    {
			"token_type":"android",
			"token":"22dde87aa7bbfde548179ef3933cb60f249592c2",
			"is_enable_aliase":false,
			"created_at":{
			    "$date":1473772757489
			}
		    }
		],
		"weight":0,
		"step":0,
		"age":0,
		"height":0,
		"avatar":"18680555070.png",
		"avatar_url":"/media/avatar/200/18680555070.jpg",
		"role":"user",
		"gender":"male",
		"created_at":{
		    "$date":1448875673502
		},
		"updated_at":{
		    "$date":1448875673502
		},
		"lastlogin_ip":"121.32.197.247",
		"lastlogin_at":{
		    "$date":1473772757475
		},
		"lastlogin_by":"",
		"enable":false,
		"email_is_checked":false,
		"phone_is_checked":true,
		"push_sos_enable":true,
		"push_fence_enable":true,
		"push_abnormal_enable":true,
		"push_message_enable":true,
		"push_lowpower_enable":true,
		"push_system_enable":true,
		"push_fall_enable":true,
		"push_env_enable":true,
		"auth_type":"weixin",
		"auth_uid":"oXm9utw5vTIi4PV4bZtcFFeFJqS8",
		"auth_updated_at":{
		    "$date":1448875673502
		},
		"register_app":"",
		"is_device_owner":false,
		"devices":[

		],
		"groups":[
		    {
			"$oid":"565ba687bf483c7369e5b4a4"
		    }
		],
		"$community":{

		},
		"$devices":[

		],
		"$groups":[
		    {
			"_id":{
			    "$oid":"565ba687bf483c7369e5b4a4"
			},
			"owner":{
			    "$oid":"565ba619bf483c7369e5b4a3"
			},
			"name":"18680555070家",
			"created_at":{
			    "$date":1448875783707
			},
			"is_public":false,
			"members":[
			    {
				"$oid":"565ba687bf483c7369e5b4a5"
			    },
			    {
				"$oid":"578f41442642511a2446b9f0"
			    },
			    {
				"$oid":"57a40ebe2642514b25a49076"
			    },
			    {
				"$oid":"57d108c4264251061d083074"
			    },
			    {
				"$oid":"57d6144126425121e8b81865"
			    }
			]
		    }
		]
	    },
	    "success":true,
	    "obj_name":"person"
	}


# 修改账号信息
-   地址: /api/person/[person oid]/edit
-   方法: POST
-   验证方法: Cookie: user
-   响应对象: [person](./object.md#person)
-   URL参数: person oid
-   请求参数: [person](./object.md#person)

__请求范例__
    
    curl -v -A CURL -b cookies.txt -d "email=bbbb@abc.com" http://127.0.0.1:8888/api/person/565ba619bf483c7369e5b4a3/edit?email=bbbb@abc.com

    > POST /api/person/53eeb1cb7fcc8b0e11a170a7/edit HTTP/1.1
    > User-Agent: CURL
    > Host: 127.0.0.1:8888
    > Accept: */*
    > Cookie: "user="2|1:0|10:1473817034|4:user|16:MTg2ODA1NTUwNzA=|2768bb77396815e5a7ca9fe3c65dc8060943c57aeb078c746faf56036533aa12""
    > Content-Length: 18
    > Content-Type: application/x-www-form-urlencoded

__响应范例__
    
    {
      "success": true
    }\


# 设置口令

-   地址: /api/person/change_passwd  或 /api/person/[person oid]/change_passwd
-   方法: POST
-   验证方法: Cookie: user
-   响应对象: 无

__请求参数__

| 名称         | 必须 | 类型         | 说明                           |
| ------------ | ---- | ------------ | ------------------------------ |
| old_password |  是  | string       |                                |
| password     |  是  | string       | 至少6个字符                    |


__请求范例__
    
     curl -v -A CURL -d 'old_password=123456&password=123456' -b cookies.txt http://127.0.0.1:8888/api/person/change_passwd?old_password=123456&password=123456	
     > POST /api/person/change_passwd HTTP/1.1
     > User-Agent: CURL
     > Host: 127.0.0.1:8888
     > Accept: */*
     > Cookie: "user="2|1:0|10:1473817034|4:user|16:MTg2ODA1NTUwNzA=|2768bb77396815e5a7ca9fe3c65dc8060943c57aeb078c746faf56036533aa12""
     > Content-Length: 34
     > Content-Type: application/x-www-form-urlencoded

__响应范例__
    
    {
      "success": true
    }


#  设置缺省组

被设置的用户必须已经是组的成员才能设置为缺省组。

-   地址: /api/person/change_group  或 /api/person/[person oid]/change_group
-   方法: POST
-   验证方法: Cookie: user
-   响应对象: 无
-   请求参数:

    | 名称         | 必须 | 类型         | 说明                           |
    | ------------ | ---- | ------------ | ------------------------------ |
    | group        |  是  | string       |                                |

-   请求范例:
    
        curl -v -A CURL  -b cookies.txt -d 'group=54d1d3ede138231996630d8c' http://127.0.0.1:8000/api/person/change_group?group=54d1d3ede138231996630d8c

-   响应范例
    
       {
         "success": true
       }


# 修改头像
-   地址: /api/person/change_avatar 或 /api/person/[person oid]/change_avatar
-   方法: POST
-   验证方法: Cookie: user
-   响应对象: 无
-   请求参数

    | 名称         | 必须 | 类型         | 说明                           |
    | ------------   | ----   | ------------   | ------------------------------   |
    | upfile       |  是  | multipart    |                                |

-   请求范例
    
         curl -v -A CURL  -F 'upfile=@2.jpeg' -b cookies.txt http://127.0.0.1:8888/api/person/change_avatar

-   响应范例__
    
        {
          "success": true
        }


# 查找账号

-   地址: /api/person/find
-   方法: GET
-   验证方法: Cookie: user
-   响应对象: [person](./object.md#person)
-   URL参数: 无
-   请求参数

    | 名称           | 必须 | 类型      | 说明                           |
    | -------------- | ---- | --------- | ------------------------------ |
    | small          |  否  | int       |   0/1 是否用简化版本显示person对象, 缺省为0   |
    | username       |  否  | string    |   在 username 中模糊匹配方式查找用户              |
    | nickname       |  否  | string    |   在 nickname 中模糊匹配方式查找用户              |
    | phone          |  否  | string    |   在 phone 中模糊匹配方式查找用户              |
    | email          |  否  | string    |   在 email 中模糊匹配方式查找用户              |
    | imei           |  否  | string    |   在 imei 中模糊匹配方式查找用户              |

-   请求范例
    
        curl -v -A CURL -b cookies.txt 'http://127.0.0.1:8000/api/person/find?phone=18680555070&small=1'

-   响应范例

	{
	    "objs":[
		{
		    "_id":{
			"$oid":"565ba619bf483c7369e5b4a3"
		    },
		    "username":"18680555070",
		    "email":"bbbb@abc.com",
		    "nickname":"2222",
		    "phone":"18680555070",
		    "devicetokens":[
			{
			    "token_type":"ios",
			    "token":"9dc0aa1154ad3c10d28bcbd21dbaa26d0fbc2135b1a6e2a2844517eb5fe5468b",
			    "is_enable_aliase":false,
			    "created_at":{
				"$date":1473671277244
			    }
			},
			{
			    "token_type":"android",
			    "token":"22dde87aa7bbfde548179ef3933cb60f249592c2",
			    "is_enable_aliase":false,
			    "created_at":{
				"$date":1473773865601
			    }
			}
		    ],
		    "avatar":"18680555070.png",
		    "avatar_url":"/media/avatar/200/18680555070.jpg",
		    "gender":"male",
		    "auth_type":"weixin",
		    "auth_uid":"oXm9utw5vTIi4PV4bZtcFFeFJqS8",
		    "register_app":"",
		    "devices":[

		    ],
		    "groups":[
			{
			    "$oid":"565ba687bf483c7369e5b4a4"
			}
		    ],
		    "$community":{

		    },
		    "$devices":[

		    ],
		    "$groups":[
			{
			    "_id":{
				"$oid":"565ba687bf483c7369e5b4a4"
			    },
			    "owner":{
				"$oid":"565ba619bf483c7369e5b4a3"
			    },
			    "name":"18680555070家"
			}
		    ]
		}
	    ],
	    "page":{
		"page_count":1,
		"rows_per_page":20,
		"total":1,
		"page_current":1
	    },
	    "success":true,
	    "obj_name":"person"
	}



注：如需将推送接口接入app，请联系柏颐科技进行联调。推送仅限于app


# 增加推送设备

-   地址: /api/person/attach
-   方法: POST
-   验证方法: Cookie: user
-   响应对象: 无
-   请求参数: 

    | 名称         | 必须 | 类型         | 说明                           |
    | ------------ | ---- | ------------ | ------------------------------ |
    | token        |  是  | string       |                                |
    | token_type   |  否  | string       | ios, android, 缺省ios          |
    | is_enable_aliase |  否  | boolean  | 保留, 缺省False                |

-   请求范例:

        curl -v -A CURL -b cookies.txt -d 'token=d471b6c9243c7fc2483f8d8167c4b04443140eab&token_type=android' 
	http://127.0.0.1:8000/api/person/attach?token=d471b6c9243c7fc2483f8d8167c4b04443140eab&token_type=android

-   响应范例:

        {
          "success": true
        }

# 移除推送设备

-   地址: /api/person/unattach
-   方法: POST
-   验证方法: Cookie: user
-   响应对象: 无
-   请求参数: 

    | 名称         | 必须 | 类型         | 说明                           |
    | ------------ | ---- | ------------ | ------------------------------ |
    | token        |  是  | string       |                                |
    | token_type   |  否  | string       | ios, android, 缺省ios          |

-   请求范例:

        CURL -b cookies.txt -d 'token=d471b6c9243c7fc2483f8d8167c4b04443140eab&token_type=android' 
	http://127.0.0.1:8000/api/person/clear_notification?token=d471b6c9243c7fc2483f8d8167c4b04443140eab&token_type=android       l
-   响应范例:

        {
          "success": true
        }

# 清除推送消息

-   地址: /api/person/clear_notification
-   方法: POST
-   验证方法: Cookie: user
-   响应对象: 无
-   请求参数: 

    | 名称         | 必须 | 类型         | 说明                           |
    | ------------ | ---- | ------------ | ------------------------------ |
    | token        |  是  | string       |                                |
    | token_type   |  否  | string       | ios, android, 缺省ios          |

-   请求范例:

        CURL -b cookies.txt -d 'token=d471b6c9243c7fc2483f8d8167c4b04443140eab&token_type=android' 
	http://127.0.0.1:8000/api/person/clear_notification?token=d471b6c9243c7fc2483f8d8167c4b04443140eab&token_type=android       l
-   响应范例:

        {
          "success": true
        }


# 查看推送的消息

-   地址: /api/notification/
-   方法: GET
-   验证方法: Cookie: user
-   响应对象: 无
-   请求参数: 

    | 名称         | 必须 | 类型         | 说明                           |
    | ------------ | ---- | ------------ | ------------------------------ |
    | token        |  是  | string       |                                |
    | token_type   |  否  | string       | ios, android                   |
    | created_at   |  否  | string       | 表示一个时间范围。YYYYMMDD[HH][-NN] YYYYMMDD为年月日，[]内为可选参数，HH为时，YYYYMMDD[HH]一起描述了开始时间，-NN表示前面时刻之后的多少小时的数据，描述了结束时间 |
    | title        |  否  | string       | 模糊查询输入内容 |

-   请求范例:

        CURL -b cookies.txt http://127.0.0.1:8000/api/notification?token=d471b6c9243c7fc2483f8d8167c4b04443140eab&token_type=android

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
	    "obj_name":"notification"
	}
