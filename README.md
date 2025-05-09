<p align="center">
  <img src="https://readme-typing-svg.herokuapp.com?color=red&center=true&vCenter=true&lines=Welcome+to+FN+PROJECT+[VPN]" alt="FN Project VPN">
</p>

---

<h1 align="center">📡 FN Project VPN</h1>
<p align="center">
  Powerful and secure VPN service with advanced features for all your needs.
</p>

---

## About

This autoscript is a lifetime free autoscript with simple v2ray x noobzvpns multiport all os features.

---

``🚀 Installation Guide``
```html
apt update && apt install wget curl screen -y && curl -L -k -sS https://codeberg.org/Rerechan02/scvps/raw/branch/main/install.sh -o install.sh && chmod +x install.sh && screen -S fn ./install.sh; if [ $? -ne 0 ]; then rm -f install.sh; fi
```

``If it stops in the middle of the process``
```html
screen -r fn
```
---

## 🌐 Port Information
| **Service**            | **Port(s)**           |
|-------------------------|-----------------------|
| **XRAY Vmess TLS**     | 443, 2443                  |
| **XRAY Vmess gRPC**    | 443, 2443                  |
| **XRAY Vmess None TLS**| 80, 2080, 2082                   |
| **XRAY Vless TLS**     | 443, 2443                  |
| **XRAY Vless gRPC**    | 443, 2443                  |
| **XRAY Vless None TLS**| 80, 2080, 2082                   |
| **Trojan gRPC**        | 443, 2443                  |
| **Trojan WS**          | 443, 2443                  |
| **NoobzVPN HTTP**     | 80, 2080, 2082                  |
| **NoobzVPN HTTP(S)**   | 443, 2443                  |
| **UDP Custom**   | 443, 2443, 80, 36712, 1-65535                  |
| **SOCKS5**   | 1080, 443, 2443                |
| **SSH WS TLS**   | 443, 2443                  |
| **SSH WS HTTP**   | 80, 2080, 2082                  |

---

## ALPN
---
| Protocol   | Description                |
|------------|----------------------------|
| HTTP/1.1   | Standard HTTP              |
| h2         | HTTP/2 (Multiplexing)      |
---

## OS Support

- Debian 10 -> 12 [ Tested ]
- Ubuntu 20.04 -> 24.04 [ Tested ]
- Kali Linux Rolling [ Tested ]
- Other? [ Soon ]

Detail: Ubuntu. We have tried testing on all LTS and Non LTS versions with code .04 and .10

---

## REST API

[API](https://app.swaggerhub.com/apis-docs/fnrerechan02/FN-API/1.0.0)

---

## Support

Please join the following Telegram groups and channels to get information about Patches or things related to improving script functions.
- Telegram : [Rerechan02](https://t.me/Rerechan02)
- Telegram Channel : [FN Project](https://t.me/fn_project)
