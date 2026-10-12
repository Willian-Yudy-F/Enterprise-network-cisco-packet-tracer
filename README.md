# Enterprise Multi-Site Network — Cisco Packet Tracer

## In plain English
Imagine a company with five offices and ten departments that all need to talk to each other, get an IP address automatically, find servers by name and open an internal website. This project builds that whole network inside **Cisco Packet Tracer** (a network simulator) and proves that every computer can reach every other one.

Built for the *Foundation Networks* unit (CMP3044) of my Bachelor of IT at AIT Sydney. The scenario was a fictional company called **Kestrel Industries**.

## What is in the network

| Part | Details |
| --- | --- |
| Routers (5) | Core, Admin, Ops, West, East |
| Department LANs (10) | Finance, Procurement, Sales, IT, HR, Executive, Engineering, R&D, Customer A, Customer B |
| WAN links | FastEthernet: Admin–Core, Ops–Core · Serial: Core–West, Core–East, West–East |
| Services | DHCP (automatic IP addresses), DNS (names instead of numbers), internal web server, dynamic routing between the five routers |

## Network topology

<img width="1470" height="956" alt="Packet Tracer topology with five routers and ten LANs" src="https://github.com/user-attachments/assets/7d2cbe79-244c-4636-a69f-5b0e2c4b6e67" />

## How the addressing was planned
Each LAN has a different number of computers, so instead of giving every LAN the same block of addresses I used **VLSM (Variable Length Subnet Masking)**: bigger departments get bigger blocks, small ones get small blocks, and nothing is wasted. Every subnet was then tested with ping and traceroute from end to end.

## What I learned
- How to turn a written business requirement into an IP address plan
- Configuring routers, DHCP pools and a DNS server from the command line
- Troubleshooting connectivity one hop at a time when a ping fails

## Files
This repository holds the write-up and the topology image. The Packet Tracer file (.pkt) and the subnetting tables were submitted through the university portal; ask me if you would like to see them.

---
Willian Yudy Futema · [Portfolio](https://willian-yudy-f.github.io/) · [LinkedIn](https://www.linkedin.com/in/willian-yudy-futema/)
