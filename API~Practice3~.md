API~Practice3~
----------------------


##List gists

List a user’s gists:

```
GET /users/:user/gists
```
List the authenticated user’s gists or if called anonymously, this will return all public gists:

```
GET /gists
```
List all public gists:

```
GET /gists/public
```
List the authenticated user’s starred gists:

```
GET /gists/starred
```

##Parameters

#####since
>>Optional string of a timestamp in ISO 8601 format: YYYY-MM-DDTHH:MM:SSZ Only gists updated at or after this time are returned.

##Response

 
```
Status: 200 OK
Link: <https://api.github.com/resource?page=2>; rel="next",
<https://api.github.com/resource?page=5>; rel="last"
X-RateLimit-Limit: 5000
X-RateLimit-Remaining: 4999
```
```
[
  {
    "url": "https://api.github.com/gists/ab3c421672736a57a7dd",
    "id": "1",
    "description": "description of gist",
    "public": true,
    "user": {
      "login": "octocat",
      "id": 1,
      "avatar_url": "https://github.com/images/error/octocat_happy.gif",
      "gravatar_id": "somehexcode",
      "url": "https://api.github.com/users/octocat"
    },
    "files": {
      "ring.erl": {
        "size": 932,
        "filename": "ring.erl",
        "raw_url": "https://gist.github.com/raw/365370/8c4d2d43d178df44f4c03a7f2ac0ff512853564e/ring.erl"
      }
    },
    "comments": 0,
    "comments_url": "https://api.github.com/gists/92b608b7a85ab46f4d04/comments/",
    "html_url": "https://gist.github.com/1",
    "git_pull_url": "git://gist.github.com/1.git",
    "git_push_url": "git@gist.github.com:1.git",
    "created_at": "2010-04-14T02:15:15Z"
  }
]
```

###Get a single gist
```
GET /gists/:id
```
Note: When using the v3 media type the “user” field will become “owner”

#####Response

```
Status: 200 OK
X-RateLimit-Limit: 5000
X-RateLimit-Remaining: 4999
```
```
{
  "url": "https://api.github.com/gists/ab3c421672736a57a7dd",
  "id": "1",
  "description": "description of gist",
  "public": true,
  "user": {
    "login": "octocat",
    "id": 1,
    "avatar_url": "https://github.com/images/error/octocat_happy.gif",
    "gravatar_id": "somehexcode",
    "url": "https://api.github.com/users/octocat"
  },
  "files": {
    "ring.erl": {
      "size": 932,
      "filename": "ring.erl",
      "raw_url": "https://gist.github.com/raw/365370/8c4d2d43d178df44f4c03a7f2ac0ff512853564e/ring.erl"
    }
  },
  "comments": 0,
  "comments_url": "https://api.github.com/gists/92b608b7a85ab46f4d04/comments/",
  "html_url": "https://gist.github.com/1",
  "git_pull_url": "git://gist.github.com/1.git",
  "git_push_url": "git@gist.github.com:1.git",
  "created_at": "2010-04-14T02:15:15Z",
  "forks": [
    {
      "user": {
        "login": "octocat",
        "id": 1,
        "avatar_url": "https://github.com/images/error/octocat_happy.gif",
        "gravatar_id": "somehexcode",
        "url": "https://api.github.com/users/octocat"
      },
      "url": "https://api.github.com/gists/d3e9e4e520509c7d220d",
      "created_at": "2011-04-14T16:00:49Z"
    }
  ],
  "history": [
    {
      "url": "https://api.github.com/gists/c8278c3966dadba232ea",
      "version": "57a7f021a713b1c5a6a199b54cc514735d2d462f",
      "user": {
        "login": "octocat",
        "id": 1,
        "avatar_url": "https://github.com/images/error/octocat_happy.gif",
        "gravatar_id": "somehexcode",
        "url": "https://api.github.com/users/octocat"
      },
      "change_status": {
        "deletions": 0,
        "additions": 180,
        "total": 180
      },
      "committed_at": "2010-04-14T02:15:15Z"
    }
  ]
}
```