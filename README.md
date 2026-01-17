# Home Server

This is my home server setup (I also consider my VPS part of my home server).

---

## Elements

### NAS

| TrueNAS home server             |
|---------------------------------|
| TrueNAS Scale Community Edition |
| 64GB RAM                        |
| 256GB NVMe (OS)                 |
| 1 TB NVMe                       |
| Ryzen 5 5500                    |
| RTX 3050 (8GB)                  |

All of these Docker apps are created using the TrueNAS UI but including the original file:

```
include:
  - path: /mnt/NVMe/apps/<<service-directory>>/compose.yaml
services: {}
```

### Raspberry Pi

| Raspberry Pi CM5 |
|------------------|
| Raspberry Pi OS  |
| 4GB RAM          |
| 32GB eMMC        |

This Pi mainly acts as a backup. But it also gives me the ability to remotely use Wake-on-LAN to power up my NAS.

### VPS


| DigitalOcean Droplet |
|----------------------|
| Ubuntu Server        |
| 1 vCPU               |
| 512MB RAM            |
| 10 GiB               |

This VPS mainly acts as a gateway to my home server. It has Nginx Proxy Manager and WireGuard to create a tunnel to my
services without using Port Forwarding.
