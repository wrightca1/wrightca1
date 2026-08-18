### Christopher Wright

I build **EdgeNOS** — an open-source, Linux-based network operating system for enterprise
switches their vendors have abandoned. The hardware still forwards at line rate; it just has
nowhere to go once the last software update ships.

It runs on two switches:

| platform | silicon |
|---|---|
| Edgecore AS5610-52X | Broadcom BCM56846 "Trident+" (PowerPC) |
| Edgecore AS4610-54T | Broadcom BCM56340 "Helix4" (ARM) |

One OS across two architectures and two ASIC generations. Underneath it is a kernel BDE
driver and a datapath daemon of my own, with the chip-init sequence and the forwarding-table
layouts recovered by reverse engineering the silicon on the bench — no licensed Broadcom SDK
involved. A stock routing daemon runs on top and the routes it learns get pushed into
hardware, so packets are forwarded in silicon rather than by the CPU.

Most of this work is reverse engineering, and I write up what I find — including the parts
that didn't work.

**Projects**

- [**edgenos**](https://github.com/wrightca1/edgenos) — the NOS itself, multi-architecture
  and multi-ASIC.
- [**edgecore-5610-reverse-engineering**](https://github.com/wrightca1/edgecore-5610-reverse-engineering)
  — register maps, table formats, SerDes init, L2/L3 write paths and the S-channel protocol
  for the BCM56846.

**Elsewhere**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Christopher_Wright-0A66C2?logo=linkedin&logoColor=white)](https://www.linkedin.com/in/christopher-wright-498b3859)
[![Buy Me a Coffee](https://img.shields.io/badge/Buy_me_a_coffee-FFDD00?logo=buymeacoffee&logoColor=black)](https://buymeacoffee.com/Wrightca1)

Every platform I add starts with buying the switch. They're cheap on eBay; the optics,
cables and lab power aren't. Coffee money buys the next box.
