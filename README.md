# A Complete Guide - Run Atlas Network Node as Provider

What is Atlas? Atlas Network is a permissionless, decentralized node orchestration layer for blockchains, apps, and protocols. At this like DePin orchestration layer.

## Here We Go...GAS 

**`Is there incentivized?` ![Confirm](https://img.shields.io/badge/confirm-yes-brightgreen)**

> [!IMPORTANT]
> **FAQs**: Atlas Network is thrilled to announce the launch of its **Incentivized Testnet** a major milestone in our journey to reshape DePIN orchestration. Wave Two Points Program is here as **Early Access**, **Impact: Contribute**, and **Rewards Galore: Earn NPs (NODE POINTs)**. Each participant will find step-by-step guides in the Marketplace to help them get started and make the most of their contributions see here to all [FAQs](https://docs.atlasnetwork.dev/docs/Navigate%20Quests/FAQ) or on [Twitter](https://x.com/BuildOnAtlas/status/1869028708704456818)

---

## 1. Preparation/Prerequisites - Run Atlas Network Node
**1. Hardware Requirements**

> [!CAUTION]
> `Machine is very sensitive compiling services tools, In order to run Atlas node, its need a server recommended specs`

| Requirement                      | Details                                   |
|----------------------------------|-------------------------------------------|
| Services                         | Full root, firewall allow all ports        |
| RAM/Memory                       | 4 GB - Up                                    |
| CPU/vCPU                         | 2 Cores - Up                                |
| Storage Space                    | 80 GB - Up                                   |
| Supported OS Linux               | Ubuntu >22.04 Up & Debian >12 Up          |
| Internet service                 | 1Gbps unlimited network bandwidth         |
| Drivers                          | Kernel >6.1-Latest, incl-latest security     |




sign up now https://testnet.atlasnetwork.xyz/refer/1cGToWb
search your machines node with id or paste any address wallet : https://explorer.atlasnetwork.xyz/machine

> [!TIP]
> Do this before you start. If you can't see any **failed pending, or stuck** provider machine setup, run this.

```
sudo apt update && sudo apt upgrade -y && \
sudo apt-get install --install-recommends linux-generic-hwe-22.04 -y && \
sudo apt autoremove --purge -y && \
sudo apt-get install iptables iptables-persistent -y && \
sudo reboot
```
> check up to date of kernel
```diff
- sudo uname -r
> output version: >6.xxxx or 6.8.0-50-generic
```

> and then, temporary (1) disable --> (2) enable, after active machines run
```
sudo ufw disable
```

```
sudo ufw enable
```

delete and update service of atlasnetwork-provider.service

```bash
sudo systemctl stop atlasnetwork-provider.service && \
sudo systemctl disable atlasnetwork-provider.service && \
sudo rm /etc/systemd/system/atlasnetwork-provider.service && \
sudo systemctl daemon-reload && \
sudo rm /usr/local/bin/atlasnetwork-provider && \
sudo rm -rf /etc/atlasnetwork /var/lib/atlasnetwork && \
sudo systemctl reset-failed
```

Usefull CMD Logs

- sudo journalctl -u atlasnetwork-provider.service
- sudo systemctl status atlasnetwork-provider.service


![Atlas-Provider-dashboard-12-21-2024_02_41_AM](https://github.com/user-attachments/assets/84d49746-4c3a-48c1-92ca-d63ca5aa50f1)

![Atlas-Provider-dashboard-12-21-2024_02_40_AM](https://github.com/user-attachments/assets/1dfbd971-86f8-4846-9d04-79ce171b6c70)

![Atlas-Provider-dashboard-12-21-2024_02_43_AM](https://github.com/user-attachments/assets/679480f9-df38-4823-a8d9-911d064e0ed0)

![Atlas-Provider-dashboard-12-21-2024_02_39_AM](https://github.com/user-attachments/assets/38972847-fe48-4bb0-a149-a3d5bf08cf47)

![Atlas-Provider-dashboard-12-21-2024_01_41_AM](https://github.com/user-attachments/assets/d37e41b4-10d0-4114-9806-fec015614cc9)

![Desktop-screenshot-12-21-2024_02_33_AM](https://github.com/user-attachments/assets/9b67444e-fdb6-45d3-98dc-313cf4aa6484)

