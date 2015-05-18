

## Account

### Account create

method: `POST` url: `/api/sign_up`

```json
{
    email: user_email,
    password: user_password
}
```

```shell
Note: password.length should be in range [6, 20]
```

------------------

Create successfully:

```json
{
    "status":0,
    "status_msg":"ok"
}
```

others error code:

```json
{
    "status": 500,
    "message": "Create account failed: .... "
}
```

### Account login

method: `POST` url: `/api/sign_in`

```json
{
   "email":"user_email",
   "password":"user_password"
}
```

```shell
password.length should be in range [6, 20]
```
---------------

Login successfully:

```json
{
   "status":0,
   "status_msg":"ok",
   "token":"154b4046455a1806425d40161755572b474d131256155440"
}
```

others fail code:

```json
{
  "status": 500,
  "message": "Invalid user or passowrd"
}
```

### Account logout

method: `GET` url: `/api/logout.json`

------------------

```json
{
   "status":0,
   "status_msg":"ok"
}
```



### Reset password

url: `POST: /api/profiles/change_password?token= ...`

params:
old_password:  old password
new_password:  new password

--------------------------

Sucess:

```json
{
   "status":0,
   "status_msg":"ok"
}
```

Other fail code:

```json
{
 "status" : 305,
 "status_msg" : "the member password is wrong!"
}
```

## Photos

### Get photo list

method: `GET` url: `/api/photos`
params: `page`: current_page, `page_size`: page_size default with 12

```json
{
  "page": 1,
  "page_size": 2
}
```

------------------
reponse:

```json
{
   "status":0,
   "status_msg":"ok",
   "page_size":2,
   "total_page":23,
   "current_page":2,
   "items":[
      {
         "photo":{
            "id":3,
            "original":{
               "url":"/uploads/photos/b896a9d0-00ea-4400-8508-3c3aa5c8282d.png",
               "normal":{
                  "url":"/uploads/photos/normal_b896a9d0-00ea-4400-8508-3c3aa5c8282d.png"
               },
               "thumb_s":{
                  "url":"/uploads/photos/thumb_s_b896a9d0-00ea-4400-8508-3c3aa5c8282d.png"
               },
               "thumb_l":{
                  "url":"/uploads/photos/thumb_l_b896a9d0-00ea-4400-8508-3c3aa5c8282d.png"
               },
               "thumb_h":{
                  "url":"/uploads/photos/thumb_h_b896a9d0-00ea-4400-8508-3c3aa5c8282d.png"
               }
            },
            "title":"Untitled Image",
            "make":"",
            "model":"",
            "description":"",
            "status":0,
            "is_public":true,
            "created_at":"2014-09-30T09:25:27.000Z",
            "updated_at":"2014-09-30T09:25:27.000Z",
            "location":"",
            "country":"",
            "province":null,
            "city":null,
            "views_count":6,
            "likes_count":2,
            "comments_count":null,
            "favorites_count":2,
            "tags_count":0,
            "camera":"",
            "equipment":"",
            "tags":[

            ],
            "account":{
               "id":1,
               "member_id":381871,
               "email":"moorekang@gmail.com",
               "first_name":"Yukang",
               "last_name":"Chen",
               "webpage":"www.demo.com",
               "country":"China",
               "state":"Guangdong",
               "city":"Shenzhen",
               "gender":null,
               "last_login_at":null,
               "last_login_ip":null,
               "created_at":"2014-09-30T09:24:46.000Z",
               "updated_at":"2014-10-10T10:39:28.000Z",
               "bio":"Programmer",
               "about":null,
               "reset_password_token":"",
               "stars_count":0,
               "likes_count":16,
               "favorites_count":8,
               "photos_count":43,
               "videos_count":1
            }
         }
      },
      {
         "photo":{
            "id":4,
            "original":{
               "url":"/uploads/photos/068f28c4-4d7d-41b1-a64c-997dbbd26e01.jpg",
               "normal":{
                  "url":"/uploads/photos/normal_068f28c4-4d7d-41b1-a64c-997dbbd26e01.jpg"
               },
               "thumb_s":{
                  "url":"/uploads/photos/thumb_s_068f28c4-4d7d-41b1-a64c-997dbbd26e01.jpg"
               },
               "thumb_l":{
                  "url":"/uploads/photos/thumb_l_068f28c4-4d7d-41b1-a64c-997dbbd26e01.jpg"
               },
               "thumb_h":{
                  "url":"/uploads/photos/thumb_h_068f28c4-4d7d-41b1-a64c-997dbbd26e01.jpg"
               }
            },
            "title":"Untitled Image",
            "make":"",
            "model":"",
            "description":"",
            "status":0,
            "is_public":true,
            "created_at":"2014-09-30T09:25:29.000Z",
            "updated_at":"2014-09-30T09:25:29.000Z",
            "location":"",
            "country":"",
            "province":null,
            "city":null,
            "views_count":5,
            "likes_count":1,
            "comments_count":null,
            "favorites_count":0,
            "tags_count":0,
            "camera":"",
            "equipment":"",
            "tags":[

            ],
            "account":{
               "id":1,
               "member_id":381871,
               "email":"moorekang@gmail.com",
               "first_name":"Yukang",
               "last_name":"Chen",
               "webpage":"www.demo.com",
               "country":"China",
               "state":"Guangdong",
               "city":"Shenzhen",
               "gender":null,
               "last_login_at":null,
               "last_login_ip":null,
               "created_at":"2014-09-30T09:24:46.000Z",
               "updated_at":"2014-10-10T10:39:28.000Z",
               "bio":"Programmer",
               "about":null,
               "reset_password_token":"",
               "stars_count":0,
               "likes_count":16,
               "favorites_count":8,
               "photos_count":43,
               "videos_count":1
            }
         }
      }
   ]
}
```

## 详细查看某一张图

method: 'GET' url: `/api/photos/show/:photo_id`
params: `photo_id`： 图片id

------------------
response:

```json
{
   "status":0,
   "status_msg":"ok",
   "items":[
      {
         "photo":{
            "id":3,
            "original":{
               "url":"/uploads/photos/b896a9d0-00ea-4400-8508-3c3aa5c8282d.png",
               "normal":{
                  "url":"/uploads/photos/normal_b896a9d0-00ea-4400-8508-3c3aa5c8282d.png"
               },
               "thumb_s":{
                  "url":"/uploads/photos/thumb_s_b896a9d0-00ea-4400-8508-3c3aa5c8282d.png"
               },
               "thumb_l":{
                  "url":"/uploads/photos/thumb_l_b896a9d0-00ea-4400-8508-3c3aa5c8282d.png"
               },
               "thumb_h":{
                  "url":"/uploads/photos/thumb_h_b896a9d0-00ea-4400-8508-3c3aa5c8282d.png"
               }
            },
            "title":"Untitled Image",
            "make":"",
            "model":"",
            "description":"",
            "status":0,
            "is_public":true,
            "created_at":"2014-09-30T09:25:27.000Z",
            "updated_at":"2014-09-30T09:25:27.000Z",
            "location":"",
            "country":"",
            "province":null,
            "city":null,
            "views_count":6,
            "likes_count":2,
            "comments_count":null,
            "favorites_count":2,
            "tags_count":0,
            "camera":"",
            "equipment":"",
            "tags":[

            ],
            "account":{
               "id":1,
               "member_id":381871,
               "email":"moorekang@gmail.com",
               "first_name":"Yukang",
               "last_name":"Chen",
               "webpage":"www.demo.com",
               "country":"China",
               "state":"Guangdong",
               "city":"Shenzhen",
               "gender":null,
               "last_login_at":null,
               "last_login_ip":null,
               "created_at":"2014-09-30T09:24:46.000Z",
               "updated_at":"2014-10-10T10:39:28.000Z",
               "bio":"Programmer",
               "about":null,
               "reset_password_token":"",
               "stars_count":0,
               "likes_count":16,
               "favorites_count":8,
               "photos_count":43,
               "videos_count":1
            }
         }
      }
   ]
}
```


## 删除一张图片

method: 'DELETE' url: `/api/photos/:photo_id`
params: `photo_id`： 图片id

------------------
成功：

```json
{
   "status": 0,
   "status_msg": "ok"
}
```

失败：

```json
{
   "status":999,
   "status_msg":"Couldn't find Photo with 'id'=1"
}
```

## Videos

列表，详情，删除类似photos, 把url的photos换成videos。


## Comments

### 评论列表

method: 'GET' url: `/api/photos/:photo_id/comments/`
params: `:photo_id` 为照片id

```json
{
   "page": 1,
   "page_size": 2
}
```

------------

```json
{
   "status":0,
   "status_msg":"ok",
   "current_page":2,
   "page_size":2,
   "total_page":5,
   "total_count":9,
   "items":[
      {
         "id":72,
         "avatar":"http://skypixel.dbeta.me:81/user/381871/avatar/x64",
         "user":"Yukang Chen",
         "user_id":381871,
         "like_count":0,
         "is_current_user_liked":false,
         "created_at":"2014-10-15 16:51:35",
         "content":"hello from api"
      },
      {
         "id":71,
         "avatar":"http://skypixel.dbeta.me:81/user/381871/avatar/x64",
         "user":"Yukang Chen",
         "user_id":381871,
         "like_count":0,
         "is_current_user_liked":false,
         "created_at":"2014-10-15 16:51:27",
         "content":"hello from api"
      }
   ]
}
```

### 增加评论

method: `POST`
url: `/api/photos/:photo_id/comments?token=xxxxxxxxxxxxxxxxxx`

说明: :photo_id 为视频id, 需要为登录状态，所以参数中带上token

params:

```json
{
   "comment[content]":"content message"
}
```

----------

```json
{
   "status":0,
   "status_msg":"ok",
   "items":[
      {
         "id":75,
         "avatar":"http://skypixel.dbeta.me:81/user/381871/avatar/x64",
         "user":"Yukang Chen",
         "user_id":381871,
         "like_count":0,
         "is_current_user_liked":false,
         "created_at":"2014-10-15 17:03:35",
         "content":"hello from api"
      }
   ]
}
```

### 删除评论

method: `DELETE` url: `/api/photos/:photo_id/comments/:comment_id?token=xxxxxxxxxxxxxxx`

说明: :photo_id 为视频id, 需要为登录状态，所以参数中带上token

------------------

```json
{
   "status":0,
   "status_msg":"ok"
}
```

## Likes

### 增加likes
method: `POST` url: `/api/photos/:photo_id/likes/add?token=xxxxxxxxxxxxxxx`

说明： `:photo_id` 为照片id，需要登录状态，所以带上token。

------------


```json
{
   "status":0,
   "status_msg":"ok"
}
```

### 取消likes

method: `DELETE` url: `/api/photos/:photo_id/likes/remove?token=xxxxxxxxxxxxxxx`

说明： `:photo_id` 为照片id，需要登录状态，所以带上token。

--------------
```json
{
   "status":0,
   "status_msg":"ok"
}
```


## Favorites

和likes类似

## Search

method: `GET` url: `/api/search/photos/:tag`

参数: `:tag` 搜索的关键字，更具tag和名字搜索资源

例子: http://skypixel.dbeta.me/api/search/photos?tag=food


## Tags
