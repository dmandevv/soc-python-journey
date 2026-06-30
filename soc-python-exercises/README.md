# Red Team Python Journey

Documenting my path from Python fundamentals to penetration testing.

**Goal:** Red team penetration tester, entering through a SOC Analyst role.  
**Language:** Python — scripting, automation, and security tooling.  
**Background:** CS degree, alarm monitoring (SOC-adjacent), full-stack JS experience.

---

## Repos

| Step | Repo | Status |
|---|---|---|
| 1 — Python Fundamentals | *(this repo)* | ✅ Complete |
| 2 — Networking with Python | [redteam-python-networking](https://github.com/dmandevv/redteam-python-networking) | ✅ Complete |
| 3 — CTF Challenges | TBD | Not started |
| 4 — Security+ | TBD | Not started |
| 5 — Security Tools | TBD | Not started |

---

## Step 1 — Python Fundamentals ✅

**Completed:** May 2026

### What I built

**Python Exercises** — four standalone scripts, each tested with pytest:

| File | Concepts covered |
|---|---|
| `grade_book.py` | Type hints, dataclasses, list comprehensions, JSON I/O |
| `student_report.py` | File I/O, context managers, data formatting |
| `pipeline.py` | Generators, chaining data transformations |
| `decorators.py` | Writing and applying decorators, `functools.wraps` |

**FastAPI CRUD App** — a fully functional REST API:

- `POST /items`, `GET /items`, `GET /items/{id}`, `PUT /items/{id}`, `DELETE /items/{id}`
- SQLAlchemy ORM with SQLite, Pydantic request/response models
- Dependency injection for DB sessions
- pytest integration tests with a real in-memory test database (not mocked)
- Async route handlers

### Key skills locked in

- Type hints, dataclasses, properties
- List comprehensions, generators
- File I/O, JSON, context managers
- Decorators
- pytest — unit and integration testing
- FastAPI, Pydantic, SQLAlchemy
- REST API design, dependency injection, async basics

---

## Step 2 — Networking with Python ✅

**Completed:** June 2026 — [redteam-python-networking](https://github.com/dmandevv/redteam-python-networking)

### What I built

| # | Exercise | What it does |
|---|----------|--------------|
| 01 | TCP echo server | Raw socket client/server, connection handling |
| 02 | Threaded port scanner | `ThreadPoolExecutor`, concurrent TCP connects |
| 03 | HTTP from scratch | Raw `GET` over a socket, response parsing |
| 04 | DNS client | UDP + TCP queries, zone transfer (AXFR), wire format parsing |
| 05 | Scapy basics | Packet sniffing, ICMP ping, SYN scan, ARP scan, DNS query |
| 06 | Packet injection | Forged ICMP/UDP, TCP RST injection, IP spoofing |
| 07 | ARP spoofing + MITM | ARP cache poisoning, loopback traffic interception |
| 08 | Scapy port scanner | SYN scan, OS fingerprinting via TTL, banner grabbing |

### Key skills locked in

- [x] How TCP/IP works at the code level
- [x] Sockets — raw connections, client/server programs
- [x] HTTP from scratch (before using libraries)
- [x] Port scanning
- [x] Reading and parsing network data
- [x] DNS lookups
- [x] Libraries: `socket`, `requests`, `scapy`
- [x] Packet crafting and injection
- [x] ARP spoofing and man-in-the-middle attacks
- [x] SYN scanning and service fingerprinting

---

## Step 3 — CTF Challenges

- [ ] TryHackMe — complete beginner path
- [ ] Write Python scripts to automate challenge solutions
- [ ] HackTheBox — once comfortable with TryHackMe
- [ ] Build a portfolio of tools written during CTFs

---

## Step 4 — CompTIA Security+

- [ ] Study networking concepts (overlaps with Step 2)
- [ ] Study cryptography basics
- [ ] Study threat intelligence and attack types
- [ ] Study incident response procedures
- [ ] Pass the exam

---

## Step 5 — First Role

- [ ] SOC Analyst (entry point — alarm monitoring background is directly relevant)
- [ ] Build 2-3 portfolio projects (security tools written in Python)
- [ ] OSCP certification (gold standard for pen testers)
- [ ] Transition to junior penetration tester

---

## Security Tools (building along the way)

- [x] Port scanner
- [x] Network packet sniffer
- [ ] Password strength checker / cracker
- [ ] Directory/subdomain enumerator
- [ ] Basic keylogger (lab environment only)
- [ ] CLI tool that automates a CTF technique

---

## Resources

- [TryHackMe](https://tryhackme.com)
- [HackTheBox](https://hackthebox.com)
- Security+: Professor Messer (free), CompTIA CertMaster
- [OSCP](https://www.offensive-security.com/pwk-oscp/)
