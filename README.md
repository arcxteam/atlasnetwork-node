# atlasnetwork-node




sign up now https://testnet.atlasnetwork.xyz/refer/1cGToWb
search your machines node with id or paste any address wallet : https://explorer.atlasnetwork.xyz/machine

run this before new install

```
sudo apt update && sudo apt upgrade -y 
sudo apt-get install iptables iptables-persistent
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

