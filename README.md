# NetworkWalks_ZenmapNetworkScanning

Week 2 project for the NetworkWalks Cybersecurity Internship — Network Scanning with Zenmap (Project Module 5).

## Overview

This project documents a hands-on network reconnaissance exercise using Zenmap, the official GUI frontend for Nmap. The goal was to identify my local network configuration, discover live hosts on the LAN, and visualize the network topology.

## Objective

Learn to use Zenmap to:
- Identify a local IP address and LAN subnet
- Perform a Ping Scan to discover live hosts on a network
- Extract IP and MAC address information for each live host
- Generate and export a visual network topology

## Methodology

1. **Installed Zenmap** from the official source (nmap.org) on Windows.
2. **Identified local network configuration** using `ipconfig` in Command Prompt, locating the active Wi-Fi adapter's IPv4 address and subnet mask.
3. **Ran a Ping Scan** (`nmap -sn <subnet>/24`) against the full local subnet to discover all responsive hosts without performing a full port scan.
4. **Reviewed the scan output** to extract host count, IP addresses, and MAC addresses for each live device.
5. **Generated a topology diagram** via Zenmap's Topology tab and exported it as a PDF.

## Findings

**Subnet scanned:** `192.168.1.0/24`

**Live hosts discovered:** 5

| IP Address | MAC Address | Notes |
|---|---|---|
| 192.168.1.* | 18:B0:A4:E3:**:** | 
| 192.168.1.* | 86:7E:6B:A7:**:** | 
| 192.168.1.* | 96:0E:B9:31:**:** | 
| 192.168.1.* | A8:77:E5:16:**:** | 
| 192.168.1.* | *(local machine)* | 

**Command used:**
```
nmap -sn 192.168.1.0/24
```

## Topology

See `topology.pdf` in this repository for the exported network map, generated via Zenmap's Topology tab.

## Key Takeaways

- A Ping Scan (`-sn`) discovers live hosts without probing ports, making it a fast, low-footprint first step in network reconnaissance.
- Not every connected device is guaranteed to appear in ping scan results — some devices are configured to ignore ICMP echo requests, so results reflect *responsive* hosts rather than a guaranteed full inventory.
- MAC address vendor lookups (shown automatically by Nmap) can help quickly identify device types (e.g. router hardware vs. unknown/randomized MACs common on modern phones for privacy).
- Visualizing network topology helps build an intuitive picture of how devices relate to each other on a LAN — a foundational skill before moving into deeper enumeration or vulnerability scanning.

## Disclaimer

This scan was performed only on a private home network that I own and administer. Scanning networks without authorization may be illegal depending on jurisdiction — always obtain explicit permission before scanning any network you do not own.

## Author

Built as part of the NetworkWalks Cybersecurity Internship (Week 2, Project Module 5: Network Scanning with Zenmap).
