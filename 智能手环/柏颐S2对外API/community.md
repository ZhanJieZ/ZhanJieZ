社区信息
========


## 新建社区
	
-   地址: /api/community/new
-   方法: POST
-   验证方法: Cookie: user
-   权限要求: superuser角色
-   响应对象: 无
-   请求参数

  | 名称            | 必须 | 类型         | 说明                           |
  | --------------- | ---- | ------------ | ------------------------------ |
  | name            |  是  | string       | 社区名称，部分社区有服务号同步需求，联系人命名即为该参数  |
  | email           |  是  | string       |                                |
  | administrators  |  是  | string       | 用户id列表，','号分隔          |
  | telephone       |  否  | string       | 社区客服电话，同时也是服务号同步需求中的服务号   |
	
-   请求范例
 
  curl -v -A CURL -b cookies.txt -d 'name=社区A&administrators=54aa9d5ee1382320f7771869,54aa9d5ee1382320f777186b'  http://127.0.0.1:8000/api/community/new
 	
-   响应范例
 
       {
           "success": true
       }


## 查看社区信息

-   地址: /api/community/[community id]
-   方法: GET
-   验证方法: Cookie: user
-   权限要求: superuser/operator角色 或 社区成员
-   响应对象: [Community](object.md#community)
-   请求范例

        curl -v -A CURL -b cookies.txt http://127.0.0.1:8000/api/community/54a38233bf483c6ddfec4b79

-   响应范例

{
    "obj":{
        "_id":{
            "$oid":"54a38233bf483c6ddfec4b79"
        },
        "name":"测试社区",
        "email":"test@test.com",
        "telephone":"13399999999",
        "administrators":[
            {
                "$oid":"53f722d5bf483c5bd03d0a80"
            }
        ],
        "sos_url":"http://test.aiqiangua.com/12349xzOrgan/api/sos/happenSOSAction.do?",
        "location_url":"",
        "sosdata_url":"",
        "heartratedata_url":"",
        "pedometerdata_url":"",
        "sleepdata_url":"",
        "powerdata_url":"",
        "falldata_url":"",
        "token":"",
        "created_at":{
            "$date":1420030643432
        },
        "$administrators":[
            {
                "_id":{
                    "$oid":"53f722d5bf483c5bd03d0a80"
                },
                "username":"user01",
                "password":"d5a99288b270b6c1989975fdb352425913c45e1640b35473ef9370fc",
                "email":"user01@abc.com",
                "nickname":"管理员",
                "phone":"12345612349",
                "telephone":"020-183849339",
                "app":"aiqiangua2.0",
                "devicetokens":[

                ],
                "weight":65,
                "step":60,
                "age":50,
                "height":175,
                "avatar":"user01.tmp",
                "avatar_url":"/media/avatar/200/user01.jpg",
                "community":{
                    "$oid":"54a38233bf483c6ddfec4b79"
                },
                "role":"user",
                "gender":"male",
                "address":"广州",
                "created_at":{
                    "$date":1408734037917
                },
                "updated_at":{
                    "$date":1408734037913
                },
                "lastlogin_ip":"183.61.80.249",
                "lastlogin_at":{
                    "$date":1473846870019
                },
                "lastlogin_by":"Java/1.6.0_25",
                "enable":true,
                "email_is_checked":false,
                "phone_is_checked":false,
                "push_sos_enable":false,
                "push_fence_enable":false,
                "push_abnormal_enable":false,
                "push_message_enable":false,
                "push_lowpower_enable":false,
                "push_system_enable":false,
                "push_fall_enable":true,
                "push_env_enable":true,
                "auth_updated_at":{
                    "$date":1473846882861
                },
                "is_device_owner":false,
                "devices":[
                    "868219000223161"
                ],
                "groups":[
                    {
                        "$oid":"579e0267264251061974b349"
                    }
                ]
            }
        ]
    },
    "success":true,
    "obj_name":"community"
}


## 修改社区信息

-   地址: /api/community/[community id]/edit
-   方法: POST
-   验证方法: Cookie: user
-   权限要求: superuser角色
-   响应对象: 无
-   请求参数:

    | 名称            | 必须 | 类型         | 说明                           |
    | --------------- | ---- | ------------ | ------------------------------ |
    | name            |  否  | string       |                                |
    | email           |  否  | string       |                                |
    | administrators  |  否  | string       | 用户id列表，','号分隔 ，实际使用中仅一个  |
    | telephone       |  否  | string       |                                |

-   请求范例

        curl -v -A CURL -b cookies.txt -d 'name=社区B'  http://127.0.0.1:8000/api/community/54aa9e5ce1382320ab39bce0/edit

-   响应范例

        {
          "success": true
        }

## 查看全部成员信息

-   地址: /api/community/[comunity id]/members/
-   方法: GET
-   验证方法: Cookie: user
-   响应对象: [Person](object.md#person) *简化*
-   请求参数: 注：以下三个参数同一次只能使用一个

    | 名称            | 必须 | 类型         | 说明                           |
    | --------------- | ---- | ------------ | ------------------------------ |
    | groupid         |  否  | string       | 'groupid='表示查无小组成员     |
    | haveDevice      |  否  | int          | 0/1, 是否拥有设备              |
    | imei            |  否  | string       | 拥有该设备的用户               |

-   请求范例

        curl -v -A CURL -b cookies.txt http://127.0.0.1:8000/api/community/54a38233bf483c6ddfec4b79/members?rows_per_page=1

-   响应范例

	{
	    "objs":[
		{
		    "_id":{
			"$oid":"53f722d5bf483c5bd03d0a80"
		    },
		    "username":"user01",
		    "email":"user01@abc.com",
		    "nickname":"管理员",
		    "phone":"12345612349",
		    "devicetokens":[

		    ],
		    "avatar":"user01.tmp",
		    "avatar_url":"/media/avatar/200/user01.jpg",
		    "community":{
			"$oid":"54a38233bf483c6ddfec4b79"
		    },
		    "gender":"male",
		    "devices":[
			"868219000223161"
		    ],
		    "groups":[
			{
			    "$oid":"579e0267264251061974b349"
			}
		    ],
		    "$community":{
			"_id":{
			    "$oid":"54a38233bf483c6ddfec4b79"
			},
			"name":"测试社区",
			"telephone":"13399999999",
			"administrators":[
			    {
				"$oid":"53f722d5bf483c5bd03d0a80"
			    }
			]
		    },
		    "$devices":[
			{
			    "_id":"868219000223161",
			    "imei":"868219000223161",
			    "imsi":"9460040289007325",
			    "type":"BY102",
			    "sim_phone":"868219000223161",
			    "sim_phone_type":"unicom",
			    "owner":{
				"$oid":"53f722d5bf483c5bd03d0a80"
			    },
			    "name":"测试1",
			    "lastlogin_at":{
				"$date":1470578992979
			    },
			    "active":true,
			    "online":false,
			    "wear_flag":1,
			    "wear_updated_at":{
				"$date":1470523618034
			    }
			}
		    ],
		    "$groups":[
			{
			    "_id":{
				"$oid":"579e0267264251061974b349"
			    },
			    "owner":{
				"$oid":"53f722d5bf483c5bd03d0a80"
			    },
			    "name":"jia"
			}
		    ]
		}
	    ],
	    "page":{
		"page_count":587,
		"rows_per_page":1,
		"total":587,
		"page_current":1
	    },
	    "success":true,
	    "obj_name":"person"
	}


## 查看全部社区小组

-   地址: /api/community/[comunity id]/groups/
-   方法: GET
-   验证方法: Cookie: user
-   响应对象: [Group](object.md#group) *简化*
-   请求范例

        curl -v -A CURL -b cookies.txt http://127.0.0.1:8000/api/community/54a38233bf483c6ddfec4b79/groups?rows_per_page=2

-   响应范例

	{
	    "objs":[
		{
		    "_id":{
			"$oid":"579e0267264251061974b349"
		    },
		    "owner":{
			"$oid":"53f722d5bf483c5bd03d0a80"
		    },
		    "name":"jia",
		    "$owner":{
			"_id":{
			    "$oid":"53f722d5bf483c5bd03d0a80"
			},
			"username":"user01",
			"email":"user01@abc.com",
			"nickname":"管理员",
			"phone":"12345612349",
			"devicetokens":[

			],
			"avatar":"user01.tmp",
			"avatar_url":"/media/avatar/200/user01.jpg",
			"community":{
			    "$oid":"54a38233bf483c6ddfec4b79"
			},
			"gender":"male",
			"devices":[
			    "868219000223161"
			],
			"groups":[
			    {
				"$oid":"579e0267264251061974b349"
			    }
			]
		    }
		},
		{
		    "_id":{
			"$oid":"56444185bf483c0560ecd41f"
		    },
		    "owner":{
			"$oid":"55d94e93bf483c3bf9a80b45"
		    },
		    "name":"6666",
		    "$owner":{
			"_id":{
			    "$oid":"55d94e93bf483c3bf9a80b45"
			},
			"username":"000000000000012",
			"email":"test@test.com",
			"nickname":"阿一",
			"phone":"13164541262",
			"devicetokens":[

			],
			"avatar_url":"/media/avatar/200/male.png",
			"community":{
			    "$oid":"54a38233bf483c6ddfec4b79"
			},
			"gender":"male",
			"devices":[
			    "000000000000012"
			],
			"groups":[
			    {
				"$oid":"56444185bf483c0560ecd41f"
			    }
			]
		    }
		}
	    ],
	    "page":{
		"page_count":4,
		"rows_per_page":2,
		"total":7,
		"page_current":1
	    },
	    "success":true,
	    "obj_name":"group"
	}


## 邀请账号到社区

邀请一个账号到邀请者自己所在的社区。

限制：被邀请人目的社区属性必须为空，否则将提示邀请失败。

-   地址: /api/community/invite
-   方法: POST
-   验证方法: Cookie: user
-   权限要求: superuser角色 或 社区管理员
-   响应对象: 无
-   请求参数:

    | 名称            | 必须 | 类型         | 说明                           |
    | --------------- | ---- | ------------ | ------------------------------ |
    | username        |  否  | string       |                             |
    | userid          |  否  | string       | username/userid 必须有其中一个参数         |
    | note            |  否  | string       | 留言                           |

-   返回码: 1000-未指定用户; 1001-指定的用户不存在； 1002-用户已经在社区

-   请求范例

        curl -v -A CURL -b cookies.txt -d 'userid=54aa9d5ee1382320f7771874'  http://127.0.0.1:8000/api/community/invite

-   响应范例

        {
          "success": true
        }




## 解除成员

消除用户的社区属性。解除社区关系不需要用户确认。

-   地址: /api/person/[person id]/uncommunity
-   方法: POST
-   验证方法: Cookie: user
-   权限要求: superuser角色 或 社区管理员
-   响应对象: 无
-   请求参数

    | 名称            | 必须 | 类型         | 说明                           |
    | --------------- | ---- | ------------ | ------------------------------ |
    | userid          |  是  | string       |                                |

-   请求范例

        curl -v -A CURL -b cookies.txt  http://127.0.0.1:8000/api/person/54aa9d5ee1382320f7771874/uncommunity

-   响应范例

        {
          "success": true
        }


## 申请加入社区

用户必须不在任何社区，并且操作人对用户有修改权限。如果操作人同时也是指定的社区管理员，则直接加入，不需要再次接受。

-   地址: /api/community/join
-   方法: POST
-   验证方法: Cookie: user
-   响应对象: 无
-   请求参数

    | 名称            | 必须 | 类型         | 说明                           |
    | --------------- | ---- | ------------ | ------------------------------ |
    | community_name  |  是  | string       | 社区名称                       |
    | userid          |  是  | string       | 需加入社区的人                 |
    | note            |  否  | string       | 留言                           |

-   返回码: 1000-未指定用户; 1001-指定的用户不存在； 1002-用户已经在社区

-   请求范例

         curl -v -A CURL -b cookies.txt -d "userid=550d3d4ce138236678cc6309&community_name=ABCDEF" http://127.0.0.1:8000/api/community/join

-   响应范例

        {
          "success": true
        }



## 申请离开社区

申请清除用户的社区属性。解除社区关系需要社区管理员确认。
用户必须在社区，并且操作人对用户有修改权限。如果操作人同时也是社区管理员，则直接离开，不需要等社区管理员接受。

注：解除后会自动退出所有该社区的群。

-   地址: /api/community/leave
-   方法: POST
-   验证方法: Cookie: user
-   响应对象: 无
-   请求参数

    | 名称            | 必须 | 类型         | 说明                           |
    | --------------- | ---- | ------------ | ------------------------------ |
    | userid          |  是  | string       | 需离开社区的人                 |

-   请求范例

        curl -v -A CURL -b cookies.txt -d "userid=550d3d4ce138236678cc6309&community_name=ABCDEF" http://127.0.0.1:8000/api/community/leave

-   响应范例


## 查看社区关系相关消息

查看与社区邀请和解除信息，根据小组的管理关系，操作员能查到有编辑权限的用户消息，包括用户发出和用户收到的。
如果是社区管理员，则同时能查到社区内全部消息。

-   地址: /api/community/messages
-   方法: GET
-   验证方法: Cookie: user
-   响应对象: [CommunityMessage](object.md#communitymessage)
-   请求参数: 无
-   请求范例:

        curl -v -A CURL -b cookies.txt http://127.0.0.1:8000/api/community/messages/

-   响应范例

	{
	    "objs":[
		{
		    "_id":{
			"$oid":"5510bcbdbf483c04441618dc"
		    },
		    "_cls":"SysMessage.CommunityMessage.CommunityJoinMessage",
		    "subject":"(15521267470)申请让(15521267777)加入社区(测试社区)",
		    "type":"community_join",
		    "sender":{
			"$oid":"54f13983bf483c0630a01a37"
		    },
		    "sender_note":"",
		    "recipient":{
			"$oid":"54f7f391bf483c296f1e5138"
		    },
		    "created_at":{
			"$date":1427189053605
		    },
		    "result":"reject",
		    "accept_at":{
			"$date":1427209350221
		    },
		    "recipient_note":"",
		    "community":{
			"$oid":"54a38233bf483c6ddfec4b79"
		    },
		    "$sender":{
			"_id":{
			    "$oid":"54f13983bf483c0630a01a37"
			},
			"username":"15521267470",
			"password":"d5a99288b270b6c1989975fdb352425913c45e1640b35473ef9370fc",
			"email":"1558818266@qq.com",
			"nickname":"蝙蝠侠",
			"phone":"15521267470",
			"telephone":"155212674701",
			"app":"aiqiangua2.0",
			"devicetokens":[

			],
			"weight":60,
			"step":0,
			"age":1,
			"height":168,
			"avatar":"15521267470.tmp",
			"avatar_url":"/media/avatar/200/15521267470.jpg",
			"community":{
			    "$oid":"54a38233bf483c6ddfec4b79"
			},
			"role":"user",
			"gender":"male",
			"address":"吉山幼儿园",
			"created_at":{
			    "$date":1425123843243
			},
			"updated_at":{
			    "$date":1425123843243
			},
			"lastlogin_ip":"121.32.196.21",
			"lastlogin_at":{
			    "$date":1473846822111
			},
			"lastlogin_by":"Mozilla/5.0",
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
			    "$date":1473849129714
			},
			"is_device_owner":false,
			"devices":[

			],
			"groups":[
			    {
				"$oid":"57bfe5032642510434c613f7"
			    }
			]
		    },
		    "$recipient":{
			"_id":{
			    "$oid":"54f7f391bf483c296f1e5138"
			},
			"username":"15521267777",
			"password":"f8cdb04495ded47615258f9dc6a3f4707fd2405434fefc3cbf4ef4e6",
			"email":"1558818266@qq.com",
			"nickname":"15521267777",
			"phone":"15521267777",
			"telephone":"",
			"app":"aiqiangua2.0",
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
			    "$date":1425564689161
			},
			"updated_at":{
			    "$date":1425564689161
			},
			"lastlogin_ip":"113.96.10.10",
			"lastlogin_at":{
			    "$date":1438013785434
			},
			"lastlogin_by":"aiqiangua/1.0",
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
			    "$date":1473849129719
			},
			"is_device_owner":false,
			"devices":[

			],
			"groups":[

			]
		    },
		    "$community":{
			"_id":{
			    "$oid":"54a38233bf483c6ddfec4b79"
			},
			"name":"测试社区",
			"email":"test@test.com",
			"telephone":"13399999999",
			"administrators":[
			    {
				"$oid":"53f722d5bf483c5bd03d0a80"
			    }
			],
			"sos_url":"http://test.aiqiangua.com/12349xzOrgan/api/sos/happenSOSAction.do?",
			"location_url":"",
			"sosdata_url":"",
			"heartratedata_url":"",
			"pedometerdata_url":"",
			"sleepdata_url":"",
			"powerdata_url":"",
			"falldata_url":"",
			"token":"",
			"created_at":{
			    "$date":1420030643432
			}
		    }
		}
	    ],
	    "page":{
		"page_count":4,
		"rows_per_page":1,
		"total":4,
		"page_current":1
	    },
	    "success":true,
	    "obj_name":"communitymessage"
	}


## 查看社区消息

-   地址: /api/community/message/[message id]
-   方法: GET
-   验证方法: Cookie: user
-   响应对象: [CommunityMessage](object.md#communitymessage)
-   请求参数: 无
-   请求范例:

        curl -v -A CURL -b cookies.txt http://127.0.0.1:8000/api/community/message/5510bcbdbf483c04441618dc&depth=1

-   响应范例
{
    "obj":{
        "_id":{
            "$oid":"5510bcbdbf483c04441618dc"
        },
        "_cls":"SysMessage.CommunityMessage.CommunityJoinMessage",
        "subject":"(15521267470)申请让(15521267777)加入社区(测试社区)",
        "type":"community_join",
        "sender":{
            "$oid":"54f13983bf483c0630a01a37"
        },
        "sender_note":"",
        "recipient":{
            "$oid":"54f7f391bf483c296f1e5138"
        },
        "created_at":{
            "$date":1427189053605
        },
        "result":"reject",
        "accept_at":{
            "$date":1427209350221
        },
        "recipient_note":"",
        "community":{
            "$oid":"54a38233bf483c6ddfec4b79"
        },
        "$sender":{
            "_id":{
                "$oid":"54f13983bf483c0630a01a37"
            },
            "username":"15521267470",
            "password":"d5a99288b270b6c1989975fdb352425913c45e1640b35473ef9370fc",
            "email":"1558818266@qq.com",
            "nickname":"蝙蝠侠",
            "phone":"15521267470",
            "telephone":"155212674701",
            "app":"aiqiangua2.0",
            "devicetokens":[

            ],
            "weight":60,
            "step":0,
            "age":1,
            "height":168,
            "avatar":"15521267470.tmp",
            "avatar_url":"/media/avatar/200/15521267470.jpg",
            "community":{
                "$oid":"54a38233bf483c6ddfec4b79"
            },
            "role":"user",
            "gender":"male",
            "address":"吉山幼儿园",
            "created_at":{
                "$date":1425123843243
            },
            "updated_at":{
                "$date":1425123843243
            },
            "lastlogin_ip":"121.32.196.21",
            "lastlogin_at":{
                "$date":1473846822111
            },
            "lastlogin_by":"Mozilla/5.0",
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
                "$date":1473850563715
            },
            "is_device_owner":false,
            "devices":[

            ],
            "groups":[
                {
                    "$oid":"57bfe5032642510434c613f7"
                }
            ]
        },
        "$recipient":{
            "_id":{
                "$oid":"54f7f391bf483c296f1e5138"
            },
            "username":"15521267777",
            "password":"f8cdb04495ded47615258f9dc6a3f4707fd2405434fefc3cbf4ef4e6",
            "email":"1558818266@qq.com",
            "nickname":"15521267777",
            "phone":"15521267777",
            "telephone":"",
            "app":"aiqiangua2.0",
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
                "$date":1425564689161
            },
            "updated_at":{
                "$date":1425564689161
            },
            "lastlogin_ip":"113.96.10.10",
            "lastlogin_at":{
                "$date":1438013785434
            },
            "lastlogin_by":"aiqiangua/1.0",
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
                "$date":1473850563720
            },
            "is_device_owner":false,
            "devices":[

            ],
            "groups":[

            ]
        },
        "$community":{
            "_id":{
                "$oid":"54a38233bf483c6ddfec4b79"
            },
            "name":"测试社区",
            "email":"test@test.com",
            "telephone":"13399999999",
            "administrators":[
                {
                    "$oid":"53f722d5bf483c5bd03d0a80"
                }
            ],
            "sos_url":"http://test.aiqiangua.com/12349xzOrgan/api/sos/happenSOSAction.do?",
            "location_url":"",
            "sosdata_url":"",
            "heartratedata_url":"",
            "pedometerdata_url":"",
            "sleepdata_url":"",
            "powerdata_url":"",
            "falldata_url":"",
            "token":"",
            "created_at":{
                "$date":1420030643432
            }
        }
    },
    "success":true,
    "obj_name":"communitymessage"
}


## 处理社区关系相关消息

社区相关消息的进一步处理，根据邀请消息序号接受或拒绝加入社区的邀请。

注：管理员可使用'cancel'和'delete', 目标对象可以使用'accept'和'reject'
注：处于'close'状态的消息不能再进行处理。

-   地址: /api/community/message/[message id]/[accept|reject|cancel|delete]/
-   方法: POST
-   验证方法: Cookie: user
-   响应对象: 
-   请求参数: 无

-   请求范例

        curl -v -A CURL -b cookies.txt  http://127.0.0.1:8000/api/community/message/54ab81d2e1382330f932f097/accept

-   响应范例

        {
          "success": true
        }


## 新建社区小组

-   地址: /api/community/[community id]/group/new
-   方法: POST
-   验证方法: Cookie: user
-   权限要求: superuser角色 或 社区管理员
-   响应对象: 无
-   请求参数

    | 名称            | 必须 | 类型         | 说明                           |
    | --------------- | ---- | ------------ | ------------------------------ |
    | name            |  是  | string       | 社区名                         |
    | owner           |  是  | person id    | 用户id                         |

-   请求范例

        curl -v -A CURL -b cookies.txt -d 'name=社区小组&owner=54aa9d5ee1382320f7771874'  http://127.0.0.1:8000/api/community/group/new

-   响应范例

        {
          "success": true
        }

##  导入用户  注：导入文件格式为CSV，编码格式为utf-8，对imei号做字符串处理

导入文件中的字段包括： deviceid , sim_phone, sim_phone_type , sos_number1 ~ sos_number4, group_name, member_name, username, password, email, nickname, address, phone等

-   地址: /api/community/[community id]/import_user
-   方法: POST
-   验证方法: Cookie: user
-   权限要求: superuser角色 或 社区管理员
-   响应对象: 无
-   请求参数

    | 名称            | 必须 | 类型         | 说明                           |
    | --------------- | ---- | ------------ | ------------------------------ |
    | upfile       |  是  | multipart    |                                |

-   请求范例

        curl -v -A CURL  -F 'upfile=@user.csv' -b cookies.txt http://127.0.0.1:8000/api/community/54c883a4e138230e8f7b5273/import_user

-   响应范例

        {
          "success": true
        }

##  增加用户

-   地址: /api/community/[community id]/add_user
-   方法: POST
-   验证方法: Cookie: user
-   权限要求: superuser角色 或 社区管理员
-   响应对象: 无
-   请求参数

    | 名称            | 必须 | 类型         | 说明                           |
    | --------------- | ---- | ------------ | ------------------------------ |
    | deviceid        |  是  | string       |                                |
    | group_name      |  否  | string       |                                |
    | ...             |  否  | string       |  其它可选字段处理方式与import_user接口一致  |

-   请求范例
-说明先调用validate接口，如果返回403证明设备有拥有人，已经被app绑定过，这个接口不能使用，
可以改用invite接口邀请拥有人进入机构
        curl -v -A CURL  -d "deviceid=86821900003303112345&group_name=小组十" -b cookies.txt
	http://127.0.0.1:8000/api/community/54c883a4e138230e8f7b5273/add_user

-   响应范例

        {
          "success": true
        }

## 查找社区

-   地址: /api/community/find
-   方法: POST
-   验证方法: Cookie: user
-   权限要求: 无
-   响应对象: 无
-   请求参数

    | 名称            | 必须 | 类型         | 说明                           |
    | --------------- | ---- | ------------ | ------------------------------ |
    | name            |  否  | string       | 模糊匹配name                   |

-   请求范例

        curl -v -A CURL -b cookies.txt http://127.0.0.1:8000/api/community/find?name=测

-   响应范例

	{
	    "objs":[
		{
		    "_id":{
			"$oid":"563074fabf483c33c6d44a32"
		    },
		    "name":"广州测试",
		    "telephone":"13113777337",
		    "administrators":[
			{
			    "$oid":"56307403bf483c33c6d44a2c"
			}
		    ],
		    "$administrators":[
			{
			    "_id":{
				"$oid":"56307403bf483c33c6d44a2c"
			    },
			    "username":"13113777337",
			    "phone":"13113777337",
			    "devicetokens":[
				{
				    "token_type":"ios",
				    "token":"6d2486e70295ef83082144b0b341d4e9c5a14b80ff1fd5f5e701b36ad5b1b662",
				    "is_enable_aliase":false,
				    "created_at":{
					"$date":1447088681977
				    }
				}
			    ],
			    "avatar_url":"/media/avatar/200/male.png",
			    "community":{
				"$oid":"563074fabf483c33c6d44a32"
			    },
			    "gender":"male",
			    "devices":[
				"868219000079910"
			    ],
			    "groups":[
				{
				    "$oid":"5630742bbf483c33c6d44a2d"
				}
			    ]
			}
		    ]
		},
		{
		    "_id":{
			"$oid":"54a38233bf483c6ddfec4b79"
		    },
		    "name":"测试社区",
		    "telephone":"13399999999",
		    "administrators":[
			{
			    "$oid":"53f722d5bf483c5bd03d0a80"
			}
		    ],
		    "$administrators":[
			{
			    "_id":{
				"$oid":"53f722d5bf483c5bd03d0a80"
			    },
			    "username":"user01",
			    "email":"user01@abc.com",
			    "nickname":"管理员",
			    "phone":"12345612349",
			    "devicetokens":[

			    ],
			    "avatar":"user01.tmp",
			    "avatar_url":"/media/avatar/200/user01.jpg",
			    "community":{
				"$oid":"54a38233bf483c6ddfec4b79"
			    },
			    "gender":"male",
			    "devices":[
				"868219000223161"
			    ],
			    "groups":[
				{
				    "$oid":"579e0267264251061974b349"
				}
			    ]
			}
		    ]
		}
	    ],
	    "page":{
		"page_count":1,
		"rows_per_page":20,
		"total":2,
		"page_current":1
	    },
	    "success":true,
	    "obj_name":"community"
	}



