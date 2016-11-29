# websocketserver

## Deploy to CF
```
cf push websocketserver -b https://github.com/cloudfoundry/go-buildpack.git
```

## Test websocket upgrade
For example, deploy to [bluemix](https://bluemix.net)

*Request*
```sh
time curl -i -N -v -H "Connection: Upgrade" -H "Upgrade: websocket" http://websocketserver.mybluemix.net/echo -H "Sec-WebSocket-Extensions: permessage-deflate" -H "Sec-WebSocket-Key: V7jGVEefI7V8fC+mW8vhFA==" -H "Sec-WebSocket-Version: 13"
```


*Response*
```sh
*   Trying 75.126.81.66...
* Connected to markwebsocketserver.mybluemix.net (75.126.81.66) port 80 (#0)
> GET /echo HTTP/1.1
> Host: markwebsocketserver.mybluemix.net
> User-Agent: curl/7.43.0
> Accept: */*
> Connection: Upgrade
> Upgrade: websocket
> Sec-WebSocket-Extensions: permessage-deflate
> Sec-WebSocket-Key: V7jGVEefI7V8fC+mW8vhFA==
> Sec-WebSocket-Version: 13
>
< HTTP/1.1 101 Switching Protocols
HTTP/1.1 101 Switching Protocols
< Connection: Upgrade
Connection: Upgrade
< Sec-WebSocket-Accept: 1Aa7yjSBqhWheY+ggR6FTK1LQz8=
Sec-WebSocket-Accept: 1Aa7yjSBqhWheY+ggR6FTK1LQz8=
< Date: Tue, 29 Nov 2016 00:03:35 GMT
Date: Tue, 29 Nov 2016 00:03:35 GMT
< X-Global-Transaction-ID: 384839783
X-Global-Transaction-ID: 384839783
< Upgrade: websocket
Upgrade: websocket

^C
curl -i -N -v -H "Connection: Upgrade" -H "Upgrade: websocket"  -H  -H  -H   0.00s user 0.00s system 1% cpu 0.785 total
```
