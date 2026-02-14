# Monero-Mining-journey


I started mining Monero on an SFF PC I had around, but I have now switched to a Dell Precision Tower 7810, which has a dual-CPU setup and mines substantially faster 24/7. It utilizes HugePages and all cores on both CPUs, which ends up giving me around 7 kH/s. The CPUs themselves are both Intel Xeons, which I plan to upgrade to the latest generation for better hash rates. I don’t really plan on using the Monero for anything in particular, as it yields less than $100 AUD per year with the current setup.


# Raspberry pi setup.

I have mounted 4 RasPi's in an enclosure 2x Raspi3B, 1x RasPi5B, 1x RasPi4B turning them into a small dedicated infrastructure cluster for my home network. On the RasPi4B I am running Pihole which handles DNS for the netire LAN, blocks ads and tracking domains, while also giving me full visibility over outbound DNS queries. On the RasPi3B i'm running a NTP server using Chrony which syncs with upstream time sources and then distributes time to the rest of my LAN.

# Proxmox Setup

I currently have my Proxmox environment set up on my HP EliteDesk 800 G3 SFF, running my NAS directly on the Proxmox host via Samba. This shares storage from a connected 2-bay drive enclosure, with the disks mounted on the host and exported over SMB to the rest of my network. Keeping the NAS on the host avoids VM overhead and keeps performance simple and reliable, while the same system also serves as a small homelab platform for experimentation.
