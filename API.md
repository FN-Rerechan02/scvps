# Rest API For This Script

• Enable Api
- menu number 11
- generate token api
- restart service api
- success on service api

- addssh
```shell
curl -X POST https://your-api-endpoint.com/api/addssh \
    -H "Authorization: Bearer your_bearer_token" \
    -H "Content-Type: application/json" \
    -d '{
        "username": "username",
        "password": "password",
        "masa": 30
    }'
```

- add-vmess
```shell
 curl -X POST https://domain.com/api/add-vmess \
    -H "Authorization: Bearer 1caa6f42-c904-96bc-eaf2-683d5d67487b" \
    -H "Content-Type: application/json" \
    -d '{
        "user": "username",
        "masaaktif": 30
    }'
```

- add-vless
```shell
curl -X POST https://your-api-endpoint.com/api/add-vless \
    -H "Authorization: Bearer your_bearer_token" \
    -H "Content-Type: application/json" \
    -d '{
        "user": "username",
        "masaaktif": 30
    }'
```

- add-trojan
```shell
curl -X POST https://your-api-endpoint.com/api/add-trojan \
    -H "Authorization: Bearer your_bearer_token" \
    -H "Content-Type: application/json" \
    -d '{
        "user": "username",
        "masaaktif": 30
    }'
```

- add-noobz
```shell
curl -X POST https://your-api-endpoint.com/api/add-noobz \
    -H "Authorization: Bearer your_bearer_token" \
    -H "Content-Type: application/json" \
    -d '{
        "user": "username",
        "device": 3,
        "bw": 10,
        "masaaktif": 30
    }'
```

## Output True
Output True addsssh:
```json
{
    "status": "true",
    "code": 200,
    "message": "Akun SSH berhasil dibuat",
    "username": "username",
    "password": "password",
    "domain": "domain.com",
    "ip": "202.152.240.50",
    "expired_on": "2025-05-28",
    "ports": {
        "ssh": "443",
        "ws_http": "80, 2082",
        "ws_tls": "443",
        "socks5": "443, 1080",
        "udp_custom": "1-65535 & 36712",
        "badvpn": "7300"
    },
    "config": "domain.com:1-65535@username:password",
    "payload": "GET /ssh HTTP/1.1[crlf]Host: domain.com[crlf]Upgrade: websocket[crlf][crlf]"
}
```

Output True add-vmess:
```json
{
  "status": "true",
  "code": 200,
  "message": "Akun VMess berhasil dibuat",
  "user": "username",
  "domain": "domain.com",
  "uuid": "796e70a1-fdf8-4695-9916-d37d1084c791",
  "http": "80, 2082",
  "https": "443",
  "grpc": "443",
  "expiration_date": "2025-05-28",
  "path": "/whatever",
  "service_name": "vmess-grpc",
  "links": {
    "tls": "vmess://eyAidiI6ICIyIiwgInBzIjogInVzZXJuYW1lIiwgImFkZCI6ICJmYXJlbGx2cG4ucHl0aG9uMy5iaXouaWQiLCAicG9ydCI6ICI0NDMiLCAiaWQiOiAiNzk2ZTcwYTEtZmRmOC00Njk1LTk5MTYtZDM3ZDEwODRjNzkxIiwgImFpZCI6ICIwIiwgIm5ldCI6ICJ3cyIsICJwYXRoIjogIi92bWVzcyIsICJ0eXBlIjogIm5vbmUiLCAiaG9zdCI6ICJmYXJlbGx2cG4ucHl0aG9uMy5iaXouaWQiLCAidGxzIjogInRscyIgfQo=",
    "ntls": "vmess://eyAidiI6ICIyIiwgInBzIjogInVzZXJuYW1lIiwgImFkZCI6ICJmYXJlbGx2cG4ucHl0aG9uMy5iaXouaWQiLCAicG9ydCI6ICI4MCIsICJpZCI6ICI3OTZlNzBhMS1mZGY4LTQ2OTUtOTkxNi1kMzdkMTA4NGM3OTEiLCAiYWlkIjogIjAiLCAibmV0IjogIndzIiwgInBhdGgiOiAiL3ZtZXNzIiwgInR5cGUiOiAibm9uZSIsICJob3N0IjogImZhcmVsbHZwbi5weXRob24zLmJpei5pZCIsICJ0bHMiOiAibm9uZSIgfQo=",
    "grpc": "vmess://eyAidiI6ICIyIiwgInBzIjogInVzZXJuYW1lIiwgImFkZCI6ICJmYXJlbGx2cG4ucHl0aG9uMy5iaXouaWQiLCAicG9ydCI6ICI0NDMiLCAiaWQiOiAiNzk2ZTcwYTEtZmRmOC00Njk1LTk5MTYtZDM3ZDEwODRjNzkxIiwgImFpZCI6ICIwIiwgIm5ldCI6ICJncnBjIiwgInBhdGgiOiAidm1lc3MtZ3JwYyIsICJ0eXBlIjogIm5vbmUiLCAiaG9zdCI6ICJmYXJlbGx2cG4ucHl0aG9uMy5iaXouaWQiLCAidGxzIjogInRscyIgfQo="
  }
}
```

Output True add-vless:
```json
{
    "status": "true",
    "code": 200,
    "message": "Akun VLESS berhasil dibuat",
    "user": "username",
    "domain": "domain.com",
    "uuid": "5e97b922-23e6-11f0-816d-0fa6bba70b3f",
    "tls_port": "443",
    "ntls_ports": "80, 2082",
    "path": "/vless",
    "service_name": "vless-grpc",
    "links": {
        "tls": "vless://5e97b922-23e6-11f0-816d-0fa6bba70b3f@domain.com:443?path=/vless&security=tls&encryption=none&type=ws#username",
        "ntls": "vless://5e97b922-23e6-11f0-816d-0fa6bba70b3f@domain.com:80?path=/vless&encryption=none&type=ws#username",
        "grpc": "vless://5e97b922-23e6-11f0-816d-0fa6bba70b3f@domain.com:443?mode=gun&security=tls&encryption=none&type=grpc&serviceName=vless-grpc&sni=domain.com#username"
    },
    "expiration_date": "2025-05-28"
}
```

Output True add-trojan:
```json
{
  "status": "true",
  "code": 200,
  "message": "Akun Trojan berhasil dibuat",
  "user": "username",
  "domain": "domain.com",
  "password": "d911b29e-c47f-4bb7-bb2a-2c675b7a1adc",
  "https": "443",
  "grpc": "443",
  "path": "/trojan-ws",
  "service_name": "trojan-grpc",
  "links": {
    "ws": "trojan://d911b29e-c47f-4bb7-bb2a-2c675b7a1adc@domain.com:443?path=%2Ftrojan-ws&security=tls&host=domain.com&type=ws&sni=domain.com#username",
    "grpc": "trojan://d911b29e-c47f-4bb7-bb2a-2c675b7a1adc@domain.com:443?mode=gun&security=tls&type=grpc&serviceName=trojan-grpc&sni=domain.com#username"
  },
  "expiration_date": "2025-05-28"
}
```

Output True add-noobz
```json
{
    "status": "true",
    "code": 200,
    "message": "Akun NoobzVPN berhasil dibuat",
    "user": "username@fn-project",
    "domain": "domain.com",
    "password": "fn-project.com",
    "limit_device": "3",
    "limit_bandwidth": "10 GB",
    "http_ports": "80, 2082",
    "https_ports": "443",
    "payload": "GET / HTTP/1.1[crlf]Host: [host][crlf]Upgrade: websocket[crlf][crlf]",
    "expiration_date": "2025-05-28"
}
```

## Output False
Output False:
```json
{
  "status": "false",
  "code": 400,
  "message": "Username 'Rerechan02' is already in use"
}
```

Output False2:
```shell
502 Bad Gateway
```