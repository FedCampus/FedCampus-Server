# Servers Access

## Suffix of all domains are **.dukekunshan.edu.cn**

* [fed-port](../fed-port.dukekunshan.edu.cn) (SSH not enabled)
* [fed-ml](../fed-ml.dukekunshan.edu.cn)
* [fed-iot](../fed-iot.dukekunshan.edu.cn)

### Hardware

CPU: 128 AMD EPYC 7763 64-Core Processor

GPU: 1 x \[GeForce RTX 3090]&#x20;

```
> lsblk
NAME   MAJ:MIN RM   SIZE RO TYPE MOUNTPOINT
sda      8:0    0   200G  0 disk 
|-sda1   8:1    0   1.9G  0 part /boot
`-sda2   8:2    0 198.1G  0 part /
sr0     11:0    1  1024M  0 rom  
```

### Access VM via SSH

Note:  with Tailscale support

Append your Publickey in [this](../../publickey/key.md) file.

* Login username is shared as the ssh session will only really be used as last debug procedure.
* [Hostname](./)
* Username: **userroot**
* No password is used, use your supplied key to login
* sudo password is available [here](https://github.com/FedCampus/Credentials)

***

## IP: 10.201.8.175

### Hardware

CPU: 128 Intel(R) Xeon(R) Platinum 8352Y CPU @ 2.20GHz

GPU: 2 x \[GeForce RTX 3090]

```
> lsblk
sda      8:0    0  4.4T  0 disk 
├─sda1   8:1    0    1G  0 part /boot/efi
└─sda2   8:2    0  4.4T  0 part /
sr0     11:0    1 1024M  0 rom  
```

### Access VM via SSH

Note: <mark style="color:red;">**DKU VPN is required**</mark>

```
# Initial Login
> ssh [github_name]@10.201.8.175
> current_password: [github_name]
> new_password: [your_new_password]
```



