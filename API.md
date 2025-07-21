# 📖 Project Rerechan - API Documentation

API ini disediakan oleh **FN Project** untuk mengelola akun VPN berbasis SSH, Vmess, Vless, Trojan, dan NoobzVPN secara otomatis melalui endpoint API. Setiap endpoint menerima `POST` request dengan format `JSON` dan menggunakan autentikasi token Bearer.

---

## 📌 Daftar Endpoint

### 🔐 Autentikasi
Semua request harus menyertakan header berikut:

```http
Authorization: Bearer your_api_token
Content-Type: application/json
```

---

🔧 1. Add SSH Account

Endpoint: /api/addssh

Request Body
```json
{
  "username": "username",
  "password": "password",
  "masa": 30
}
```

Contoh Response Sukses
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
    "ws_http": "80, 2082, 8080",
    "ws_tls": "443",
    "socks5": "443, 1080",
    "udp_custom": "1-65535 & 36712",
    "badvpn": "7300"
  },
    "slowdns": {
          "dns": "1.1.1.1, 8.8.8.8",
          "nameserver": "dns.rerechan.com",
          "publik_key": "5bb04eb5c1d8e8ced2feefd2a3b7e4d57cf648dce0d5a225ac62197729336f50"    
    },
  "config": "domain.com:1-65535@username:password",
  "payload": "GET /ssh HTTP/1.1[crlf]Host: domain.com[crlf]Upgrade: websocket[crlf][crlf]"
}
```

---

🔧 2. Add VMess Account

Endpoint: /api/add-vmess

Request Body
```json
{
  "user": "username",
  "masaaktif": 30
}
```

Response Sukses

```json
{
  "status": "true",
  "code": 200,
  "message": "Akun VMess berhasil dibuat",
  "user": "username",
  "domain": "domain.com",
  "uuid": "796e70a1-fdf8-4695-9916-d37d1084c791",
  "http": "80, 2082, 8080",
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

---

🔧 3. Add VLESS Account

Endpoint: /api/add-vless

Request Body
```json
{
  "user": "username",
  "masaaktif": 30
}
```

Response Sukses

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
    "path": "/multipath, /vless",
    "service_name": "vless-grpc",
    "links": {
        "tls": "vless://5e97b922-23e6-11f0-816d-0fa6bba70b3f@domain.com:443?path=/vless&security=tls&encryption=none&type=ws#username",
        "ntls": "vless://5e97b922-23e6-11f0-816d-0fa6bba70b3f@domain.com:80?path=/vless&encryption=none&type=ws#username",
        "grpc": "vless://5e97b922-23e6-11f0-816d-0fa6bba70b3f@domain.com:443?mode=gun&security=tls&encryption=none&type=grpc&serviceName=vless-grpc&sni=domain.com#username"
    },
    "expiration_date": "2025-05-28"
}
```


---

🔧 4. Add Trojan Account

Endpoint: /api/add-trojan

Request Body
```json
{
  "user": "username",
  "masaaktif": 30
}
```

Response Sukses

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


---

🔧 5. Add NoobzVPN

Endpoint: /api/add-noobz

Request Body
```json
{
  "user": "username",
  "device": 3,
  "bw": 100,
  "masaaktif": 30
}
```

Response Sukses
```json
{
  "status": "true",
  "code": 200,
  "message": "Akun NoobzVPN berhasil dibuat",
  "user": "username@fn-project",
  "domain": "domain.com",
  "password": "fn-project.com",
  "limit_device": "3",
  "limit_bandwidth": "100 GB",
  "http_ports": "80, 2082, 8080",
  "https_ports": "443",
  "payload": "GET / HTTP/1.1[crlf]Host: [host][crlf]Upgrade: websocket[crlf][crlf]",
  "expiration_date": "2025-05-28"
}
```


---

🔄 Endpoint Renew

♻️ 6. Renew VMess

Endpoint: /api/renew-vmess

Request
```json
{
  "username": "username",
  "days": 30
}
```

Response
```json
{
  "message": "V2ray account successfully extended",
  "username": "username",
  "expires_on": "2025-08-07"
}
```


---

♻️ 7. Renew VLESS

Endpoint: /api/renew-vless

Request
```json
{
  "username": "username",
  "days": 30
}
```

Response
```json
{
  "message": "VLESS account successfully extended",
  "username": "username",
  "expires_on": "2025-08-07"
}
```


---

♻️ 8. Renew Trojan

Endpoint: /api/renew-trojan

Request
```json
{
  "username": "username",
  "days": 30
}
```

Response
```json
{
  "message": "Trojan account successfully extended",
  "username": "username",
  "expires_on": "2025-08-07"
}
```


---

♻️ 9. Renew NoobzVPN
# Note:
`noobz only auto extend 30 days`

Endpoint: /api/renew-noobz

Request
```json
{
  "username": "username"
}
```

Response
```json
{
  "status": "true",
  "code": 200,
  "message": "NoobzVPN account successfully renewed",
  "username": "username",
  "expires_on": "2025-08-07 00:00:00"
}
```


---

♻️ 10. Renew SSH

Endpoint: /api/renew-ssh

Request
```json
{
  "username": "username",
  "days": 30
}
```

Response
```json
{
  "message": "User expiration updated successfully",
  "username": "username",
  "expires_on": "2025-08-07"
}
```


---

🔧 11. Add ShadowSocks Account

Endpoint: /api/add-ss

Request Body
```json
{
  "user": "username",
  "masaaktif": 30
}
```

Response Sukses

```json
{
  "status": "true",
  "code": 200,
  "message": "ShadowSocks account created successfully",
  "user": "username",
  "uuid": "180a5b70-9135-441a-bf3b-acfd1d886dba",
  "domain": "us.nfime.biz.id",
  "tls_port": "443",
  "ntls_port": "80, 2082",
  "path": "/ss-ws",
  "cipher": "chacha20-ietf-poly1305",
  "service_name": "ss-grpc",
  "expires_on": "2025-08-07",
  "links": {
    "tls": "ss://Y2hhY2hhMjAtaWV0Zi1wb2x5MTMwNToxODBhNWI3MC05MTM1LTQ0MWEtYmYzYi1hY2ZkMWQ4ODZkYmE=@us.nfime.biz.id:443?path=/ss-ws&security=tls&host=us.nfime.biz.id&type=ws&sni=us.nfime.biz.id#username",
    "ntls": "ss://Y2hhY2hhMjAtaWV0Zi1wb2x5MTMwNToxODBhNWI3MC05MTM1LTQ0MWEtYmYzYi1hY2ZkMWQ4ODZkYmE=@us.nfime.biz.id:80?path=/ss-ws&security=none&host=us.nfime.biz.id&type=ws#username",
    "grpc": "ss://Y2hhY2hhMjAtaWV0Zi1wb2x5MTMwNToxODBhNWI3MC05MTM1LTQ0MWEtYmYzYi1hY2ZkMWQ4ODZkYmE=@us.nfime.biz.id:443?security=tls&encryption=none&type=grpc&serviceName=shadow-grpc&sni=us.nfime.biz.id#username"
  }
}
```

---

🔧 4. Add Trojan Account

Endpoint: /api/add-s5

Request Body
```json
{
  "username": "username",
  "password": "password",
  "masaaktif": 30
}
```

Response Sukses

```json
{
 "status": "true",
 "code": 200,
 "message": "Akun SOCKS5 berhasil dibuat",
  "user": "username",
  "domain": "us.nfime.biz.id",
  "http": "80, 2082, 8080",
  "https": "443",
  "grpc": "443",
  "expiration_date": "2025-08-07",
  "path": "/socks",
  "service_name": "socks-grpc",
  "links": {
    "tls": "socks://dXNlcm5hbWU6cGFzc3dvcmQ=@us.nfime.biz.id:443?path=/socks&security=tls&host=us.nfime.biz.id&type=ws&sni=us.nfime.biz.id#username",
    "ntls": "socks://dXNlcm5hbWU6cGFzc3dvcmQ=@us.nfime.biz.id:80?path=/socks&security=none&host=us.nfime.biz.id&type=ws#username",
    "grpc": "socks://dXNlcm5hbWU6cGFzc3dvcmQ=@us.nfime.biz.id:443?security=tls&encryption=none&type=grpc&serviceName=socks-grpc&sni=us.nfime.biz.id#username"
  }
 }
```

---

♻️ 13. Renew ShadowSocks

Endpoint: /api/renew-ss

Request
```json
{
  "username": "username",
  "days": 30
}
```

Response
```json
{
  "message": "ShadowSocks account successfully extended",
  "username": "username",
  "expires_on": "2025-08-07"
}
```

---

♻️ 14. Renew Socks

Endpoint: /api/renew-s5

Request
```json
{
  "username": "username",
  "days": 30
}
```

Response
```json
{
  "message": "Socks5 account successfully extended",
  "username": "username",
  "expires_on": "2025-08-07"
}
```

---


❌ Response Gagal (Umum)
```json
{
  "status": "false",
  "code": 400,
  "message": "Username is required"
}
```
```json
{
  "status": "false",
  "code": 404,
  "message": "Username not found"
}
```
```json
{
  "status": "false",
  "code": 500,
  "message": "Failed to renew account"
}
```


---

📣 Author & License

Author: Rerechan02 (DindaPutriFN)

Project: Project Rerechan

License: Personal/Internal use only.