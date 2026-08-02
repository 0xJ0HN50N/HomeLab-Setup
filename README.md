# HomeLab Setup
My homelab started from a genuine interest in networking after learning many new networking skills from University, and an interest to build a home network that is controlled and secure. It’s backed by a UPS for power redundancy, with two gigabit smart switches. A shuttle PC with 2 ethernet ports sits between the modem and router to monitor WAN traffic. My main compute runs on a Proxmox host with a NAS for storage, supported by a Raspberry Pi cluster for lightweight services and experimentation. I also run a Monero miner on the side for fun and the entire homelab has a dedicated sceen showing live system statistics.
![HomeLab](https://github.com/user-attachments/assets/107f5263-eaef-4e66-a2db-9bffd5cbfffc)


## Raspberry pi setup.

I have mounted 4 RasPi's in an enclosure 2x Raspi3B, 1x RasPi5B, 1x RasPi4B turning them into a small dedicated infrastructure cluster for my home network. On the RasPi4B I am running Pihole which handles DNS for the netire LAN, blocks ads and tracking domains, while also giving me full visibility over outbound DNS queries. On the RasPi3B i'm running a NTP server using Chrony which syncs with upstream time sources and then distributes time to the rest of my LAN.
![RasPi_Enclosure](https://github.com/user-attachments/assets/7959eba9-9c79-4cf2-93a7-d571da64e7c8)

## Proxmox Setup

I currently have my Proxmox environment set up on my HP EliteDesk 800 G3 SFF, running my NAS directly on the Proxmox host via Samba. This shares storage from a connected 2-bay drive enclosure, with the disks mounted on the host and exported over SMB to the rest of my network. Keeping the NAS on the host avoids VM overhead and keeps performance simple and reliable, while the same system also serves as a small homelab platform for experimentation.
![Proxmox_NAS](https://github.com/user-attachments/assets/55ec513b-3197-481f-9cef-42414edbccc3)

## Transparent WAN Monitoring Bridge
By utilising a Shuttle SFF PC with two ethernet ports I was able to turn it into an effective transparent Layer 2 network bridge for passive WAN traffic monitoring. It's positioned inline between an NBN modem and my router, the system forwards ethernet frames without performing routing, NAT, or any firewalling, allowing all internet traffic to pass through unmodified while remaining effectively invisible to the network. I have traffic mirrored internally to a tool called Suricata for intrusion detection and packet analysis, it gives me peace of mind by providing me with complete visibility into inbound and outbound WAN traffic before it reaches the router.

<img width="797" height="330" alt="IDS" src="https://github.com/user-attachments/assets/e42e7435-2730-4582-8532-c72b5cab5757" />

## Monero-Mining-journey

I started mining Monero on an SFF PC I had laying around, but I have now switched to a Dell Precision Tower 7810, which has a dual-CPU setup and mines substantially faster, which I leave on 24/7. It utilizes HugePages and all cores on both CPUs, which ends up giving me around 5 kH/s. The CPUs themselves are both Intel Xeons, which I plan to upgrade to the latest generation for better hash rates. I don’t really plan on using the Monero for anything in particular, as it yields less than $100 AUD per year with the current setup. I do enjoy it as a side hobby and to learn about crypto currency.

<img width="1572" height="539" alt="XMR" src="https://github.com/user-attachments/assets/cc5a9684-4f9a-473f-9a5e-795708ff4cb1" />


