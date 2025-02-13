![Testnet Node - Full Guides cover (3)](https://github.com/user-attachments/assets/89b2b17a-d361-4fb8-accd-0af75a2dfeef)

# A Complete Guide - Run NodeOps Network as Provider & Provers (previously Atlas Network)

What is NodeOps Network? The leading chain-agnostic, AI-powered DePIN Orchestration layer for general-purpose compute, economically secured by Autonomous Verifiable Services (AVS). NodeOps Network provides the economic security to the DePIN compute powering all of NodeOps' products and services.

## Here We Go...GAS 

**`Is there incentivized?` ![Confirm](https://img.shields.io/badge/confirm-yes-brightgreen)**

> [!IMPORTANT]
> **FAQs**: NodeOps network (Atlas Network) is thrilled to announce the launch of its **Incentivized Testnet** a major milestone in our journey to reshape DePIN orchestration. Wave Two Points Program is here as **Early Access**, **Impact: Contribute**, and **Rewards Galore: Earn NPs (NODE POINTs)**. Each participant will find step-by-step guides in the Marketplace to help them get started and make the most of their contributions see here to all [FAQs](https://docs.atlasnetwork.dev/docs/Navigate%20Quests/FAQ) or [Twitter](https://x.com/BuildOnAtlas/status/1869028708704456818) & [Coinlist](https://coinlist.co/atlas-network-incentivized-testnet)

---

## 1. Preparation/Prerequisites
**1. Hardware Requirements**

> [!CAUTION]
> NodeOps machine is have very `sensitive config/compilation services tools`, in order to run NodeOps, its need a server recommended specs

| Requirement                      | Details                                   |
|----------------------------------|-------------------------------------------|
| Services                         | Full **root**, firewall allow out/ingoing all **traffic**  |
| RAM/Memory                       | 4 GB - Up                                    |
| CPU/vCPU                         | 2 Cores - Up                                |
| Storage Space                    | 80 GB - Up                                   |
| Supported OS Linux               | Ubuntu >22.04 Up & Debian >12 Up          |
| Internet service                 | 1Gbps unlimited network bandwidth         |
| Drivers                          | Kernel >6.1.x or new latest, include security     |

> [!CAUTION]
> Do this before you start, if you don't want get machine to `suspended, failed, pending/stuck etc`, at provider node. plz run this. Read docs NodeOps

- The machine will be rejected if: **(1)** It runs workloads in addition to the NodeOps Network assigned loads **(2)** If SWAP is enabled
- Following for using **UFW firewall-upgrade kernel-port**, command this into ssh-terminal that'll redetect any system Ubuntu 20-22-24

```
sudo apt update -y && sudo apt upgrade -y && \
UBUNTU_VERSION=$(lsb_release -rs | cut -d '.' -f1) && \
if [ "$UBUNTU_VERSION" = "20" ]; then \
  KERNEL_PACKAGE="linux-generic-hwe-20.04"; \
elif [ "$UBUNTU_VERSION" = "22" ]; then \
  KERNEL_PACKAGE="linux-generic-hwe-22.04"; \
elif [ "$UBUNTU_VERSION" = "24" ]; then \
  KERNEL_PACKAGE="linux-generic-hwe-24.04"; \
else \
  echo "Versi Ubuntu Not Compatible: $UBUNTU_VERSION"; \
  exit 1; \
fi && \
sudo apt-get install --install-recommends $KERNEL_PACKAGE -y && \
sudo apt autoremove --purge -y && \
sudo apt install ufw -y && \
sudo ufw default deny incoming && \
sudo ufw default allow outgoing && \
sudo ufw allow ssh && \
sudo ufw allow 8472/udp && \
sudo ufw allow 10250/tcp && \
sudo ufw allow 51820/udp && \
sudo ufw allow 51821/udp && \
sudo ufw enable && \
sudo ufw reload && \
sudo ufw status verbose
```

> check up to date of **kernel and ufw status**
```diff
- command
- sudo uname -r
> output version: >6.xxxx or 6.8.0-50-generic
- command
- sudo ufw status verbose
> Status: active
> Logging: on (low)
> Default: deny (incoming), allow (outgoing), deny (routed)
> New profiles: skip
```
**2. Setup for Network**

`Which chain does Atlas testnet support? ARB Sepolia Testnet`
- Arbitrum Sepolia ETH
- Need some ETH testnet go to [bridge official](https://bridge.arbitrum.io/?destinationChain=arbitrum-sepolia&sourceChain=sepolia) Sepolia ETH or googling faucet
- Change RPC network for ARB Sepolia ETH, use it `https://arbitrum-sepolia.drpc.org`

## 2. Installation
**1. NodeOps Provider Dashboard**

- I appreciate to `SIGNUP ACCOUNT` through my link here.. [![Dashboard](https://img.shields.io/badge/SIGNUP-DASHBOARD-8a2be2)](https://testnet.nodeops.network/refer/mPaVx04)
- Complete go to faucet & focus on task node run **provider machine** and **add machine** to other task action
- For provider is here https://testnet-providers.nodeops.network/ go to add machine
- Plz, if you first time `add 1 machine`
- Setup provider > staking > sign transaction > copy command to your terminal ssh
- If having many **failed tx** try tomorrow or try a fresh wallet with the first **SIGNUP** again & clear cache/cookies NodeOps only

**2. Run the Command**
```diff
- This example cmd
- Copy command from the website after the success sign-tx/id, ex: like here
> curl -L https://get.atlasnetwork.dev | sh -s - xWm9nyjUy6KpZaJOHEFehVtvbut0QxFCx5GTF4pCXzsojhdN3bRZjktL41d47AAP
```
- Go back to `provider-dashboard` for a view step like ![Step](https://img.shields.io/badge/CONFIGURING-brown) .. ![Step](https://img.shields.io/badge/AWAITING_STAKE-brown) ... ![Step](https://img.shields.io/badge/ACTIVE-brightgreen)

> Important; Early Offer: You don't need any NODE tokens, just click on **Stake One machine per day**

![Testnet Node - Full Guides cover (4)](https://github.com/user-attachments/assets/65ce470a-8568-4a7f-a8fc-4081900cc12e)

## 3. Verifying Task & Status Running
**1. NodeOps Main-Dashboard**

`Go Back to main-dashboard for a complete task`

- Verify task scroll **add a machine** and **register as compute provider**
- Complete to all setting account & task if you need

**2. Status Provider Running**

`Search machine details and workloads uptime`

- To search for active `machine name` can copy/paste the address wallet into https://explorer.nodeops.network/machine
- Uptime : last checked : less than a minute ago ; **GOOD (100%)** The overall health of your machine is good, you've had zero errors in the last 24 hours.

![Desktop-screenshot-02-13-2025_12_54_AM](https://github.com/user-attachments/assets/3f2bc7f7-dcef-42c8-8b35-a96f45cde233)

![NodeOps-Provider-dashboard-02-13-2025_02_23_AM](https://github.com/user-attachments/assets/975102f0-bd55-4d62-817d-aeb961ab49e6)


## 4. Usefull Command Logs

- Check status Atlas
```
sudo systemctl status atlasnetwork-provider.service
```
- Check info logs Atlas
```
sudo journalctl -u atlasnetwork-provider.service
```
```
sudo journalctl -u atlasnetwork-provider.service --no-pager --lines=50
```
- Check info Restart Atlas
```
sudo systemctl restart atlasnetwork-provider.service
```

- Check stopping run Atlas
```
sudo systemctl stop atlasnetwork-provider.service
```
- So, **warning** for delete/stop/clean/update service NodeOPS, but dont worry you can get fresh **(cleanup)**
```bash
sudo systemctl stop atlasnetwork-provider.service && \
sudo systemctl disable atlasnetwork-provider.service && \
sudo rm -f /etc/systemd/system/atlasnetwork-provider.service && \
sudo systemctl daemon-reload && \
sudo rm -f /usr/local/bin/atlasnetwork-provider && \
sudo rm -rf /etc/atlasnetwork /var/lib/atlasnetwork && \
sudo systemctl reset-failed
```
