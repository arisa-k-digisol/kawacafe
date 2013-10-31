API ~Practice2~
============
---------------------


##リクエストユーザーの情報取得
```
GET /api/v1/user
```

認証: 必須

###input

なし

###response

```json
{"name": "Hiroshige Umino",
 "url_name": "yaotti",
 "profile_image_url": "https://si0.twimg.com/profile_images/2309761038/1ijg13pfs0dg84sk2y0h_normal.jpeg",
 "url": "http://qiita.com/users/yaotti",
 "description": "Qiita(Ruby on Rails)やKobito(Macアプリ)の開発をしています．",
 "website_url": "http://yaotti.hatenablog.com",
 "organization": "Increments Inc",
 "location": "Tokyo, Japan",
 "facebook": "yaotti",
 "linkedin": "yaotti",
 "twitter": "yaotti",
 "github": "yaotti",
 "followers": 181,
 "following_users": 118,
 "items": 101,
 "teams": [{"name":"インクリメンツ", "url_name": "increments"}]
}
```

##特定ユーザーの情報取得
```
GET /api/v1/users/:url_name
```
認証: 任意

###input

なし

###response

```json
{"name": "Hiroshige Umino",
 "url_name": "yaotti",
 "profile_image_url": "https://si0.twimg.com/profile_images/2309761038/1ijg13pfs0dg84sk2y0h_normal.jpeg",
 "url": "http://qiita.com/users/yaotti",
 "description": "Qiita(Ruby on Rails)やKobito(Macアプリ)の開発をしています．",
 "website_url": "http://yaotti.hatenablog.com",
 "organization": "Increments Inc",
 "location": "Tokyo, Japan",
 "facebook": "yaotti",
 "linkedin": "yaotti",
 "twitter": "yaotti",
 "github": "yaotti",
 "followers": 181,
 "following_users": 118,
 "items": 101
}
```

##特定ユーザーの投稿取得
```
GET /api/v1/users/:url_name/items
```
認証: 任意

###input

+ team_url_name (任意) String
    + チームのサブドメイン部分 (https://○○○.qiita.com の"○○○")

###response

```json
[{"id": 1,
 "uuid": "1a43e55e7209c8f3c565",
 "user":
  {"name": "Hiroshige Umino",
   "url_name": "yaotti",
   "profile_image_url": "https://si0.twimg.com/profile_images/2309761038/1ijg13pfs0dg84sk2y0h_normal" },
 "title": "てすと",
 "body": "<p>foooooooooooooooo</p>\n",
 "created_at": "2012-10-03 22:12:36 +0900",
 "updated_at": "2012-10-03 22:12:36 +0900",
 "created_at_in_words": "18 hours ago",
 "updated_at_in_words": "18 hours ago",
 "tags":
  [{"name": "FOOBAR",
    "url_name": "FOOBAR",
    "icon_url": "http://qiita.com/icons/thumb/missing.png",
    "versions": ['1.2', '1.3']}],
 "stock_count": 0,
 "stock_users": [],
 "comment_count": 0,
 "url": "http://qiita.com/items/1a43e55e7209c8f3c565",
 "gist_url": null,
 "tweet": false,
 "private": false,
 "stocked": false
},
 ...
]
```
