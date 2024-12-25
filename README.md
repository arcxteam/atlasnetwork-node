![Testnet Node - Full Guides cover (3)](https://github.com/user-attachments/assets/89b2b17a-d361-4fb8-accd-0af75a2dfeef)


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
> Atlas machine is have very `sensitive config/compilation services tools`, in order to run Atlas Node, its need a server recommended specs

| Requirement                      | Details                                   |
|----------------------------------|-------------------------------------------|
| Services                         | Full root, firewall allow out/ingoing all traffic  |
| RAM/Memory                       | 4 GB - Up                                    |
| CPU/vCPU                         | 2 Cores - Up                                |
| Storage Space                    | 80 GB - Up                                   |
| Supported OS Linux               | Ubuntu >22.04 Up & Debian >12 Up          |
| Internet service                 | 1Gbps unlimited network bandwidth         |
| Drivers                          | Kernel >6.1-Latest, incl-latest security     |

> [!CAUTION]
> Do this before you start, if you don't want get machine to `suspended, failed, pending/stuck etc`, at provider node. plz run this.

```
sudo apt update && sudo apt upgrade -y && \
sudo apt-get install --install-recommends linux-generic-hwe-22.04 -y && \
sudo apt autoremove --purge -y && \
sudo apt-get install iptables iptables-persistent -y && \
sudo iptables -P INPUT ACCEPT && \
sudo iptables -P OUTPUT ACCEPT && \
sudo iptables -F INPUT && \
sudo iptables -F OUTPUT && \
sudo iptables -A INPUT -p tcp --dport 22 -j ACCEPT && \
sudo iptables -A OUTPUT -p tcp --dport 22 -j ACCEPT && \
sudo netfilter-persistent save && \
sudo reboot
```
**and too**

```
sudo apt update && sudo apt upgrade -y && \
sudo apt install ufw -y && \
sudo ufw allow ssh && \
sudo ufw default allow incoming && \
sudo ufw default allow outgoing && \
sudo ufw enable && \
sudo ufw reload && \
sudo ufw status verbose
```

> check up to date of **kernel adn ufw status**
```diff
- sudo uname -r
> output version: >6.xxxx or 6.8.0-50-generic
- sudo ufw status verbose
> Status: active
> Logging: on (low)
> Default: allow (incoming), allow (outgoing), deny (routed)
> New profiles: skip
```
**2. Setup for Network**

`Which chain does Atlas testnet support? ARB Sepolia Testnet`
- Arbitrum Sepolia ETH
- Need some ETH testnet go to [bridge official](https://bridge.arbitrum.io/?destinationChain=arbitrum-sepolia&sourceChain=sepolia) Sepolia ETH or googling faucet
- Change RPC network for ARB Sepolia ETH, use it `https://arbitrum-sepolia.drpc.org`

## 2. Installation - Run Atlas Network Node
**1. Atlas Provider Dashboard**

- I appreciate to SIGNUP through my link for Atlas Network [![Dashboard](https://img.shields.io/badge/HERE-DASHBOARD-8a2be2)](https://testnet.atlasnetwork.xyz/refer/1cGToWb)
- Complete go to faucet & focus on task node run **provider machine** and **add machine** to other take action
- For provider is here https://testnet-providers.atlasnetwork.xyz/ go to add machine
- Plz, if you first time `add 1 machine`
- Setup provider > staking > sign transaction > copy command to your terminal ssh
- If having many **failed tx** try tomorrow or try a fresh wallet with the first **SIGNUP** again & clear cache/cookies Atlas only

**2. Run the Command**
```diff
- This example cmd
- Copy command after the success sign-tx, into your terminal ssh
> curl -L https://get.atlasnetwork.dev | sh -s - xWm9nyjUy6KpZaJOHEFehVtvbut0QxFCx5GTF4pCXzsojhdN3bRZjktL41d47AAP
```
- Back into provider-dashboard for a view step like ![Step](https://img.shields.io/badge/CONFIGURING-brown) | ![Step](https://img.shields.io/badge/AWAITING_STAKE-brown) | ![Step](https://img.shields.io/badge/ACTIVE-brightgreen)

> Important; Early Offer: You don't need any NODE tokens, just click on **Stake One machine per day**

## 3. Verifying Task & Status Running
**1. Atlas Main-Dashboard**

`Back into main-dashboard for a complete task`

- Verify task scroll **add a machine** and **register as compute provider**
- Complete to all setting account & task if you need


**2. Status Provider Running**

`Search machine details and workloads uptime`

- For searching **machine name** anyone can copy paste any SIGN address wallet https://explorer.atlasnetwork.xyz/machine
- Uptime : last checked : less than a minute ago ; **GOOD (100%)** The overall health of your machine is good, you've had zero errors in the last 24 hours.

## 4. Usefull Command Logs
**1. 

- Check status Atlas `sudo systemctl status atlasnetwork-provider.service`
- Check info logs Atlas `sudo journalctl -u atlasnetwork-provider.service`

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

