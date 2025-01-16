# VC6-12
Server Repository

## Setup FlareVM mit dokurr

Im ersten Schritt erstellst du einen Windows 11 Container und ein eigenes Labor Netzwerk.
```yaml
services:
  windows:
    image: "dockurr/windows"
    container_name: "FlareVM"
    environment:
      VERSION: "11"
    devices:
      - "/dev/kvm"
      - "/dev/net/tun"
    volume: 
    cap_add:
      - NET_ADMIN
    ports:
      - 8006:8006
      - 3389:3389/tcp
      - 3389:3389/udp
    stop_grace_period: 2m
```

---
