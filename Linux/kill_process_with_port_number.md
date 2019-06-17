# 프로세스 죽이기

비정상적으로 프로세스가 종료된 경우
'Port **** is already in use'
라고 뜨는 경우가 간혹 있다.

그럴때 그 포트의 프로세스를 죽이는 방법

```
$ lsof -i tcp:8080
COMMAND   PID   USER   FD   TYPE             DEVICE SIZE/OFF NODE NAME
java    93386    amy   50u  IPv6 ******************      0t0  TCP *:http-alt (LISTEN)

$ kill -9 93386

$ lsof -i tcp:8080
(아무것도 안나온다!)
```
