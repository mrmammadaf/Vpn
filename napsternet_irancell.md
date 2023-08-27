{
 "stats": {},
 "log": {
  "loglevel": "none"
 },
 "policy": {
  "levels": {
   "8": {
    "handshake": 4,
    "connIdle": 300,
    "uplinkOnly": 1,
    "downlinkOnly": 1
   }
  },
  "system": {
   "statsOutboundUplink": true,
   "statsOutboundDownlink": true
  }
 },
 "inbounds": [
  {
   "tag": "socks",
   "port": 10808,
   "protocol": "socks",
   "settings": {
    "auth": "noauth",
    "udp": true,
    "userLevel": 8
   },
   "sniffing": {
    "enabled": true,
    "destOverride": [
     "http",
     "tls"
    ]
   }
  },
  {
   "tag": "http",
   "port": 10809,
   "protocol": "http",
   "settings": {
    "userLevel": 8
   }
  }
 ],
 "outbounds": [
  {
   "tag": "proxy",
   "protocol": "vmess",
   "settings": {
    "vnext": [
     {
      "address": "45.199.138.195",
      "port": 30358,
      "users": [
       {
        "id": "fe5f69e7-e183-439b-950b-9661ef0651f2",
        "alterId": 64,
        "security": "auto",
        "level": 8
       }
      ]
     }
    ]
   },
   "streamSettings": {
    "network": "tcp",
    "security": ""
   },
   "mux": {
    "enabled": false
   }
  },
  {
   "tag": "direct",
   "protocol": "freedom",
   "settings": {}
  },
  {
   "tag": "block",
   "protocol": "blackhole",
   "settings": {
    "response": {
     "type": "http"
    }
   }
  }
 ],
 "dns": {
  "servers": [
   "8.8.8.8"
  ]
 },
 "routing": {
  "domainStrategy": "Asls",
  "rules": []
 }
}![IMG_20230823_171408_725](https://github.com/mrmammadaf/Vpn/assets/143089942/b0c38326-e252-4cfd-8f49-f1283fe5beac)
