# OpenResty App SOS

办公网非紧急自动诊断系统

## Depend

* [OpenResty](http://openresty.org/en/installation.html)

## Run

```
git clone https://github.com/Openresty-App/template.git
cd template
./scripts/startup.sh
```

## Test

```lang=shell
[root@localhost template]# curl -i http://127.0.0.1:8080/
HTTP/1.1 200 OK
Server: openresty/1.13.6.1
Date: Fri, 08 Dec 2017 22:23:13 GMT
Content-Type: text/plain
Transfer-Encoding: chunked
Connection: keep-alive

{"message":"Hello, OpenResty"}
```

## Lua

```lang=lua
-- app
local ngx = require "ngx"
local cjson = require "cjson.safe"

local body = {message = "Hello, OpenResty"}
ngx.say(cjson.encode(body))

return ngx.exit(ngx.HTTP_OK)
```
