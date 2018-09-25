
身份验证
========

# 申请短信验证码

同一手机号1分钟内只允许申请一次短信验证码，一个验证码在5分钟内有效，只能使用一次。 


-   地址: /api/sms/request
-   方法: POST
-   身份验证: 否
-   响应对象: 无
-   请求参数

    | 名称            | 必须 | 类型         | 说明                           |
    | --------------- | ---- | ------------ | ------------------------------ |
    | phone           |  是  | string       | 手机号码 |
    | purpose         |  否  | string       | 申请验证码的用途，register:注册; password:动态密码; reset:用于重置密码;(缺省值，登录) |
    | app             |  否  | string       | 应用名，缺省值aiqiangua; 如果用户有单独的app，或者自行开发app并需要使用爱牵挂的推送服务，则该参数必填，且要在爱牵挂服务器上预注册  |

-   请求范例

	
        curl -v -A CURL -d "phone=13300000000&purpose=password" http://127.0.0.1:/api/sms/request


-   响应范例

        {
          "success": true
        }



# 第三方验证


成功则自动登录，返回用户信息和cookies。失败给出相应返回码（103:用户不存在）。

-   地址: /api/auth/authorize
-   方法: POST
-   身份验证: 否
-   响应对象: [person](./object.md#person) *简化*
-   请求参数:

    | 名称         | 必须 | 类型         | 说明                           |
    | ------------ | ---- | ------------ | ------------------------------ |
    | auth_type    |  是  | string       | weibo/weixin/qq                |
    | auth_uid     |  是  | string       |                                |
    | app          |  否  | string       |  应用名，缺省值aiqiangua，同/api/sms/request参数说明    |

-   请求范例
        
        curl -v -A CURL -d "auth_type=weibo&auth_uid=weibo_111" -c cookies.txt http://127.0.0.1:8000/api/auth/authorize?small=1

-   响应范例

        {
          "obj": {
            "_id": {
              "$oid": "5565e3e97f18883d8eeb1b64"
            }, 
            "username": "user14", 
            "phone": "11111111112", 
            "devicetokens": [], 
            "avatar_url": "/media/avatar/200/male.png", 
            "role": "user", 
            "devices": [], 
            "groups": [], 
            "$community": {}, 
            "$devices": [], 
            "$groups": []
          }, 
          "success": true, 
          "obj_name": "person"
        }


# 第三方账号绑定(待开发)

已登录用户，关联第三方账号，如果第三方账号已在系统内，返回失败。

-   地址: /api/auth/bind
-   方法: POST
-   身份验证: cookies
-   响应对象: [person](./object.md#person) *简化*
-   请求参数:

    | 名称         | 必须 | 类型         | 说明                           |
    | ------------ | ---- | ------------ | ------------------------------ |
    | auth_type    |  是  | string       | weibo/weixin/qq                |
    | auth_uid     |  是  | string       |                                |


# 第三方账号解除绑定(待开发)

已登录用户，解决第三方账号关联。

-   地址: /api/auth/unbind
-   方法: POST
-   身份验证: cookies
-   响应对象: [person](./object.md#person) *简化*
-   请求参数:

    | 名称         | 必须 | 类型         | 说明                           |
    | ------------ | ---- | ------------ | ------------------------------ |
    | auth_type    |  是  | string       | weibo/weixin/qq                |
    | auth_uid     |  是  | string       |                                |



# 注册账号

限制：username必须没有使用，如果提供了auth_uid参数，必须在系统内没有被其它账号绑定; 如果提供了phone参数，必须在系统中没有被其它账号使用。
      先调用“申请短信验证码”接口，获取动态验证(注册register)，再调用这个注册接口，的phone填刚才获取动态验证的手机号，phone_checksum填获取到的验证码。
-   地址: /api/auth/register
-   方法: POST
-   响应对象: none
-   请求参数

    | 名称         | 必须 | 类型         | 说明                           |
    | ------------ | ---- | ------------ | ------------------------------ |
    | username     |  是  | string       |   |
    | password     |  是  | string       |                                |
    | auth_type    |  否  | string       | weibo/weixin/qq                |
    | auth_uid     |  否  | string       | 必须与auth_type同时出现。用于已经第三方认证通过后，登录系统返回用户不存在，app立即注册新用户 |
    | phone        |  否  | string       | 注意，必须是app注册人的手机号，而非腕表手机号       |
    | phone_checksum   |  否  | string   | 必须与phone同时出现，表示phone所有人      |
    | email        |  否  | string       |                                |
    | nickname        |  否  | string       |                                |
    | avatar_url        |  否  | string       |                                |
    | gander        |  否  | string       | male,female                                |
    | push_sos_enable |  否  | bool       | 0,1                                |
    | push_fence_enable |  否  | bool       | 0,1                                |
    | push_abnormal_enable |  否  | bool       | 0,1                                |
    | push_message_enable |  否  | bool       | 0,1                                |
    | push_lowpower_enable |  否  | bool       | 0,1                                |
    | push_system_enable |  否  | bool       | 0,1                                |

-   请求范例
    
        curl -v -A CURL -d "username=user14&password=111111&phone=11111111112&phone_checksum=111111&auth_type=weibo&auth_uid=weibo_111" http://127.0.0.1:8000/api/auth/register

-   响应范例
    
        {
          "success": true
        }


# 登录

-   地址: /api/auth/login
-   方法: POST
-   响应对象: [person](./object.md#person) *简化*
-   请求参数:

    | 名称         | 必须 | 类型         | 说明                           |
    | ------------ | ---- | ------------ | ------------------------------ |
    | username     |  是  | string       |  填用户名或手机号              |
    | password     |  是  | string       |  填用户密码或短信密码          |
    | app          |  否  | string       |  应用名，缺省值aiqiangua  app参数就是用来关联推送的，如果你们想我们服务器直接往你们app那边发推送就要填这个参数，同时提供对应的信鸽appid secret key |
  

-   请求范例:
    
        curl -v -A CURL -d "username=demo&password=admin" -c cookies.txt http://127.0.0.1:8888/api/auth/login

-   响应Cookie:
    
        Set-Cookie: user="2|1:0|10:1407508841|4:user|8:YWRtaW4=|19bf2a8edd510eca173cecff546c446e3d800ae34ca3649ec56a566d2386e0de"; expires=Sun, 07 Sep 2014 14:40:41 GMT; Path=/

-   响应范例:  

        {
            {
                "obj": {
                    "_id": {
                        "$oid": "53f722d5bf483c5bd03d0a80"
                    },
                    "username": "user01",
                    "email": "user01@abc.com",
                    "nickname": "管理员",
                    "phone": "12345612349",
                    "devicetokens": [],
                    "avatar": "user01.tmp",
                    "avatar_url": "/media/avatar/200/user01.jpg",
                    "community": {
                        "$oid": "54a38233bf483c6ddfec4b79"
                    },
                    "gender": "male",
                    "devices": [
                    ],
                    "groups": [
                        {
                            "$oid": "579e0267264251061974b349"
                        }
                    ],
                    "$community": {
                        "_id": {
                            "$oid": "54a38233bf483c6ddfec4b79"
                        },
                        "name": "测试社区",
                        "telephone": "13399999999",
                        "administrators": [
                            {
                                "$oid": "53f722d5bf483c5bd03d0a80"
                            }
                        ]
                    },
                    "$devices": [
                    ],
                    "$groups": [
                        {
                            "_id": {
                                "$oid": "579e0267264251061974b349"
                            },
                            "owner": {
                                "$oid": "53f722d5bf483c5bd03d0a80"
                            },
                            "name": "jia"
                        }
                    ]
                },
                "success": true,
                "obj_name": "person"
            }
        }


# 登出

-   地址: /api/auth/logout
-   方法: GET, POST
-   请求参数: 无
-   响应对象: 无
-   请求范例
    
        curl -v -A CURL -d "" -c cookies.txt http://127.0.0.1:8888/api/auth/logout

-   响应范例

        {
          "success": true
        }


# 电话号码重设口令

-   地址: /api/auth/reset_passwd_by_phone/
-   方法: POST
-   请求参数

    | 名称         | 必须 | 类型         | 说明                           |
    | ------------ | ---- | ------------ | ------------------------------ |
    | phone     |  是  | string       |  手机号              |
    | phone_checksum   |  是  | string       |  短信验证码          |
    | password   |  是  | string       |  新密码          |

-   请求参数: 无
-   响应对象: 无
-   请求范例

        curl -v -A CURL -d "phone=13300000000&phone_checksum=715730&password=111111" http://127.0.0.1:8000/api/auth/reset_passwd_by_phone

-   响应范例

        {
          "success": true
        }


# 忘记口令（废弃）

- 地址: /api/auth/reset
- 方法: POST

__请求参数__

| 名称         | 必须 | 类型         | 说明                           |
| ------------ | ---- | ------------ | ------------------------------ |
| email        |  是  | string       |                                |


# 重设口令（废弃）

如果用户名和邮箱是匹配的，则直接重设口令，并发邮件到邮箱。

- 地址: /api/auth/reset_passwd
- 方法: POST

__请求参数__

| 名称         | 必须 | 类型         | 说明                           |
| ------------ | ---- | ------------ | ------------------------------ |
| username     |  是  | string       |                                |
| email        |  是  | string       |                                |