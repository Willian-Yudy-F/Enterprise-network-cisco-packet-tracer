

# Enterprise Multi-Site Network — Cisco Packet Tracer

Multi-router enterprise network built in Cisco Packet Tracer as part of the *Networking Foundations* unit at AIT (Sydney).

## Overview

This project simulates a corporate network connecting five sites through a 5-router backbone, serving 10 departmental LANs with end-to-end connectivity, dynamic IP allocation via DHCP, name resolution through an internal DNS server, and an internal web service. The goal was to apply addressing, routing and core network services in a realistic enterprise topology.

## Architecture

**Routers (5):** Core, Admin, Ops, West, East

**LANs (10):** Finance, Procurement, Sales, IT, HR, Executive, Engineering, R&D, CustomerA, CustomerB

**WAN links:**
- FastEthernet — Admin ↔ Core, Ops ↔ Core
- Serial — Core ↔ West, Core ↔ East, West ↔ East

## Network topology

<img width="1470" height="956" alt="Screenshot 2026-05-21 at 1 01 29 am" src="https://github.com/user-attachments/assets/7d2cbe79-244c-4636-a69f-5b0e2c4b6e67" /> 

## Services configured

- **DHCP** — dynamic IP allocation across departmental LANs
- **DNS** — internal name resolution
- **Web server** — internal HTTP service reachable from all LANs
- **Routing** — [coloca aqui: RIP / OSPF / ambos — o que você usou]

## Addressing

The address plan was designed using **VLSM** to match the host requirements of each LAN without wasting address space. Full subnet allocation is documented in `addressing.pdf` and `subnetting.pdf`.

## Files in this repository

| File | Description |
|------|-------------|
| `enterprise-network.pkt` | Cisco Packet Tracer project file |
| `addressing.pdf` | IP addressing plan per LAN |
| `subnetting.pdf` | VLSM derivation and subnet calculations |
| `topology-screenshot.png` | Logical topology diagram |

## How to open

1. Install [Cisco Packet Tracer](https://www.netacad.com/courses/packet-tracer) (version 8.x or later)
2. Open `enterprise-network.pkt`
3. Use the *Simulation* mode to trace traffic between LANs

## What I learned

- Designing VLSM addressing plans for heterogeneous LAN sizes
- Configuring dynamic routing across multi-router topologies
- Deploying core network services (DHCP, DNS, HTTP) and validating end-to-end connectivity
- Documenting network design for hand-off and review

---

Built by [Willian Yudy Futema](https://github.com/Willian-Yudy-F) — IT student at AIT, Sydney.



