# Daily Routine

**The working guide for the whole journey** — what to work on each day, and where every track currently stands. Moved here from the Network+ repo on 2026-09-17: it had grown to cover the homelab, simulated labs and parked SOC-analyst work, which made it the journey's routine rather than one exam's.

Training sources, rankings and free-tier notes live in **[practice-resources.md](https://github.com/dmandevv/soc-python-network-plus/blob/main/practice-resources.md)** — this file only says **what to work on and where each track stands.**

Claude follows this file to pick up where things left off, and updates *Where things stand* as blocks are completed. **The homelab's position is tracked privately**, in the homelab repo's `progress.md`.

## The shape of a day

**The blocks are a continuous loop, not a daily reset.** Work down the list in order; a day ends wherever it ends, and the next session picks up at the **next** block. After block 4 it wraps to block 1.

```
  1  Certification  →  2  Simulated lab  →  3  Troubleshooting  →  4  Homelab
  ↑                                                                        │
  └────────────────────────────────────────────────────────────────────────┘
```

| Block | Track | Currently |
|---|---|---|
| **1** | **Certification** — one objective section of the current exam | **Network+** — the walkthrough in [soc-python-network-plus/objectives](https://github.com/dmandevv/soc-python-network-plus/tree/main/objectives) |
| **2** | **Simulated lab** — one scenario, built and verified | **Packet Tracer** — queue below |
| **3** | **Troubleshooting practice** — one exercise, **never on the homelab** | **Network+ Domain 5** — formats below |
| **4** | **Homelab — 2 hours** | The build itself |

**The blocks are defined by role, not by tool,** so the structure outlives each exam. Block 1 follows the journey's step order — Network+ now, then Security+, then CCDL1 — and block 2 moves from Packet Tracer to Containerlab once Network+ is behind it.

**Built 2026-09-10 around one goal: mostly hands-on learning.** **Restructured 2026-09-17:** block 3 was a homelab audit and became external troubleshooting practice, and **the homelab moved to last.**

**⚠️ The homelab is block 4 on purpose.** It needs no discipline and would happily consume a whole day. **Blocks 1 to 3 are the ones that only happen if they come first** — with block 3 no longer lab work, leaving the homelab third would have put a study block after the reward.

- **The lab does not open until 1, 2 and 3 are done in the current pass.** Short blocks are fine; skipped ones are not.
- **The three-day skip trigger applies to blocks 1 to 3.** Avoidance is not the lab's problem.

**⚠️ Do not restart at block 1 each session.** The *Where things stand* table below records where the last session stopped — start at the block **after** it.

## Where things stand

**Last session ended after the homelab** (2026-09-17) — **block 4** under the new order. **Resume at block 1.**

**⚠️ The lab has had most of the last week**, and block 1 was skipped once on 2026-09-13. **19 of 25 Network+ objectives are done, and the largest domain is still ahead:** Domain 5, troubleshooting, five objectives and 24% of the exam.

| Track | Position | Next |
|---|---|---|
| **1 · Certification — Network+** | **4.2 complete** 2026-09-11, quiz **17/20**. **4.3 started** — device hardening written | **4.3 remainder** — NAC, key management, security rules, zones. Then a quiz on all of 4.0. **Then Domain 5** — 5.1 through 5.5, the largest domain at 24% |
| **2 · Simulated lab — Packet Tracer** | **5 scenarios done** — STP, double tagging, OSPF, EtherChannel/LACP, HSRP. NAT scrapped | **Scenario 6 — DHCP relay** |
| **3 · Troubleshooting practice** | **Not started** — block created 2026-09-17 | **Exercise 1 — a scenario ticket** worked through the 5.1 methodology |
| **4 · Homelab** | Tracked privately | See `progress.md` in the homelab repo |

## Block 2 — Packet Tracer scenario queue

**One scenario per entry, each finishable within two blocks**, drawn from the N10-009 objectives and chosen for things the homelab cannot demonstrate — redundancy, dynamic routing, and failure behaviour need more devices than one switch provides.

**⚠️ Exam practice, not homelab modelling.** Each scenario gets its own `.pkt` file. Mixing the two is what made the NAT attempt confusing.

**Findings are written into the matching objective file** in the Network+ repo.

| # | Scenario | Objective | Status |
|---|---|---|---|
| **1** | ~~NAT and PAT~~ | 2.1 | **Scrapped** — the 3560 cannot translate |
| **2** | **Spanning Tree** | 2.2 | ✅ **Complete.** 9 lost pings on PVST+, **zero on RSTP** |
| **2b** | **VLAN double tagging** | 4.2 | ✅ **Complete.** Untagged native hop observed and closed. Attack itself not reproducible in Packet Tracer |
| **3** | **OSPF, single area** | 2.1 | ✅ **Complete.** Adjacencies, AD vs metric, the 100 Mbps reference-bandwidth trap, and **asymmetric routing produced by a one-sided cost change**. Link-failure reconvergence not measured |
| **4** | **EtherChannel / LACP** | 2.2 | ✅ **Complete.** Blocked port removed from STP's view, **zero loss on member failure** vs 9 pings on PVST+, `src-mac` hashing and the single-flow ceiling. **LACP proven blind to VLAN mismatch — CDP caught it.** Two PT fidelity limits recorded |
| **5** | **First-hop redundancy (HSRP)** | 2.1 | ✅ **Complete 2026-09-13.** Virtual MAC as the real mechanism, preempt, 8–10 lost pings vs zero on EtherChannel. **Reproduced the blackhole — a router staying active for a subnet it can no longer route out of.** Tracking unsupported in PT |
| **6** | **DHCP relay.** Central server, remote VLANs, `ip helper-address`, giaddr read in the capture | 3.4 | Queued |
| **7** | **IPv6 and SLAAC.** Dual-stack a segment, watch RA and DAD, compare with DHCPv6 | 1.7 / 3.4 | Queued |
| **8** | **VLSM and summarisation.** Three sites, one block, subnet by hand then summarise | 1.7 | Queued |
| **9** | **Wireless channel planning.** Three APs, non-overlapping channels, co-channel interference | 2.3 | Queued |
| **10** | **QoS.** Voice prioritised over bulk traffic across a congested link | 2.1 | Queued |

## Block 3 — Troubleshooting practice

**Network+ Domain 5 is 24% of the exam and the one domain that can't be learned by reading.** This block practises it hands-on — **entirely outside the homelab.** Nothing here touches the lab: every exercise is a scenario, a simulator, a capture file, or diagnostic tools pointed at the internet.

**Every exercise is worked through the 5.1 methodology**, out loud and in order: identify the problem → establish a theory → test it → plan → implement → verify → document. **The method is what's being practised**, more than any single fault.

**Formats, rotated one per block:**

| Format | What you do | Objectives |
|---|---|---|
| **Scenario ticket** | Claude gives a symptom and an environment, and supplies command output only when you ask for the right command. Diagnose it | 5.1 – 5.4 |
| **Pre-broken Packet Tracer lab** | Open a faulty topology you didn't build and repair it. Cisco Networking Academy troubleshooting activities — the *Network Addressing and Basic Troubleshooting* course is the first to check | 5.1 – 5.3, 5.5 `show` commands |
| **Packet capture** | Find the fault in someone else's traffic — retransmissions, a failed DHCP exchange, DNS errors. **Wireshark's sample captures** library | 5.3 – 5.5 |
| **Diagnostic tools** | `ping`, `traceroute`/`tracert`, `nslookup`/`dig`, `netstat`/`ss`, `arp`, `nmap` — on the desktop, **against external targets only**. `scanme.nmap.org` explicitly permits light scanning | 5.5 |

**Start with scenario tickets and diagnostic tools** — neither depends on the Domain 5 walkthrough in block 1, which is still ahead. **The Packet Tracer course needs its free scope verified** before relying on it.

**⚠️ Never scan or test anything you don't own or have explicit permission for.** `scanme.nmap.org` exists for exactly this reason; most of the internet does not.

## Parked tracks

**Not deleted — parked with their position, so they can be resumed.**

| Track | Position when parked | Why |
|---|---|---|
| **TryHackMe** | TShark room complete. SOC Fundamentals turned out to be premium | Parked 2026-09-10. **Nmap Live Host Discovery** (`nmap01`) is the next room if it returns. Use [tryhackme.com/free-rooms](https://tryhackme.com/free-rooms) — third-party free-room lists are stale |
| **Packet analysis** | **3 complete** — *First to Last*, *Easy as 123*, *Lumma in the Room-ah!* (all answers correct). Tradecraft in [analysis-lessons.md](https://github.com/dmandevv/soc-python-network-plus/blob/main/analysis-lessons.md) | Parked 2026-09-10. Next would be ***It's a trap!*** (2025-06-13). **This is the SOC-analyst track rather than the exam track** — worth restarting after the exam |

## Progression triggers

| When | Change |
|---|---|
| **Network+ objectives finish** | Block 1 becomes Network+ practice exams |
| **Network+ passed** | Block 1 moves to **Security+**, and block 3 to Security+ incident-response scenarios. The parked SOC-analyst tracks become candidates to return |
| **The Packet Tracer queue empties** | Block 2 becomes **Containerlab** |
| **A block in 1–3 is skipped three days running** | Replace it. A track being avoided is not being learned |

## Why the lab comes last

It previously competed with these hours and lost, which is the wrong way round. **Simulated work was a rehearsal for the lab; the lab is the thing itself** — and so it's the reward the other three blocks earn.
