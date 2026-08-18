### Christopher Wright

I build **EdgeNOS** — an open-source, Linux-based network operating system for enterprise
switches their vendors have abandoned. The hardware still forwards at line rate; it just has
nowhere to go once the last software update ships.

It runs on three switches:

| platform | silicon |
|---|---|
| Edgecore AS5610-52X | Broadcom BCM56846 "Trident+" (PowerPC) |
| Edgecore AS4610-54T | Broadcom BCM56340 "Helix4" (ARM) |
| Arista 7150S-52 | Intel/Fulcrum FM6000 — discontinued, no SDK available |

The 7150 cold-boots into EdgeNOS, brings the ASIC up from reset, peers OSPF with the switch
next to it, and forwards traffic in hardware with none of the vendor's software running.
Getting there was mostly reverse engineering. It used to boot by replaying a 389,809-write
register capture taken off the vendor OS — 93.5% of that is gone now, replaced by code that
works the settings out from the hardware's behaviour instead of parroting a recording.

It's an alpha and I say so plainly: two ports of fifty-two on the FM6000, routing is most of
what it does on that chip, and there's a long list of features still to port across. I write
up what I find, including the parts that didn't work.

**Projects**

- [**edgenos**](https://github.com/wrightca1/edgenos) — the NOS itself, multi-architecture and
  multi-ASIC. FM6000 bring-up lives on
  [`feature/arista-7150-fm6000`](https://github.com/wrightca1/edgenos/tree/feature/arista-7150-fm6000).
- [**edgecore-5610-reverse-engineering**](https://github.com/wrightca1/edgecore-5610-reverse-engineering)
  — register maps, table formats, SerDes init and S-channel protocol for the BCM56846.
- [**arista-onie-installer**](https://github.com/wrightca1/arista-onie-installer) ·
  [**swi-tools**](https://github.com/wrightca1/swi-tools) — getting ONIE and stock images onto
  Arista hardware.

**Elsewhere**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Christopher_Wright-0A66C2?logo=linkedin&logoColor=white)](https://www.linkedin.com/in/christopher-wright-498b3859)
[![Buy Me a Coffee](https://img.shields.io/badge/Buy_me_a_coffee-FFDD00?logo=buymeacoffee&logoColor=black)](https://buymeacoffee.com/Wrightca1)

Every platform I add starts with buying the switch. They're cheap on eBay; the optics,
cables and lab power aren't. Coffee money buys the next box.
