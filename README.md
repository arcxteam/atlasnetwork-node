![Testnet Node - Full Guides cover (3)](https://github.com/user-attachments/assets/89b2b17a-d361-4fb8-accd-0af75a2dfeef)

# A Complete Guide - Run NodeOPS as Provider & (previously Atlas Network)

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
| Services                         | Full **root**, firewall allow out/ingoing all **traffic**  |
| RAM/Memory                       | 4 GB - Up                                    |
| CPU/vCPU                         | 2 Cores - Up                                |
| Storage Space                    | 80 GB - Up                                   |
| Supported OS Linux               | Ubuntu >22.04 Up & Debian >12 Up          |
| Internet service                 | 1Gbps unlimited network bandwidth         |
| Drivers                          | Kernel >6.1-Latest, incl-latest security     |

> [!CAUTION]
> Do this before you start, if you don't want get machine to `suspended, failed, pending/stuck etc`, at provider node. plz run this.

- Following for using **UFW firewall+upgrade kernel & port**, command this into ssh-terminal will redetect for system Ubuntu 20-22-24**

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
sudo ufw default allow incoming && \
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

> check up to date of **kernel adn ufw status**
```diff
- command
- sudo uname -r
> output version: >6.xxxx or 6.8.0-50-generic
- command
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

- I appreciate to `SIGNUP ACCOUNT` through my link click... [![Dashboard](https://img.shields.io/badge/HERE-DASHBOARD-8a2be2)](https://testnet.nodeops.network/refer/mPaVx04)
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
- Go back to `provider-dashboard` for a view step like ![Step](https://img.shields.io/badge/CONFIGURING-brown) .. ![Step](https://img.shields.io/badge/AWAITING_STAKE-brown) ... ![Step](https://img.shields.io/badge/ACTIVE-brightgreen)

> Important; Early Offer: You don't need any NODE tokens, just click on **Stake One machine per day**

![Testnet Node - Full Guides cover (4)](https://github.com/user-attachments/assets/65ce470a-8568-4a7f-a8fc-4081900cc12e)

## 3. Verifying Task & Status Running
**1. Atlas Main-Dashboard**

`Go Back to main-dashboard for a complete task`

- Verify task scroll **add a machine** and **register as compute provider**
- Complete to all setting account & task if you need

**2. Status Provider Running**

`Search machine details and workloads uptime`

- To search for a `machine name` anyone can copy/paste the SIGN address wallet into https://explorer.atlasnetwork.xyz/machine
- Uptime : last checked : less than a minute ago ; **GOOD (100%)** The overall health of your machine is good, you've had zero errors in the last 24 hours.

![Desktop-screenshot-02-13-2025_12_54_AM](https://github.com/user-attachments/assets/3f2bc7f7-dcef-42c8-8b35-a96f45cde233)

![Atlas-Provider-dashboard-12-21-2024_02_39_AM](https://github.com/user-attachments/assets/38972847-fe48-4bb0-a149-a3d5bf08cf47)

## 4. Usefull Command Logs

- Check status Atlas
```
sudo systemctl status atlasnetwork-provider.service
```
- Check info logs Atlas
```
sudo journalctl -u atlasnetwork-provider.service
```
- Check info Restart Atlas
```
sudo systemctl restart atlasnetwork-provider.service
```

- Check stopping run Atlas
```
sudo systemctl stop atlasnetwork-provider.service
```
- Check **warning** for delete/stop/clean/update service Atlas
```bash
sudo systemctl stop atlasnetwork-provider.service && \
sudo systemctl disable atlasnetwork-provider.service && \
sudo rm -f /etc/systemd/system/atlasnetwork-provider.service && \
sudo systemctl daemon-reload && \
sudo rm -f /usr/local/bin/atlasnetwork-provider && \
sudo rm -rf /etc/atlasnetwork /var/lib/atlasnetwork /root/.atlas-network && \
sudo systemctl reset-failed
```
