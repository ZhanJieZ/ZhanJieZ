家庭圈信息
==========


## 家庭圈申请账号

家庭圈指操作人为管理员的普通家庭圈，未找到则创建一个这样的家庭圈；
用提供的参数注册一个新账号，并用该新账号激活腕表；将创建人和新账号都加入家庭圈。


-   地址: /api/group/register
-   方法: POST
-   验证方法: Cookie: user
-   响应对象: group
-   请求参数

    | 名称            | 必须 | 类型         | 说明                           |
    | --------------- | ---- | ------------ | ------------------------------ |
    | group_name      |  否  | string       | 家庭圈名, 缺省为创建人username, 仅第一次申请时有效 |
    | member_name     |  否  | string       | 家庭圈内关系名, 缺省为新建用户username |
    | username        |  是  | string       | 此处指绑定时创建的腕表承载用户的用户名。为保证唯一，一般使用时间戳 |
    | password        |  是  | string       | 此处指绑定时创建的腕表承载用户的密码，一般跟上面用户名相同 |
    | email           |  否  | string       | 不填的话，会使用创建的自己的email   |
    | nickname        |  否  | string       | 设备昵称，在参数传递的时候，因为设计问题，nickname=name，都要上传 |
    | address         |  否  | string       |                                |
    | phone           |  否  | string       | phone=sim_phone，都要上传，设计问题  |
    | deviceid        | 否   | string       | 20位设备序号，使用方法与激活流程一致   |
    | sim_phone       | 否   | string       | 腕表的SIM卡手机号              |
    | sim_phone_type  | 否   | string       | unicom , cmcc, ctcc            |
    | name            | 否   | string       | 腕表名称                       |

-   请求范例

        curl -v -A CURL -b cookies.txt -d "username=member05&password=member05" http://127.0.0.1:8888/api/group/register

        > POST /api/group/register HTTP/1.1
        > User-Agent: CURL
        > Host: 127.0.0.1:8888
        > Accept: */*
        > Cookie: user="2|1:0|10:1408975429|4:user|8:YWRtaW4=|9ffddb70b9d642e1de4649c90dc46dda311f415c8629cf57327badecd2ce41a7"
        > Content-Length: 35
        > Content-Type: application/x-www-form-urlencoded


-   响应范例

        {
          "obj": {
            "name": "admin家", 
            "created_at": {
              "$date": 1409144278771
            }, 
            "members": [
              {
                "person": {
                  "$oid": "53fd661a7fcc8b1b0bd45a56"
                }, 
                "_id": {
                  "$oid": "53fd661a7fcc8b1b0bd45a57"
                }, 
                "group": {
                  "$oid": "53fd65567fcc8b1b0b9bf54c"
                }, 
                "member_name": "member02"
              }, 
              {
                "person": {
                  "$oid": "53fd664e7fcc8b1b0bf83be0"
                }, 
                "_id": {
                  "$oid": "53fd664e7fcc8b1b0bf83be1"
                }, 
                "group": {
                  "$oid": "53fd65567fcc8b1b0b9bf54c"
                }, 
                "member_name": "member03"
              }
            ], 
            "owner": {
              "$oid": "53f726307fcc8b31b85b6ae0"
            }, 
            "is_public": false, 
            "_id": {
              "$oid": "53fd65567fcc8b1b0b9bf54c"
            }, 
            "member_num": 2
          }, 
          "success": true, 
          "obj_name": "group"
        }


## 普通家庭圈邀请账号

家庭圈指操作人为管理员的普通家庭圈，未找到则创建一个这样的家庭圈；
创建人和被邀请人都加入家庭圈。
注：如果用户重复，则返回302

-   地址: /api/group/invite
-   方法: POST
-   验证方法: Cookie: user
-   响应对象: group
-   请求参数

    | 名称            | 必须 | 类型         | 说明                           |
    | --------------- | ---- | ------------ | ------------------------------ |
    | userid          |  否  | string       |                                |
    | username        |  否  | string       | username与userid两个参数必须有一个       |
    | group_name      |  否  | string       | 家庭圈名, 缺省为创建人username, 仅第一次申请时有效 |
    | member_name     |  否  | string       | 家庭圈内关系名, 缺省为新建用户username |

-   请求范例

        curl -v -A CURL -d "member_name=abc&userid=540d1c3c7fcc8b1418bf79f7" -b cookies.txt http://127.0.0.1:8888/api/group/invite/

        > POST /api/group/invite/ HTTP/1.1
        > User-Agent: CURL
        > Host: 127.0.0.1:8888
        > Accept: */*
        > Cookie: user="2|1:0|10:1410233434|4:user|8:dXNlcjA1|600f6c2d7776ea907561966e76cbb31f07e0b331f86eee22d6b8ed52c4ec941e"
        > Content-Length: 47
        > Content-Type: application/x-www-form-urlencoded

-   响应范例

        {
          "obj": {
            "_id": {
              "$oid": "540e745e7fcc8b16d2ed18aa"
            }, 
            "owner": {
              "$oid": "540d1c3c7fcc8b1418bf79f6"
            }, 
            "created_at": {
              "$date": 1410262238206
            }, 
            "name": "user05家", 
            "is_public": false, 
            "members": [
              {
                "_id": {
                  "$oid": "540e745e7fcc8b16d2ed18ab"
                }, 
                "group": {
                  "$oid": "540e745e7fcc8b16d2ed18aa"
                }, 
                "person": {
                  "$oid": "540d1c3c7fcc8b1418bf79f6"
                }, 
                "member_name": "user05"
              }, 
              {
                "_id": {
                  "$oid": "540e745e7fcc8b16d2ed18ac"
                }, 
                "group": {
                  "$oid": "540e745e7fcc8b16d2ed18aa"
                }, 
                "person": {
                  "$oid": "540d1c3c7fcc8b1418bf79f7"
                }, 
                "member_name": "abc"
              }
            ]
          }, 
          "success": true, 
          "obj_name": "group"
        }


## 查看家庭圈信息
-   地址: /api/group/[group id]
-   方法: GET
-   验证方法: Cookie: user
-   权限要求: 小组成员 或 社区管理员
-   响应对象: [group](object.md#group)
-   URL参数: group id
-   请求范例

        curl -v -A CURL -b cookies.txt http://127.0.0.1:8888/api/group/565ba687bf483c7369e5b4a4
        
        > GET /api/group/565ba687bf483c7369e5b4a4 HTTP/1.1
        > User-Agent: CURL
        > Host: 127.0.0.1:8888
        > Accept: */*
        > Cookie: user="2|1:0|10:1408975429|4:user|8:YWRtaW4=|9ffddb70b9d642e1de4649c90dc46dda311f415c8629cf57327badecd2ce41a7"

-   响应范例
	{
	    "obj":{
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
		],
		"$owner":{
		    "_id":{
			"$oid":"565ba619bf483c7369e5b4a3"
		    },
		    "username":"18680555070",
		    "password":"f8cdb04495ded47615258f9dc6a3f4707fd2405434fefc3cbf4ef4e6",
		    "email":"bbbb@abc.com",
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
				"$date":1473775073289
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
		    "lastlogin_ip":"121.32.196.21",
		    "lastlogin_at":{
			"$date":1473775073273
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
		    "devices":[ ],
		    "groups":[
			{
			    "$oid":"565ba687bf483c7369e5b4a4"
			}
		    ]
		},
		"$community":{

		},
		"$members":[
		    {
			"_id":{
			    "$oid":"565ba687bf483c7369e5b4a5"
			},
			"group":{
			    "$oid":"565ba687bf483c7369e5b4a4"
			},
			"person":{
			    "$oid":"565ba619bf483c7369e5b4a3"
			},
			"member_name":"18680555070",
			"is_default":0
		    },
		    {
			"_id":{
			    "$oid":"578f41442642511a2446b9f0"
			},
			"group":{
			    "$oid":"565ba687bf483c7369e5b4a4"
			},
			"person":{
			    "$oid":"56ca84602642512a69ab2b70"
			},
			"member_name":"测试",
			"is_default":0
		    },
		    {
			"_id":{
			    "$oid":"57a40ebe2642514b25a49076"
			},
			"group":{
			    "$oid":"565ba687bf483c7369e5b4a4"
			},
			"person":{
			    "$oid":"57a40ebe2642514b25a49075"
			},
			"member_name":"1470369463162770",
			"is_default":0
		    },
		    {
			"_id":{
			    "$oid":"57d108c4264251061d083074"
			},
			"group":{
			    "$oid":"565ba687bf483c7369e5b4a4"
			},
			"person":{
			    "$oid":"56a5b3142642512b1edfcb00"
			},
			"member_name":"",
			"is_default":0
		    },
		    {
			"_id":{
			    "$oid":"57d6144126425121e8b81865"
			},
			"group":{
			    "$oid":"565ba687bf483c7369e5b4a4"
			},
			"person":{
			    "$oid":"57d6144126425121e8b81864"
			},
			"member_name":"1473647680912",
			"is_default":0
		    }
		]
	    },
	    "success":true,
	    "obj_name":"group"
	}


## 删除成员

向自己管理的小组删除一个或多个成员。

-   地址: /api/group/[group id]/member/delete
-   方法: POST
-   验证方法: Cookie: user
-   权限要求: superuser角色 或 小组管理员 或 社区管理员
-   响应对象: 无
-   请求参数

    | 名称            | 必须 | 类型         | 说明                           |
    | --------------- | ---- | ------------ | ------------------------------ |
    | userid         |  是  | string       | ','逗号分隔的person id            |

-   请求范例

        curl -v -A CURL  -d "userid=56ca84602642512a69ab2b70" -b cookies.txt
	http://127.0.0.1:8000/api/group/565ba687bf483c7369e5b4a4/member/delete?userid=56ca84602642512a69ab2b70

-   响应范例
    
        {
          "success": true
        }


## 查看成员信息

-   地址: /api/group/member/[member id]
-   方法: GET
-   验证方法: Cookie: user
-   权限要求: 小组管理员 或 社区管理员
-   响应对象: [member](object.md#member)
-   URL参数: member id
-   请求范例

        curl -v -A CURL -b cookies.txt  http://127.0.0.1:8888/api/group/member/57d6144126425121e8b81865
        
        > GET /api/group/member/57d6144126425121e8b81865 HTTP/1.1
        > User-Agent: CURL
        > Host: 127.0.0.1:8888
        > Accept: */*
        > Cookie: user="2|1:0|10:1408975429|4:user|8:YWRtaW4=|9ffddb70b9d642e1de4649c90dc46dda311f415c8629cf57327badecd2ce41a7"

-   响应范例

	{
	    "obj":{
		"_id":{
		    "$oid":"57d6144126425121e8b81865"
		},
		"group":{
		    "$oid":"565ba687bf483c7369e5b4a4"
		},
		"person":{
		    "$oid":"57d6144126425121e8b81864"
		},
		"member_name":"1473647680912",
		"is_default":0,
		"$person":{
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
		    "home_wifi":"28:c6:8e:39:03:c7|BAIYI0001",
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
	    "obj_name":"member"
	}

## 查看用户列表

-   地址: /api/group/[group id]/person/list
-   方法: GET
-   验证方法: Cookie: user
-   权限要求: 小组成员
-   响应对象: 自定义
-   URL参数: group id
-   请求范例

        curl -v -A CURL -b cookies.txt http://127.0.0.1:8000/api/group/565ba687bf483c7369e5b4a4/person/list
        
-   响应范例

	{
	    "objs":[
		{
		    "username":"18680555070",
		    "_id":{
			"$oid":"565ba619bf483c7369e5b4a3"
		    },
		    "nickname":"2222",
		    "devices":[

		    ],
		    "avatar_url":"/media/avatar/200/18680555070.jpg"
		},
		{
		    "username":"13380043590",
		    "_id":{
			"$oid":"56a5b3142642512b1edfcb00"
		    },
		    "nickname":"替他",
		    "devices":[

		    ],
		    "avatar_url":"/media/avatar/200/13380043590.jpg"
		},
		{
		    "username":"1470369463162770",
		    "_id":{
			"$oid":"57a40ebe2642514b25a49075"
		    },
		    "nickname":"测试表",
		    "devices":[
			"000000000000004"
		    ],
		    "avatar_url":"/media/avatar/200/male.png"
		},
		{
		    "username":"1473647680912",
		    "_id":{
			"$oid":"57d6144126425121e8b81864"
		    },
		    "nickname":"99926",
		    "devices":[
			"868219000099926"
		    ],
		    "avatar_url":"/media/avatar/200/male.png"
		},
		{
		    "username":"num1",
		    "_id":{
			"$oid":"57d7981526425121eb887b41"
		    },
		    "nickname":null,
		    "devices":[

		    ],
		    "avatar_url":"/media/avatar/200/male.png"
		}
	    ],
	    "page":{
		"page_count":1,
		"rows_per_page":20,
		"total":5,
		"page_current":1
	    },
	    "success":true,
	    "obj_name":"person"
	}

## 查看腕表列表

-   地址: /api/group/[group id]/device/list
-   方法: GET
-   验证方法: Cookie: user
-   权限要求: 小组成员
-   响应对象: [device](object.md#device)
-   URL参数: group id
-   请求范例

        http://127.0.0.1:8000/api/group/565ba687bf483c7369e5b4a4/device/list
        
-   响应范例

	{
	    "objs":[
		{
		    "_id":"000000000000004",
		    "imei":"000000000000004",
		    "imsi":"",
		    "type":"BY102",
		    "sim_phone":"",
		    "sim_phone_type":"unicom",
		    "owner":{
			"$oid":"57a40ebe2642514b25a49075"
		    },
		    "name":"测试表",
		    "lastlogin_at":{
			"$date":1438612847302
		    },
		    "active":false,
		    "online":false,
		    "$owner":{
			"_id":{
			    "$oid":"57a40ebe2642514b25a49075"
			},
			"username":"1470369463162770",
			"nickname":"测试表",
			"devicetokens":[

			],
			"avatar_url":"/media/avatar/200/male.png",
			"community":{
			    "$oid":"57a40e4c2642514b2293e769"
			},
			"gender":"male",
			"devices":[
			    "000000000000004"
			],
			"groups":[
			    {
				"$oid":"565ba687bf483c7369e5b4a4"
			    }
			]
		    }
		},
		{
		    "_id":"868219000099926",
		    "imei":"868219000099926",
		    "imsi":"9460040289008130",
		    "type":"BY102",
		    "sim_phone":"",
		    "sim_phone_type":"unicom",
		    "owner":{
			"$oid":"57d6144126425121e8b81864"
		    },
		    "name":"99926",
		    "lastlogin_at":{
			"$date":1473758218830
		    },
		    "active":false,
		    "online":true,
		    "wear_flag":0,
		    "wear_updated_at":{
			"$date":1473776247443
		    },
		    "$owner":{
			"_id":{
			    "$oid":"57d6144126425121e8b81864"
			},
			"username":"1473647680912",
			"nickname":"99926",
			"devicetokens":[

			],
			"avatar_url":"/media/avatar/200/male.png",
			"gender":"male",
			"devices":[
			    "868219000099926"
			],
			"groups":[
			    {
				"$oid":"565ba687bf483c7369e5b4a4"
			    }
			]
		    }
		}
	    ],
	    "page":{
		"page_count":1,
		"rows_per_page":20,
		"total":2,
		"page_current":1
	    },
	    "success":true,
	    "obj_name":"device"
	}



        

## 编辑成员信息    (需要修复)

自己和小组管理员有权限。

-   地址: /api/group/member/[member id]/edit
-   方法: POST
-   验证方法: Cookie: user
-   权限要求: 小组管理员 或 社区管理员
-   响应对象: 无
-   URL参数: member id
-   请求范例

        curl -v -A CURL -b cookies.txt -d 'member_name=AAA' http://127.0.0.1:8888/api/group/member/53fd829b7fcc8b2582b6cbb0/edit
        
        > POST /api/group/member/53fd829b7fcc8b2582b6cbb0/edit HTTP/1.1
        > User-Agent: CURL
        > Host: 127.0.0.1:8888
        > Accept: */*
        > Cookie: user="2|1:0|10:1408975429|4:user|8:YWRtaW4=|9ffddb70b9d642e1de4649c90dc46dda311f415c8629cf57327badecd2ce41a7"
        > Content-Length: 15
        > Content-Type: application/x-www-form-urlencoded


-   响应范例

        {
          "success": true
        }


## 修改小组信息

-   地址: /api/group/[group id]/edit
-   方法: POST
-   验证方法: Cookie: user
-   权限要求: superuser角色 或 社区管理员 或 组管理员
-   响应对象: 无
-   请求参数

    | 名称            | 必须 | 类型         | 说明                           |
    | --------------- | ---- | ------------ | ------------------------------ |
    | name            |  否  | string       | 社区名                         |
    | owner           |  否  | person id    | 用户id                         |

-   请求范例

        curl -v -A CURL -d  -b cookies.txt http://127.0.0.1:8000/api/group/57d7a1dc26425121e8b8186e/edit

-   响应范例

        {
          "success": true
        }

## 解散小组

-   地址: /api/group/[group id]/disband
-   方法: POST
-   验证方法: Cookie: user
-   权限要求: superuser角色 或 社区管理员 或 组管理员
-   响应对象: 无
-   请求参数: 无
-   请求范例

        curl -v -A CURL -d '' -b cookies.txt http://127.0.0.1:8000/api/group/54c9a2b8e138232861eb77d6/disband

-   响应范例

        {
          "success": true
        }



## 生成邀请码

-   地址: /api/group/[group id]/invite_code/new/
-   方法: POST
-   验证方法: Cookie: user
-   响应对象: groupinvitecode
-   请求参数:无
-   请求范例

        curl -v -A CURL -b cookies.txt http://127.0.0.1:8000/api/group/565ba687bf483c7369e5b4a4/invite_code/new/

-   响应范例

	{
	    "obj":{
		"_id":{
		    "$oid":"565ba687bf483c7369e5b4a4"
		},
		"code":"655127",
		"group":{
		    "$oid":"565ba687bf483c7369e5b4a4"
		},
		"$group":{
		    "_id":{
			"$oid":"565ba687bf483c7369e5b4a4"
		    },
		    "owner":{
			"$oid":"565ba619bf483c7369e5b4a3"
		    },
		    "name":"18680555070家"
		}
	    },
	    "success":true,
	    "obj_name":"groupinvitecode"
	}


## 使用邀请码

-   地址: /api/group/invite_code/confirm/
-   方法: POST
-   验证方法: Cookie: user
-   响应对象: group
-   请求参数:

    | 名称            | 必须 | 类型         | 说明                           |
    | --------------- | ---- | ------------ | ------------------------------ |
    | code            |  是  | string       |                                |

-   请求范例

        curl -v -A CURL -d 'code=655127' -b cookies.txt http://127.0.0.1:8000/api/group/invite_code/confirm?code=655127

-   响应范例

	{
	    "obj":{
		"_id":{
		    "$oid":"565ba687bf483c7369e5b4a4"
		},
		"owner":{
		    "$oid":"565ba619bf483c7369e5b4a3"
		},
		"name":"18680555070家",
		"$owner":{
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
				"$date":1473777434156
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
		    ]
		}
	    },
	    "success":true,
	    "obj_name":"group"
	}


## 当前用户离开小组

-   地址: /api/group/[group id]/leave/
-   方法: POST
-   验证方法: Cookie: user
-   响应对象: 无
-   请求参数: 无
-   请求范例

        curl -v -A CURL -b cookies.txt http://127.0.0.1:8000/api/group/565ba687bf483c7369e5b4a4/leave

-   响应范例

        {
          "success": true
        }


