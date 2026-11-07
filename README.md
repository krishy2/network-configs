# network-configs

<p align="center">
  <a href="https://buymeacoffee.com/szorfoktato"><img src="https://img.shields.io/badge/Buy%20me%20a%20coffee-szorfoktato-FFDD00?style=for-the-badge&logo=buymeacoffee&logoColor=black" alt="Buy me a coffee"></a><br>
  If these guides save you time, you can support the work at <a href="https://buymeacoffee.com/szorfoktato">buymeacoffee.com/szorfoktato</a> ☕
</p>

---

## About this repository

This is a collection of **real-world network setups, documented as guidebooks**.

Every use case here started as a working production configuration. Each guide explains how the setup is built and also **why it works**: the design decisions, how the protocols interact, what the firewall has to allow, and the non-obvious tricks that make it behave.

Each guide aims to:

- **Describe a configuration that is actually running.** Nothing is a lab-only idea.
- **Be anonymized.** IP addresses are moved into neutral ranges such as `10.155.0.0/16` and documentation addresses. Hostnames, keys, passwords and the names of people, companies and sites are removed.
- **Go in depth.** Expect topology diagrams, addressing plans, packet walks, firewall breakdowns, sanitized config snippets, troubleshooting steps and a list of recommended improvements.
- **Be reusable.** Each guide ends with a checklist for adapting the setup to your own network.

Most guides are written for **MikroTik RouterOS 7**, but the concepts (WireGuard, GRE, OSPF, NAT, firewalling) carry over to any platform.

---

## Use cases

| # | Guide | Platform | Topics | Summary |
|---|---|---|---|---|
| 1 | [**Multi-site to multi-site VPN**](multi-site-to-multi-site-VPN/README.md) | MikroTik RouterOS 7 | WireGuard · GRE · OSPF · Firewall · NAT | A hub-and-spoke VPN that connects many sites so every LAN can reach every other LAN. WireGuard provides encrypted transport through NAT, a GRE tunnel per site carries the traffic, and OSPF routes everything automatically. The guide also explains a one-armed node that is **not** its LAN's default gateway, yet everything still works. |
| 2 | [**Multi-WAN with DHCP: load balancing, failover, QoS**](multi-WAN-load-balancing-failover-QoS/README.md) | MikroTik RouterOS 7 | DHCP WANs · PCC · Routing tables · Failover · QoS · Firewall | A dual-WAN edge router where both uplinks are DHCP (one of them double-NATed). It balances new connections across both uplinks with PCC and per-WAN routing tables, fails over by route distance, and shapes per-LAN traffic with PCQ simple queues. It also covers a self-learning blacklist firewall and three separate LANs (guest, office, POS), plus what to fix so failover detects upstream outages and QoS priorities actually take effect. |

*More use cases are coming. Watch or star the repository to get notified.*

---

## How to use these guides

1. Start with the **Topology** and **Addressing plan** sections of a guide to get the big picture.
2. Read the **"why"** sections before copying any configuration. Most of the value is in the reasoning.
3. Use the **sanitized configuration reference** as a template, and replace the example addresses, names and keys with your own.
4. Follow the **checklist** when you adapt or extend the setup, and use the **troubleshooting** table when something doesn't come up.

> ⚠️ The configurations are provided as-is. Always review them against your own security requirements and test them in a maintenance window before you deploy.

---

## License

See [LICENSE](LICENSE).

---

<p align="center">
  ☕ Found something useful here? Support more guides like this: <a href="https://buymeacoffee.com/szorfoktato"><b>buymeacoffee.com/szorfoktato</b></a><br><br>
  <a href="https://buymeacoffee.com/szorfoktato"><img src="https://img.shields.io/badge/Buy%20me%20a%20coffee-szorfoktato-FFDD00?style=for-the-badge&logo=buymeacoffee&logoColor=black" alt="Buy me a coffee"></a>
</p>
