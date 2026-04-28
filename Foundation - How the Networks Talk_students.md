# Day 01 — Foundations: How Do the Networks Talk?

> **Cyber.SoHo Educational Hub** • *From the Industry to the Classroom — Building the IT's Future, Today and Together!*
> **Course:** Networking Essentials (non-credited) — **Day 1 of 6** — **4 hours**

---

## Slide 1 — Title

# **Day 01**
## Foundations — How Do the Networks Talk?

**Networking Essentials — Day 1 of 6**
*Cyber.SoHo Educational Hub*

> *From the Industry to the Classroom — Building the IT's Future, Today and Together!*

---

## Slide 2 — Welcome & Today's Goal

### Why Day 1 Matters

- You will leave today able to **describe a network in plain English**
- You will have a **working lab environment** on your laptop
- You will have produced your **first real engineering artifact** — a 1-page network plan

> *No prior networking knowledge required. We start at zero.*

---

## Slide 3 — Today's Schedule (4 hours)

| Block | Duration | Content |
|---|---|---|
| **Lecture 1** | 1 h | What is a network? Types & speed |
| **Exercise 1** | 1 h | Lab Tools Tour — install & verify |
| **Lecture 2** | 1 h | Getting online + documentation |
| **Exercise 2** | 1 h | Project Stage 1 — *Acme SoHo* |

> Plus **1 h home work per exercise** for the report.

---

## Slide 4 — Learning Outcomes

By the end of today you will be able to:

1. **Define** what a network is and what it carries
2. **Distinguish** PAN, LAN, MAN, WAN
3. **Read** common speed/capacity units (bps → Gbps)
4. **Run** a basic lab on VirtualBox + GNS3
5. **Plan** a small office network on paper

---

## Slide 5 — The Project: *Acme SoHo Consulting*

### Your Recurring Client for 6 Days

- Fictional **8-person consulting firm**
- 2-floor new office, moving in 4 weeks
- Each day = 1 stage of the project
- By Day 6 → complete network plan

> **Cyber.SoHo Network Build Challenge** — your portfolio piece.

---

# 📡 LECTURE 1 — What, Which, How Fast?

---

## Slide 6 — Lecture 1 Roadmap

### Three Big Questions

1. **What is a network?** *(and what actually moves through it?)*
2. **Which kinds exist?** *(PAN, LAN, MAN, WAN)*
3. **How fast / how much?** *(bandwidth, throughput, latency)*

> Each question answered with a real-life example you already know.

---

## Slide 7 — 1.1 What Is a Network?

### Working Definition

> *A network is **two or more devices connected by a medium** that lets them **exchange data** using **agreed rules**.*

Three essential ingredients:

- **Devices** — endpoints that produce/consume data
- **Medium** — copper, fibre, or radio waves
- **Rules (protocols)** — how they take turns talking

---

## Slide 8 — What Counts as a "Device"?

### Endpoints vs Intermediate Devices

| Endpoints | Intermediate Devices |
|---|---|
| Laptop / desktop | Switch |
| Phone / tablet | Router |
| Server / NAS | Access Point (AP) |
| Printer / Smart-TV | Firewall |
| IoT (sensor, lock, doorbell) | Modem |

> Endpoints **make** the data. Intermediate devices **move** it.

---

## Slide 9 — What Carries the Data?

### Three Physical Media

1. **Copper** — twisted-pair (Ethernet), coaxial
2. **Fibre optics** — pulses of light through glass
3. **Radio waves** — Wi-Fi, Bluetooth, cellular

> All three carry the **same logical data** — only the physical layer differs.

---

## Slide 10 — Why "Protocols" Matter

### Rules of the Road

- Devices speak **dozens** of protocols simultaneously
- Each protocol = **one job** (addressing, error-checking, naming…)
- Without protocols → digital chaos
- Standardised by **IETF**, **IEEE**, **ISO**

> *Protocol = the grammar of the network.*

---

## Slide 11 — Key Takeaway: What Is a Network?

> ### 🗝️ Key Takeaway
>
> A network = **devices + medium + rules**.
> Strip any one of those three and you have **no network** — just hardware in a box.

---

## Slide 12 — 1.2 Types of Networks (1/2)

### Sized by Geographic Reach

| Type | Reach | Typical Use |
|---|---|---|
| **PAN** — Personal Area | ~1 m | Phone ↔ earbuds (Bluetooth) |
| **LAN** — Local Area | Building | Home / office Wi-Fi & Ethernet |
| **MAN** — Metropolitan | City | Campus, ISP municipal fibre |
| **WAN** — Wide Area | Country / globe | The internet itself |

---

## Slide 13 — 1.2 Types of Networks (2/2)

### How They Nest

```
   ┌────────── WAN (the internet) ──────────┐
   │                                        │
   │   ┌──── MAN (city / ISP) ─────┐        │
   │   │                           │        │
   │   │   ┌─ LAN (your office) ─┐ │        │
   │   │   │                     │ │        │
   │   │   │   ┌─ PAN (phone ─┐  │ │        │
   │   │   │   │  earbuds)    │  │ │        │
   │   │   │   └──────────────┘  │ │        │
   │   │   └─────────────────────┘ │        │
   │   └───────────────────────────┘        │
   └────────────────────────────────────────┘
```

> Smaller networks **plug into** larger ones — like Russian dolls.

---

## Slide 14 — Other Network Flavours You'll Hear

### Function-based, not size-based

- **WLAN** — Wireless LAN (Wi-Fi)
- **SAN** — Storage Area Network (data-centre disks)
- **CAN** — Campus Area Network (university)
- **VPN** — Virtual Private Network (overlay tunnel)

> Same building blocks, **different purpose**.

---

## Slide 15 — Key Takeaway: Network Types

> ### 🗝️ Key Takeaway
>
> Pick the network type by **distance + purpose**:
> meters → **PAN**, building → **LAN**, city → **MAN**, world → **WAN**.

---

## Slide 16 — 1.3 Speed & Capacity — Three Words

### Stop Confusing Them

- **Bandwidth** — *theoretical* maximum capacity
- **Throughput** — *actual* data delivered per second
- **Latency** — *delay* before the first bit arrives

> Bandwidth is the **size of the pipe**. Throughput is **what comes out**. Latency is **how long until water reaches you**.

---

## Slide 17 — The Highway Analogy

### Visualise It

| Network term | Highway equivalent |
|---|---|
| **Bandwidth** | Number of lanes |
| **Throughput** | Cars actually arriving per minute |
| **Latency** | Travel time from on-ramp to exit |
| **Jitter** | Variation in arrival times |
| **Packet loss** | Cars that crashed and never arrived |

---

## Slide 18 — Units of Capacity

### Bits vs Bytes — read the lowercase 'b'

| Unit | Meaning | Order of magnitude |
|---|---|---|
| **bps** | bits per second | base unit |
| **Kbps** | kilobits / s | 10³ |
| **Mbps** | megabits / s | 10⁶ |
| **Gbps** | gigabits / s | 10⁹ |
| **Tbps** | terabits / s | 10¹² |

> **8 bits = 1 byte** — ISP speeds are in **bits**, downloads shown in **bytes**.

---

## Slide 19 — Real-World Reference Speeds

### Memorise These Anchors

- **2 Mbps** — basic web + email
- **25 Mbps** — single 4K stream
- **100 Mbps** — typical home fibre
- **1 Gbps** — modern home/SoHo fibre
- **10 Gbps+** — business / data-centre

> The **uplink** speed (upload) is often much lower than downlink — check before video-conferencing.

---

## Slide 20 — Speed Sanity Formula

### Estimate Download Time

> **Time (s) ≈ File size (Mb) ÷ Throughput (Mbps)**

Quick mental check:

- 1 GB file = 8000 Mb
- On 100 Mbps connection → **80 s** ideal
- Reality: **~50 % overhead** → expect **2 minutes**

---

## Slide 21 — Latency Reference Numbers

### What "Fast" Actually Means

- **< 1 ms** — same LAN
- **5–20 ms** — same city / ISP
- **40–80 ms** — same continent
- **150–300 ms** — intercontinental
- **600+ ms** — satellite uplink

> Latency is bound by **physics** (speed of light) — bandwidth is bound by **money**.

---

## Slide 22 — Key Takeaway: Speed & Capacity

> ### 🗝️ Key Takeaway
>
> **Bandwidth ≠ Throughput ≠ Latency.**
> A "1 Gbps" pipe can still feel slow if **latency** is high or **packet loss** is wrecking throughput.

---

## Slide 23 — Lecture 1 Recap

### Three Things to Remember

1. **Network = devices + medium + protocols**
2. **PAN < LAN < MAN < WAN** — sized by reach
3. **Bandwidth, throughput, latency** are different — never trade names

> Ready for **Exercise 1** → install & verify your lab tools.

---

# 🧪 EXERCISE 1 — Lab Tools Tour

---

## Slide 24 — Exercise 1 Overview

### Goal: Install & Verify Your Lab

You will install and prove-it-works for:

1. **NetAcad account** *(Cisco free training portal)*
2. **VT-x / AMD-V** virtualisation enabled in BIOS
3. **VirtualBox** *(Type-2 hypervisor)*
4. **GNS3** + GNS3 VM *(network simulator)*
5. **Cisco Modeling Labs Free** *(5-node free tier)*

---

## Slide 25 — Why These Specific Tools?

### Industry Stack — Rationale

- **VirtualBox** → free, cross-platform, GPL v3
- **GNS3** → real Cisco / Juniper images, free
- **CML Free** → official Cisco simulator, 5-node lab
- **NetAcad** → Cisco's free curriculum + Packet Tracer

> Total cost: **€0**. Total industry credibility: **high**.

---

## Slide 26 — Exercise 1 Deliverable

### Your Report Must Show

- Screenshot of NetAcad **enrolment confirmation**
- BIOS screenshot (or `systeminfo` output) proving VT-x / AMD-V is **ON**
- VirtualBox launching a **test VM**
- GNS3 + GNS3 VM **green status**
- Cisco CML Free login **success page**

> Detailed enough that a beginner could follow it.

---

# 📡 LECTURE 2 — Getting Online & Writing It Down

---

## Slide 27 — Lecture 2 Roadmap

### Two Topics

1. **Getting online** — what every device needs
2. **Documentation & schemas** — why and how to draw

> The first half is *technical*. The second half is *what separates juniors from seniors*.

---

## Slide 28 — 2.1 Four Pieces Every Device Needs

### To Reach the Internet

1. **IP address** *(its identity on the network)*
2. **Subnet mask** *(which neighbours are local)*
3. **Default gateway** *(the door to outside)*
4. **DNS server** *(name → address phonebook)*

> Miss any one → "I have Wi-Fi but no internet."

---

## Slide 29 — IP Address — The Postal Address

### IPv4 vs IPv6

| | IPv4 | IPv6 |
|---|---|---|
| **Length** | 32 bits | 128 bits |
| **Format** | `192.168.1.10` | `2001:db8::1` |
| **Total addresses** | ~4.3 billion | ~3.4 × 10³⁸ |
| **Status** | Running out | Future-proof |

> Both can coexist (**dual-stack**). You'll see both in production.

---

## Slide 30 — Subnet Mask — The Neighbourhood Boundary

### What It Decides

- Tells your device **which IPs are local**
- Local IPs → talk **directly**
- Non-local IPs → send via **gateway**

Common masks:

- `255.255.255.0` (`/24`) → 254 usable hosts
- `255.255.0.0` (`/16`) → 65 534 hosts
- `255.255.255.128` (`/25`) → 126 hosts

---

## Slide 31 — Default Gateway — The Front Door

### Always Required

- The **router's IP** on your subnet
- Anything **off-LAN** travels through it
- Without it → device is **island-locked**

> Think of it as the post-office for everything outside your street.

---

## Slide 32 — DNS — The Internet Phonebook

### Names → Addresses

- Humans use names (`google.com`)
- Machines use IPs (`142.250.190.46`)
- DNS is the **translator**

Public resolvers worth knowing:

- **`1.1.1.1`** — Cloudflare
- **`8.8.8.8`** — Google
- **`9.9.9.9`** — Quad9 (privacy / security focus)

---

## Slide 33 — Two Ways to Get These 4 Pieces

### Static vs Dynamic

| | Static | DHCP (Dynamic) |
|---|---|---|
| **Set by** | Human, manually | Router, automatically |
| **Used for** | Servers, printers, gateways | Laptops, phones, IoT |
| **Pros** | Predictable | Zero-touch |
| **Cons** | Tedious; error-prone | Address can change |

> Modern home/SoHo = **DHCP** for clients, **static** for infra.

---

## Slide 34 — DHCP — The Four-Step Handshake

### How "It Just Works"

1. **Discover** — *"Anyone there? I need an IP."*
2. **Offer** — *"Here, take 192.168.1.42."*
3. **Request** — *"Yes, I'll take it."*
4. **Acknowledge** — *"Confirmed — it's yours for 24 h."*

> Mnemonic: **D-O-R-A**.

---

## Slide 35 — Key Takeaway: Getting Online

> ### 🗝️ Key Takeaway
>
> **IP + Mask + Gateway + DNS = Online.**
> Drop any one and you'll feel "the Wi-Fi is down" — even though the cable is fine.

---

## Slide 36 — 2.2 Documentation — The Boring Superpower

### Why It Matters

- Networks **outlive** the engineers who build them
- The job at 3 a.m. is **fixing**, not **rediscovering**
- Auditors, insurers, and lawyers want **paper**
- Every senior I respect documents **first**

> *No diagram = no network.*

---

## Slide 37 — Logical vs Physical Diagrams

### Two Different Pictures

| Logical | Physical |
|---|---|
| Subnets, VLANs, routes | Cables, ports, racks |
| Audience: engineers | Audience: technicians |
| "What talks to what" | "What plugs into what" |
| Stable across moves | Changes on every move |

> Real environments need **both** — they answer different questions.

---

## Slide 38 — The Five Documentation Artifacts

### Minimum Viable Network Doc Pack

1. **Logical diagram** — VLANs, IP ranges, routing
2. **Physical diagram** — racks, cabling, ports
3. **Device inventory** — make, model, MAC, IP, location
4. **IP plan** — which subnet for which purpose
5. **Change log** — every modification, dated

> Skip any of these and **future-you will hate present-you**.

---

## Slide 39 — Tools of the Trade

### Free / Open-Source First

- **draw.io / diagrams.net** — diagramming
- **Excalidraw** — hand-drawn-look sketches
- **LibreOffice Calc** — inventory & IP plan
- **Netbox / phpIPAM** — IP address management
- **BookStack** — wiki / knowledge base

> Paid tools (Visio, Lucidchart, SolarWinds) are *nice* — not *necessary*.

---

## Slide 40 — Naming Conventions

### Boring but Critical

- Devices: **`SITE-ROLE-NUMBER`** → `MTL-SW-01`
- VLANs: **purpose-based** → `VLAN10_CORP`
- Subnets: **document the ‘why'**, not just the IP
- Files: **dated** → `topology_v1_2026-04-28.drawio`

> Consistency > cleverness. Future-you needs to grep this.

---

## Slide 41 — Key Takeaway: Documentation

> ### 🗝️ Key Takeaway
>
> The **diagram is the network**. If it's not drawn and named, it does not exist on Monday morning when somebody calls in sick.

---

## Slide 42 — Lecture 2 Recap

### Three Things to Remember

1. **IP + Mask + Gateway + DNS** = the four pieces
2. **DHCP** automates the four-piece delivery
3. **Diagrams + inventory + IP plan + change log** = the doc pack

> Ready for **Exercise 2** → plan Acme SoHo's first network.

---

# 🧪 EXERCISE 2 — Project Stage 1: Acme SoHo

---

## Slide 43 — Exercise 2 — The Brief

### Acme SoHo Consulting

- 8 employees on **2 floors**
- Laptops, phones, NAS, MFP, video-conf TV, IoT
- **1 Gbps fibre** uplink
- **2 SSIDs** required (corporate + guest)
- Boss: *"We deal with client financial data — do not embarrass me."*
- **Deadline:** 4 weeks

---

## Slide 44 — Exercise 2 — Your Two Artifacts

### Deliverables for Stage 1

1. **`Acme_SoHo_Requirements_v1.md`** — 1-page requirements doc
2. **`Acme_SoHo_Topology_v1.drawio`** — first-pass logical sketch

Plus:

- **`My_Reflection.md`** (5 lines)
- **`Day_01_Exercise_02_Report.md`** (full step-by-step report)

> Same doc-pack you just learned about — applied for real.

---

## Slide 45 — Exercise 2 — Topology Must-Haves

### Minimum Elements to Draw

- **Internet cloud** (top)
- **Edge router / firewall**
- **Core switch** (server closet)
- **1 access switch per floor**
- **2 APs** (one per floor)
- Endpoint groups: **8 laptops**, **MFP**, **NAS**, **TV**, **IoT**
- **4 VLAN colours** (Corporate / Servers / Guest / IoT)

---

## Slide 46 — Exercise 2 — VLAN Plan

### Recommended First-Pass Segmentation

| VLAN | ID | Purpose |
|---|---|---|
| Corporate | 10 | Laptops + corp phones |
| Servers | 20 | NAS, MFP, video-conf TV |
| Guest | 30 | Guest Wi-Fi (isolated) |
| IoT | 40 | Smart-lock, doorbell, sensors |

> **Each VLAN = different colour** in your diagram.

---

## Slide 47 — Day 01 — Final Recap

### What You Now Know

1. ✅ A network = devices + medium + protocols
2. ✅ Network types scale by reach (PAN → WAN)
3. ✅ Bandwidth, throughput, latency are distinct
4. ✅ Four pieces every device needs to be online
5. ✅ DHCP automates delivery of those four pieces
6. ✅ Documentation is a senior-engineer superpower

---

## Slide 48 — Tomorrow (Day 02) — Preview

### Cabling, Standards & Reference Models

- Copper, fibre, wireless — **physical media in depth**
- Ethernet **categories** (Cat5e → Cat8)
- The **OSI 7-layer** model
- The **TCP/IP 4-layer** model
- **Hands-on** with your fresh GNS3 lab

> Have **VirtualBox + GNS3** running before next class.

---

## Slide 49 — Ethics & Liability Reminder

### Read Before Day 02

- All labs only on **systems you own**
- **Never** scan or capture on school / employer / public networks
- Verify every download on **VirusTotal**
- Materials are **AS-IS** — Cyber.SoHo accepts **no liability**

> When in doubt, **do not run it**.

---

## Slide 50 — Closing

# Thank You.

### Questions? Stay 5 minutes after class.

> *Cyber.SoHo Educational Hub*
> **From the Industry to the Classroom — Building the IT's Future, Today and Together!**
> *© 2026 — All rights reserved*
