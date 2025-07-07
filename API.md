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
    "ws_http": "80, 2082",
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
Berisi link Vmess (TLS, Non-TLS, GRPC) lengkap dengan UUID dan konfigurasi.
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
Berisi link VLESS (TLS, Non-TLS, GRPC) dengan UUID dan konfigurasi.
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
Berisi konfigurasi Trojan (WS, GRPC) dan tanggal expired.
```


---

🔧 5. Add NoobzVPN

Endpoint: /api/add-noobz

Request Body
```json
{
  "user": "username",
  "device": 3,
  "bw": 10,
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
  "limit_bandwidth": "10 GB",
  "http_ports": "80, 2082",
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