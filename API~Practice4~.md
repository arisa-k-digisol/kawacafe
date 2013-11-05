API~Practice4~
-------------------
##Schema

All API access is over HTTPS, and accessed from the api.github.com domain (or through yourdomain.com/api/v3/ for enterprise). All data is sent and received as JSON.

```
$ curl -i https://api.github.com/users/octocat/orgs

HTTP/1.1 200 OK
Server: nginx
Date: Fri, 12 Oct 2012 23:33:14 GMT
Content-Type: application/json; charset=utf-8
Connection: keep-alive
Status: 200 OK
ETag: "a00049ba79152d03380c34652f2cb612"
X-GitHub-Media-Type: github.beta
X-RateLimit-Limit: 5000
X-RateLimit-Remaining: 4987
X-RateLimit-Reset: 1350085394
Content-Length: 5
Cache-Control: max-age=0, private, must-revalidate
X-Content-Type-Options: nosniff

[]
```
Blank fields are included as null instead of being omitted.

All timestamps are returned in ISO 8601 format:

```
YYYY-MM-DDTHH:MM:SSZ
```