# Rest API For This Script

• Enable Api
- menu number 11
- generate token api
- restart service api
- success on service api

- Addssh
```shell
curl -X POST https://your-api-endpoint.com/addssh \
    -H "Authorization: Bearer your_bearer_token" \
    -H "Content-Type: application/json" \
    -d '{
        "username": "username_ssh",
        "password": "your_password",
        "masa": 30
    }'
```

- Add Vmess
```shell
curl -X POST https://your-api-endpoint.com/api/add-vmess \
    -H "Authorization: Bearer your_bearer_token" \
    -H "Content-Type: application/json" \
    -d '{
        "user": "username_vmess",
        "masaaktif": 30
    }'
```

- Add Vless
```shell
curl -X POST https://your-api-endpoint.com/api/add-vless \
    -H "Authorization: Bearer your_bearer_token" \
    -H "Content-Type: application/json" \
    -d '{
        "user": "username_vless",
        "masaaktif": 30
    }'
```

- Add Trojan
```shell
curl -X POST https://your-api-endpoint.com/api/add-trojan \
    -H "Authorization: Bearer your_bearer_token" \
    -H "Content-Type: application/json" \
    -d '{
        "user": "username_trojan",
        "masaaktif": 30
    }'
```

- Add Noobz
```shell
curl -X POST https://your-api-endpoint.com/api/add-noobz \
    -H "Authorization: Bearer your_bearer_token" \
    -H "Content-Type: application/json" \
    -d '{
        "user": "username_noobz",
        "device": 3,
        "bw": 10,
        "masaaktif": 30
    }'
```

Output:
```success
"code": "200"
```
or
```failed
"code": "error code | 404, 400, 502, 501 etc.."
```