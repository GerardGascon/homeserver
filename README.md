# Home Server

This is my home server setup. 

I also consider a VPS part of my home server as it serves an essential role for remote access.

---

## Servers

### Kamaji

> The big server that does most of the tasks.

| TrueNAS home server             |
|---------------------------------|
| TrueNAS Scale Community Edition |
| 64GB RAM                        |
| 256GB NVMe (OS)                 |
| 1 TB NVMe                       |
| 4x 512 GB HDD (stripped mirror) |
| 3x 6TB HDD (RAID-Z1)            |
| Ryzen 5 5500                    |
| RTX 3050 (8GB)                  |

All of these Docker apps are created using the TrueNAS UI but including the original file:

```
include:
  - path: /mnt/NVMe/apps/<<service-directory>>/compose.yaml
services: {}
```

### Sakamoto

> The tiny server that sits around doing almost nothing but it's useful when it needs to.

| Raspberry Pi CM5 |
|------------------|
| Raspberry Pi OS  |
| 4GB RAM          |
| 32GB eMMC        |

This Pi mainly acts as a backup. But it also gives me the ability to remotely use Wake-on-LAN to power up my NAS.

### Rosso

> The server on the cloud that locates everyone else.

| Hetzner CPX22 |
|---------------|
| Ubuntu Server |
| 2 vCPUs       |
| 4 GB RAM      |
| 80 GB         |

This VPS mainly acts as a gateway to my home server. It has Nginx and WireGuard to create a tunnel to my services
without using Port Forwarding.
