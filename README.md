### Christopher Wright

I build network operating systems for switches and routers their vendors have declared
end-of-life. The hardware still forwards at line rate; it just has nowhere to go once the
last software update ships.

**NOSaic** is the current one — a from-scratch rebuild in Go and C, Apache-2.0. Four boards
forward packets in hardware today: two Aristas and an Edgecore from their own flash, a Cisco
Nexus netboots it. OSPF and IS-IS routing, VLANs, LACP, MLAG, a virtual gateway, and
`nosaic verify` to check the chip against Linux — across three Broadcom generations plus
Intel/Fulcrum silicon. Nothing's called production until it's proven there.

**EdgeNOS** came first and still runs its own boards — five switches, Broadcom
Trident+/Trident2/Trident2+ and Intel/Fulcrum FM6000, PowerPC/ARM/x86_64. NOSaic doesn't
replace it; it's what I learned building it, rebuilt clean.

Most of this is reverse engineering — chip-init sequences, forwarding-table layouts, register
maps recovered on the bench, no licensed Broadcom SDK. I write up what I find, including what
didn't work.

**Projects**

- [**nosaic-switch**](https://github.com/Salvaged-silicon/nosaic-switch) — the current NOS,
  multi-arch and multi-ASIC from day one.
- [**edgenos**](https://github.com/wrightca1/edgenos) — the original, still running its boards.
- [**edgecore-5610-reverse-engineering**](https://github.com/wrightca1/edgecore-5610-reverse-engineering)
  — register maps, table formats, SerDes init, L2/L3 write paths and the S-channel protocol
  for the BCM56846.
- [**relicnosCAT4500**](https://github.com/wrightca1/relicnosCAT4500) — reverse-engineering
  the Cisco Catalyst 4500 K2 ASIC for Linux packet forwarding.
- [**relicnos-c2811**](https://github.com/wrightca1/relicnos-c2811) — Linux 6.6 on a Cisco
  2811, with a driver for its 32-port async module.

**Talks**

- NANOG 98 — "Salvaged Silicon: Building an Open Network OS for a Switch the Industry Left
  for Dead." [Slides](https://nanog.org/events/nanog-98/content/5870/) ·
  [Video](https://youtu.be/NN5yK6MDkQo)

**Elsewhere**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Christopher_Wright-0A66C2?logo=linkedin&logoColor=white)](https://www.linkedin.com/in/christopher-wright-498b3859)
[![X](https://img.shields.io/badge/X-@salvagedsilicon-000000?logo=x&logoColor=white)](https://x.com/salvagedsilicon)
[![Buy Me a Coffee](https://img.shields.io/badge/Buy_me_a_coffee-FFDD00?logo=buymeacoffee&logoColor=black)](https://buymeacoffee.com/Wrightca1)

Every platform I add starts with buying the switch. They're cheap on eBay; the optics,
cables and lab power aren't. Coffee money buys the next box.
