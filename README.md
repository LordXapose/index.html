# Hexploit-Labs Curriculum & Roadmaps

> Free, hands-on training in offensive security, systems, and Web3 structured as clear paths from **scratch to advanced**.

This document is the master curriculum for Hexploit-Labs. It defines the **roadmaps** (guided routes), the **courses** inside each, and the **modules** inside each course, across six domains:

1. [Linux](#1-linux)
2. [Computer Networking](#2-computer-networking)
3. [Web Security](#3-web-security)
4. [Exploit Development](#4-exploit-development)
5. [Web3 & Smart Contract Development](#5-web3--smart-contract-development)
6. [Cyber Security — Scratch to Advanced](#6-cyber-security--scratch-to-advanced)

Everything is designed to be learned by *doing*: watch a lesson, grab the lab files, and practice against a target you control. All practice is **lab-only and authorized-targets-only** the skills here are taught for defense, research, and building.

---

## How the roadmaps work

Each domain is a **roadmap** split into three stages:

| Stage | Badge | Meaning |
|-------|-------|---------|
| **Foundation** | `Beginner` | Zero assumptions. Core concepts and vocabulary. |
| **Core** | `Intermediate` | The working skills you'll use daily. |
| **Advanced** | `Advanced` | Depth, modern techniques, and real engagements. |

Every **course** lists:

- **What it is**  a one-paragraph description.
- **Modules** the ordered lessons/topics.
- **You'll be able to** concrete, testable outcomes.
- **Tools** what you'll install and use.
- **Practice** labs, CTF rooms, or a mini-project.

Each roadmap ends with a **Capstone** a portfolio-worthy project that proves the whole track.

> **Legend used in trees:** `└──` next step · `├──` parallel option · `⇒` unlocks · `★` capstone

---

## Global dependency map

Don't learn these in random order. Two tracks are the bedrock for everything else:

```
                        ┌─────────────┐     ┌────────────────────┐
       START HERE  ⇒    │    LINUX    │  +  │ COMPUTER NETWORKING │
                        └──────┬──────┘     └──────────┬─────────┘
                               │                       │
              ┌────────────────┼───────────────────────┼──────────────────┐
              │                │                        │                  │
        ┌─────▼──────┐   ┌─────▼───────┐         ┌──────▼──────┐    ┌───────▼────────┐
        │ WEB        │   │ EXPLOIT     │         │ WEB3 / SMART│    │  CYBER SECURITY│
        │ SECURITY   │   │ DEVELOPMENT │         │  CONTRACTS  │    │  (the umbrella)│
        └────────────┘   └─────────────┘         └─────────────┘    └────────────────┘
              │                │                        │                  │
              └────────────────┴───────────┬────────────┴──────────────────┘
                                           ▼
                            ★ Cyber Security Capstone Engagement
```

- **Web3** is the one track you *can* start in parallel with a little Linux it leans on programming more than on networking.
- **Cyber Security** is the umbrella track: it references the others and adds the defensive, cloud, and governance pieces that tie a career together.

---

## Suggested combined career paths

These chain courses *across* domains into a single goal-oriented roadmap.

### ▸ Path A Web Application Pentester
```
Linux (Foundation+Core)
  └── Computer Networking (Foundation+Core)
        └── Web Security (all 3 stages)
              └── Cyber Security: Recon, Reporting & Red-Team electives
                    ⇒ ★ Full web app assessment + professional report
```

### ▸ Path B Exploit Developer / Vulnerability Researcher
```
Linux (Foundation+Core)
  └── Programming for Security (C + Assembly)
        └── Exploit Development (all 3 stages)
              └── Cyber Security: Malware Analysis + Fuzzing electives
                    ⇒ ★ Write a working exploit for a known CVE in a lab VM
```

### ▸ Path C Smart Contract Auditor
```
Linux (Foundation only)
  └── Web3 & Smart Contract Development (Foundation+Core)
        └── Web3 Security & Auditing (Advanced)
              ⇒ ★ Audit a DeFi mini-protocol and publish a findings report
```

### ▸ Path D SOC Analyst / Blue Team
```
Linux (Foundation+Core)
  └── Computer Networking (all 3 stages)
        └── Cyber Security: Defensive, Logging/SIEM, IR & Detection electives
              ⇒ ★ Investigate a simulated intrusion end-to-end
```

---
---

# 1. Linux

> The operating system every hacker, defender, and developer lives in. Master the shell and everything else gets easier.

**Prerequisites:** None.
**Outcome:** Comfortably operate, script, administer, and harden a Linux system from the command line.
**Aligns with:** CompTIA Linux+, LPIC-1, and the practical baseline for OSCP/PNPT.

### Roadmap at a glance

| Stage | Course | Level | Hours | Focus |
|-------|--------|-------|-------|-------|
| Foundation | 1.1 First Contact with Linux | Beginner | 3 | Install, shell, filesystem |
| Foundation | 1.2 Files, Permissions & Text | Beginner | 4 | Navigation, `chmod`, grep/sed/awk |
| Core | 1.3 Users, Processes & Services | Intermediate | 4 | Accounts, `systemd`, jobs |
| Core | 1.4 Bash Scripting | Intermediate | 5 | Automate everything |
| Advanced | 1.5 System Administration & Hardening | Advanced | 6 | Secure, monitor, maintain |
| Advanced | 1.6 Containers & the Kernel | Advanced | 5 | Docker, namespaces, `/proc` |

### Stage 1 Foundation

#### Course 1.1 — First Contact with Linux `Beginner · ~3h`
Get oriented: what Linux is, how to install it (VM or WSL), and how to survive in a terminal.
**Modules**
- Why Linux, and choosing a distro (Ubuntu, Kali, Arch)
- Installing in a VM / WSL / dual-boot
- The shell: prompt, commands, arguments, flags
- Getting help: `man`, `--help`, `tldr`
- The Filesystem Hierarchy Standard (`/etc`, `/var`, `/home`, `/bin`)

**You'll be able to:** move around any Linux box and read its layout.
**Tools:** VirtualBox/VMware, a terminal.
**Practice:** Set up your own Ubuntu + Kali lab VMs.

#### Course 1.2 Files, Permissions & Text `Beginner · ~4h`
The daily bread: manipulating files and slicing text.
**Modules**
- Navigating & managing files (`ls`, `cd`, `cp`, `mv`, `rm`, `find`)
- Viewing & editing (`cat`, `less`, `nano`, intro to `vim`)
- Permissions & ownership (`chmod`, `chown`, octal notation)
- Redirection & pipes (`>`, `>>`, `|`)
- Text processing power tools (`grep`, `sed`, `awk`, `cut`, `sort`, `uniq`)

**You'll be able to:** find, filter, and transform data without leaving the shell.
**Practice:** Parse a log file to extract all failed login IPs.

### Stage 2 Core

#### Course 1.3 — Users, Processes & Services `Intermediate · ~4h`
How a running system actually works.
**Modules**
- Users, groups, and `sudo`
- Processes & jobs (`ps`, `top`/`htop`, `kill`, `&`, `jobs`, `nohup`)
- Services with `systemd` (`systemctl`, units, enabling on boot)
- Scheduling with `cron` and timers
- Logs and the journal (`journalctl`, `/var/log`)

**You'll be able to:** manage what runs, when, and as whom.
**Practice:** Create a service that runs a script on boot and logs its output.

#### Course 1.4 Bash Scripting `Intermediate · ~5h`
Turn repetitive work into one command.
**Modules**
- Variables, quoting, and command substitution
- Conditionals and test expressions
- Loops (`for`, `while`) and reading input
- Functions and arguments (`$1`, `$@`)
- Practical scripting: parsing output, building small tools

**You'll be able to:** automate recon, backups, and setup with your own scripts.
**Practice:** Write a script that pings a subnet and reports live hosts.

### Stage 3 Advanced

#### Course 1.5 System Administration & Hardening `Advanced · ~6h`
Run a server like a professional and lock it down.
**Modules**
- Package management deep dive (`apt`/`dnf`/`pacman`, repositories)
- Networking from the CLI (`ip`, `ss`, `ssh`, `scp`, firewalls with `ufw`/`nftables`)
- Disks, mounts, and storage (`df`, `du`, `lsblk`, `fstab`)
- Hardening: SSH keys, disabling root login, least privilege, `fail2ban`
- Mandatory access control: SELinux / AppArmor overview
- Auditing with `auditd` and awareness of privilege-escalation vectors

**You'll be able to:** stand up and secure a production-style Linux server.
**Practice:** Harden a fresh VPS and run a self-audit checklist.

#### Course 1.6 Containers & the Kernel `Advanced · ~5h`
The modern deployment layer and what sits beneath it.
**Modules**
- Kernel, modules, and the `/proc` & `/sys` interfaces
- Namespaces and cgroups — what "containers" really are
- Docker fundamentals: images, containers, volumes, networks
- Writing a `Dockerfile` and `docker-compose`
- Container security basics

**You'll be able to:** containerize apps and reason about isolation.
**Practice:** Containerize one of your own scripts/tools.

### ★ Capstone Build & Harden a Linux Server
Provision a Linux server, deploy a small service in Docker, automate its setup with a Bash script, harden it, and document every decision in a short runbook.

---
---

# 2. Computer Networking

> How data actually moves between machines the map every attacker and defender reads.

**Prerequisites:** Basic Linux (Course 1.1–1.2 helps).
**Outcome:** Understand, capture, analyze, and secure network traffic across the stack.
**Aligns with:** CompTIA Network+, Cisco CCNA.

### Roadmap at a glance

| Stage | Course | Level | Hours | Focus |
|-------|--------|-------|-------|-------|
| Foundation | 2.1 Networking First Principles | Beginner | 3 | Models, topologies |
| Foundation | 2.2 Addressing & Subnetting | Beginner | 4 | IPv4/IPv6, CIDR, MAC/ARP |
| Core | 2.3 Protocols That Run the Internet | Intermediate | 5 | TCP/UDP, DNS, DHCP, HTTP/TLS |
| Core | 2.4 Packet Analysis with Wireshark | Intermediate | 4 | Read the wire |
| Core | 2.5 Routing & Switching | Intermediate | 5 | VLANs, routing, NAT |
| Advanced | 2.6 Network Security & Defense | Advanced | 5 | Firewalls, IDS/IPS, VPN |
| Advanced | 2.7 Wireless & Cloud Networking | Advanced | 4 | 802.11, cloud VPCs |

### Stage 1 Foundation

#### Course 2.1 Networking First Principles `Beginner · ~3h`
**Modules**
- What a network is: hosts, links, NICs, topologies
- The OSI model and the TCP/IP model side by side
- Encapsulation: how a message becomes packets and frames
- LAN vs WAN vs the Internet
- Bandwidth, latency, throughput

**You'll be able to:** describe what happens end-to-end when you load a web page.
**Practice:** Diagram your home network by layer.

#### Course 2.2 Addressing & Subnetting `Beginner · ~4h`
**Modules**
- IPv4 addresses, classes, and private ranges
- Subnetting and CIDR notation (the part everyone fears — made simple)
- IPv6 essentials
- MAC addresses and the ARP process
- Ports and sockets

**You'll be able to:** subnet a network on paper and read any IP/port pair.
**Practice:** Given a CIDR block, list usable hosts and the broadcast address.

### Stage 2 Core

#### Course 2.3 Protocols That Run the Internet `Intermediate · ~5h`
**Modules**
- TCP deep dive: the 3-way handshake, flags, sequence numbers
- UDP and when it's used
- DNS: resolution, record types, and why it's a frequent target
- DHCP and NAT
- HTTP/HTTPS and the TLS handshake
- Everyday protocols: SSH, FTP, SMTP, ICMP

**You'll be able to:** explain the traffic behind common services.
**Practice:** Trace a DNS lookup and a TLS handshake conceptually.

#### Course 2.4 Packet Analysis with Wireshark `Intermediate · ~4h`
**Modules**
- Capturing traffic (`tcpdump` and Wireshark)
- Display filters and following streams
- Dissecting TCP/UDP/HTTP/DNS in a capture
- Spotting anomalies in traffic
- Saving, exporting, and reporting findings

**You'll be able to:** open a `.pcap` and explain what's happening.
**Practice:** Analyze a provided capture and identify the protocols in use.

#### Course 2.5 Routing & Switching `Intermediate · ~5h`
**Modules**
- Switching, MAC tables, and VLANs
- Routing basics: default gateways and routing tables
- Static routing vs dynamic (RIP, OSPF, a taste of BGP)
- NAT/PAT in depth
- Building a virtual topology (Packet Tracer / GNS3)

**You'll be able to:** design and reason about a small routed network.
**Practice:** Build a two-subnet routed lab and make hosts talk.

### Stage 3 — Advanced

#### Course 2.6 Network Security & Defense `Advanced · ~5h`
**Modules**
- Firewalls: stateful vs stateless, rule design
- IDS/IPS concepts (Snort/Suricata overview)
- VPNs and tunneling (IPsec, WireGuard)
- Network segmentation and zero-trust ideas
- Traffic-based detection and network forensics basics

**You'll be able to:** design defensive network controls and read alerts.
**Practice:** Write firewall rules to segment a lab network.

#### Course 2.7 Wireless & Cloud Networking `Advanced · ~4h`
**Modules**
- 802.11 Wi-Fi fundamentals and security (WPA2/WPA3)
- Wireless auth and common weaknesses (conceptual)
- Cloud networking: VPCs, subnets, security groups
- Load balancers, CDNs, and DNS at scale
- Software-defined networking overview

**You'll be able to:** reason about modern wireless and cloud network design.
**Practice:** Map a cloud VPC with public/private subnets on paper.

### ★ Capstone Design, Build & Document a Virtual Network
Build a multi-subnet lab (GNS3/Packet Tracer) with routing, a firewall, and services, capture representative traffic, and produce a network diagram + a short traffic-analysis report.

---
---

# 3. Web Security

> The web is the biggest attack surface on earth. Learn to find and fix its flaws ethically, in labs you own.

**Prerequisites:** Linux (1.1–1.2), Networking (2.1–2.3), a little HTML/JS.
**Outcome:** Assess a web application methodically and write a professional findings report.
**Aligns with:** OWASP Top 10, PortSwigger Web Security Academy, PNPT/OSCP web modules.

### Roadmap at a glance

| Stage | Course | Level | Hours | Focus |
|-------|--------|-------|-------|-------|
| Foundation | 3.1 How the Web Works (for Hackers) | Beginner | 3 | HTTP, cookies, sessions |
| Foundation | 3.2 Your Web Testing Lab | Beginner | 3 | Burp, DVWA, Juice Shop |
| Core | 3.3 Injection & XSS | Intermediate | 6 | SQLi, command inj, XSS |
| Core | 3.4 Auth, Access Control & CSRF | Intermediate | 5 | Sessions, IDOR, CSRF |
| Core | 3.5 SSRF, Uploads & Misconfig | Intermediate | 5 | SSRF, traversal, headers |
| Advanced | 3.6 Advanced Server-Side Attacks | Advanced | 6 | SSTI, deserialization |
| Advanced | 3.7 APIs, JWT & Business Logic | Advanced | 5 | REST/GraphQL, JWT, logic |
| Advanced | 3.8 Bug Bounty Methodology | Advanced | 4 | Recon → report → payout |

### Stage 1 Foundation

#### Course 3.1 How the Web Works (for Hackers) `Beginner · ~3h`
**Modules**
- HTTP requests & responses, methods, status codes
- Headers, cookies, and sessions
- The browser security model and same-origin policy
- URLs, parameters, and encoding
- Client vs server responsibilities

**You'll be able to:** read and modify raw HTTP and understand where trust lives.
**Practice:** Inspect and replay requests with your browser dev tools.

#### Course 3.2 Your Web Testing Lab `Beginner · ~3h`
**Modules**
- Installing Burp Suite (Community) and configuring the proxy
- Deploying intentionally vulnerable apps (DVWA, OWASP Juice Shop) in Docker
- Intercepting, repeating, and encoding requests
- Mapping an application's attack surface
- Note-taking and evidence discipline

**You'll be able to:** set up a safe, legal environment to practice everything that follows.
**Practice:** Proxy Juice Shop through Burp and map its endpoints.

### Stage 2 Core (the OWASP essentials)

#### Course 3.3 Injection & XSS `Intermediate · ~6h`
**Modules**
- How injection happens: untrusted input meets an interpreter
- SQL injection: discovery, impact, and defense (prepared statements)
- Command injection concepts and mitigation
- Cross-Site Scripting: reflected, stored, and DOM-based
- Output encoding, CSP, and remediation

**You'll be able to:** identify and responsibly demonstrate injection/XSS in a lab, and explain the fix.
**Tools:** Burp Suite, browser dev tools.
**Practice:** Solve the SQLi and XSS labs on PortSwigger Academy.

#### Course 3.4 Auth, Access Control & CSRF `Intermediate · ~5h`
**Modules**
- Authentication weaknesses and secure session design
- Broken access control and IDOR (Insecure Direct Object References)
- Privilege escalation within an app
- Cross-Site Request Forgery and defenses (tokens, SameSite)
- Password storage done right (hashing, salting)

**You'll be able to:** test authorization boundaries and session handling.
**Practice:** Find an IDOR in a lab app and document the impact.

#### Course 3.5 SSRF, Uploads & Misconfiguration `Intermediate · ~5h`
**Modules**
- Server-Side Request Forgery: theory, impact, and mitigation
- File upload flaws and path/directory traversal
- Security misconfiguration and hardening headers
- Sensitive data exposure and error handling
- Components with known vulnerabilities (dependency hygiene)

**You'll be able to:** assess a broader class of server-side issues.
**Practice:** Exploit a traversal lab and propose a fix.

### Stage 3 Advanced

#### Course 3.6 Advanced Server-Side Attacks `Advanced · ~6h`
**Modules**
- Server-Side Template Injection (SSTI)
- Insecure deserialization
- Advanced SQLi (blind, time-based) and WAF-evasion *concepts*
- XXE (XML External Entity)
- Chaining vulnerabilities for greater impact

**You'll be able to:** approach complex, multi-step web vulnerabilities.
**Practice:** Complete an "expert" PortSwigger lab and write it up.

#### Course 3.7 APIs, JWT & Business Logic `Advanced · ~5h`
**Modules**
- REST and GraphQL API security testing
- JWT structure and common implementation flaws
- OAuth/OIDC flows and where they break
- Business-logic vulnerabilities (the bugs scanners miss)
- Rate limiting, mass assignment, and API-specific issues

**You'll be able to:** test modern API-driven applications.
**Practice:** Audit a sample API for auth and logic flaws.

#### Course 3.8 Bug Bounty Methodology `Advanced · ~4h`
**Modules**
- Reconnaissance and asset discovery (`subfinder`, `ffuf`, `nuclei`)
- Scoping and reading program rules
- Prioritizing high-impact classes
- Writing a clear, reproducible vulnerability report
- Responsible disclosure and professional communication

**You'll be able to:** run a structured bug-hunting workflow and report well.
**Tools:** Burp, `ffuf`, `nuclei`, `subfinder`, `sqlmap`.
**Practice:** Recon a bug-bounty *scope you're authorized for* and draft a report template.

### ★ Capstone Full Web Application Assessment
Perform a methodical assessment of a vulnerable application, chain at least one multi-step finding, and deliver a professional pentest report (executive summary, findings, severity, remediation).

---
---

# 4. Exploit Development

> Understand software at the memory level and learn how vulnerabilities become exploits for research and defense, on lab targets only.

**Prerequisites:** Linux (1.1–1.4), comfort with C, and patience.
**Outcome:** Analyze binaries, understand memory-corruption classes, and develop exploits in a controlled lab.
**Aligns with:** OffSec OSED, pwn.college, and CTF `pwn` categories.

>  **Ethics & legality:** exploit development is taught here for vulnerability research, defensive engineering, and CTFs. Only ever run these techniques against systems you own or are explicitly authorized to test.

### Roadmap at a glance

| Stage | Course | Level | Hours | Focus |
|-------|--------|-------|-------|-------|
| Foundation | 4.1 Programming for Security (C) | Beginner | 6 | C, memory model |
| Foundation | 4.2 Assembly & Computer Architecture | Beginner | 6 | x86/x64, registers |
| Foundation | 4.3 Debuggers & Disassembly | Intermediate | 4 | GDB, Ghidra |
| Core | 4.4 Stack-Based Memory Corruption | Intermediate | 6 | Overflows, shellcode |
| Core | 4.5 Bypassing Modern Mitigations | Advanced | 6 | DEP/ASLR, ROP |
| Advanced | 4.6 Heap Exploitation | Advanced | 7 | UAF, heap internals |
| Advanced | 4.7 Fuzzing & Bug Discovery | Advanced | 5 | AFL++, triage |

### Stage 1 Foundation

#### Course 4.1 Programming for Security (C) `Beginner · ~6h`
**Modules**
- C syntax, pointers, and arrays
- Manual memory management (`malloc`/`free`)
- The process memory layout: stack, heap, data, text
- Calling conventions and the function call stack
- Compiling, linking, and reading `objdump` output

**You'll be able to:** read C and reason about how it maps to memory.
**Practice:** Write and dissect small C programs that manipulate the stack.

#### Course 4.2 Assembly & Computer Architecture `Beginner · ~6h`
**Modules**
- CPU registers, the instruction cycle, and endianness
- x86/x64 assembly essentials (mov, push, pop, call, ret, jmp)
- The stack in assembly: prologues, epilogues, and return addresses
- Syscalls and how programs talk to the kernel
- Reading compiler-generated assembly

**You'll be able to:** follow program execution instruction by instruction.
**Practice:** Hand-trace a simple function's stack frame.

#### Course 4.3 Debuggers & Disassembly `Intermediate · ~4h`
**Modules**
- GDB with `pwndbg`/`GEF`: breakpoints, stepping, inspecting memory
- Static analysis with Ghidra / radare2
- Recognizing functions, loops, and control flow in disassembly
- Scripting interaction with `pwntools`
- Building a repeatable analysis workflow

**You'll be able to:** examine any binary dynamically and statically.
**Practice:** Reverse a small crackme in a lab.

### Stage 2 Core

#### Course 4.4 Stack-Based Memory Corruption `Intermediate · ~6h`
**Modules**
- Why buffer overflows happen (unbounded input meets fixed buffers)
- Overwriting the return address — the classic control-flow hijack
- Introduction to shellcode and its role
- Format-string vulnerabilities
- Secure coding: bounds checking and safe APIs

**You'll be able to:** explain and demonstrate a stack overflow in a lab binary, and describe the defense.
**Tools:** GDB+pwndbg, pwntools.
**Practice:** Solve introductory `pwn` challenges (pwn.college / picoCTF).

#### Course 4.5 Bypassing Modern Mitigations `Advanced · ~6h`
**Modules**
- Stack canaries: purpose and detection
- DEP/NX and why injected shellcode stops working
- ASLR/PIE and the role of information leaks
- Return-Oriented Programming (ROP) fundamentals
- Putting it together against a hardened lab target

**You'll be able to:** reason about and work through standard mitigations in a research setting.
**Practice:** Build a ROP chain for a provided lab binary.

### Stage 3 Advanced

#### Course 4.6 Heap Exploitation `Advanced · ~7h`
**Modules**
- How the glibc heap allocator works (chunks, bins, tcache)
- Use-after-free and double-free classes
- Heap grooming concepts
- Modern allocator hardening
- Case studies from CTF challenges

**You'll be able to:** understand heap-based corruption at a research level.
**Practice:** Work through curated heap challenges in a lab.

#### Course 4.7 Fuzzing & Bug Discovery `Advanced · ~5h`
**Modules**
- Coverage-guided fuzzing with AFL++
- Harnessing a target for fuzzing
- Triaging and de-duplicating crashes
- Root-causing a crash to a vulnerability class
- Coordinated/responsible disclosure

**You'll be able to:** find and triage bugs systematically.
**Practice:** Fuzz an intentionally buggy program and triage the crashes.

### ★ Capstone Exploit a Known CVE in a Lab VM
Pick a CVE with a public advisory, reproduce it in an isolated VM, understand the root cause, and develop a working proof-of-concept — then write up the vulnerability and its mitigation.

---
---

# 5. Web3 & Smart Contract Development

> Build on Ethereum, then learn to break and secure what you built. Development *and* auditing in one track.

**Prerequisites:** Basic programming; a little Linux. Networking not required.
**Outcome:** Write, test, deploy, and audit Solidity smart contracts and DeFi primitives.
**Aligns with:** Cyfrin Updraft, Ethereum developer resources, smart-contract audit practice.

### Roadmap at a glance

| Stage | Course | Level | Hours | Focus |
|-------|--------|-------|-------|-------|
| Foundation | 5.1 Blockchain & Ethereum Fundamentals | Beginner | 4 | Chains, EVM, gas |
| Foundation | 5.2 Solidity Fundamentals | Beginner | 6 | Types, functions, storage |
| Core | 5.3 Tokens & Contract Patterns | Intermediate | 5 | ERC-20/721/1155, proxies |
| Core | 5.4 Testing & Tooling with Foundry | Intermediate | 5 | Forge, fuzzing, scripts |
| Core | 5.5 DeFi Primitives | Intermediate | 6 | AMMs, lending, staking |
| Advanced | 5.6 Gas, Assembly & Optimization | Advanced | 5 | Yul, storage packing |
| Advanced | 5.7 Smart Contract Security & Auditing | Advanced | 8 | Vulns, methodology, reports |

### Stage 1 Foundation

#### Course 5.1 Blockchain & Ethereum Fundamentals `Beginner · ~4h`
**Modules**
- Blocks, hashing, and consensus (PoW → PoS)
- Wallets, keys, and addresses
- Ethereum accounts, transactions, and gas
- The EVM: what runs your code
- Reading a block explorer

**You'll be able to:** explain how a transaction is created, signed, and executed.
**Practice:** Send a testnet transaction and trace it on a block explorer.

#### Course 5.2 Solidity Fundamentals `Beginner · ~6h`
**Modules**
- Contract structure, types, and state variables
- Functions, visibility, and modifiers
- Mappings, structs, arrays, and storage vs memory
- Events and error handling (`require`, custom errors)
- Deploying with Remix and a first contract

**You'll be able to:** write and deploy a basic smart contract.
**Practice:** Build a simple storage or voting contract.

### Stage 2 Core

#### Course 5.3 Tokens & Contract Patterns `Intermediate · ~5h`
**Modules**
- ERC-20 fungible tokens
- ERC-721 and ERC-1155 (NFTs and multi-token)
- Access control (Ownable, roles)
- Upgradeability and the proxy pattern
- Using OpenZeppelin safely

**You'll be able to:** implement standard tokens and common patterns.
**Practice:** Ship your own ERC-20 with access control on a testnet.

#### Course 5.4 Testing & Tooling with Foundry `Intermediate · ~5h`
**Modules**
- Setting up Foundry (`forge`, `cast`, `anvil`)
- Writing unit tests in Solidity
- Fuzz testing and invariants
- Deployment scripts and environment management
- Debugging failing tests

**You'll be able to:** test contracts to a professional standard.
**Practice:** Achieve full test coverage on your token from 5.3.

#### Course 5.5 DeFi Primitives `Intermediate · ~6h`
**Modules**
- Automated Market Makers and the `x·y=k` model
- Lending/borrowing mechanics
- Staking and yield
- Oracles and price feeds
- Composability and integration risks

**You'll be able to:** understand and build core DeFi building blocks.
**Practice:** Build a minimal AMM (Uniswap-V2-style) and test swaps.

### Stage 3 Advanced

#### Course 5.6 Gas, Assembly & Optimization `Advanced · ~5h`
**Modules**
- How gas is metered and where it's spent
- Storage layout and packing
- Inline assembly (Yul) basics
- Common optimization patterns and their trade-offs
- Benchmarking with Foundry gas reports

**You'll be able to:** measurably reduce a contract's gas costs.
**Practice:** Optimize the AMM and document gas savings.

#### Course 5.7 Smart Contract Security & Auditing `Advanced · ~8h`
**Modules**
- Reentrancy and the checks-effects-interactions pattern
- Access-control and authorization bugs
- Oracle manipulation and flash-loan-assisted attacks
- Integer and rounding issues; unchecked external calls
- MEV awareness
- Tooling: Slither (static analysis) and Echidna (fuzzing)
- Audit methodology and writing a findings report
- Case studies (e.g., historical bridge and reentrancy incidents)

**You'll be able to:** audit a contract, classify findings by severity, and report them professionally.
**Tools:** Foundry, Slither, Echidna.
**Practice:** Audit a deliberately vulnerable contract and produce a report.

### ★ Capstone Build, Test & Audit a DeFi Mini-Protocol
Design a small protocol (e.g., an AMM or staking vault), test it thoroughly with Foundry, then audit it as if it were someone else's code and publish a professional findings report.

---
---

# 6. Cyber Security Scratch to Advanced

> The umbrella track. It ties the others together and adds the defensive, cloud, and governance skills that make a career.

**Prerequisites:** Linux (1.1–1.4) and Networking (2.1–2.4). Web Security and Exploit Dev are recommended electives.
**Outcome:** Operate across offense and defense, run an engagement end-to-end, and understand the wider security landscape.
**Aligns with:** CompTIA Security+, TCM PNPT, OffSec OSCP, ISC² CISSP (management tier).

### Roadmap at a glance

| Stage | Course | Level | Hours | Focus |
|-------|--------|-------|-------|-------|
| Foundation | 6.1 Security First Principles | Beginner | 4 | CIA, threats, risk |
| Foundation | 6.2 Applied Cryptography | Beginner | 4 | Hashing, PKI, TLS |
| Core | 6.3 Offensive Security & the Kill Chain | Intermediate | 7 | Recon → post-exploit |
| Core | 6.4 Defensive Security & Blue Team | Intermediate | 6 | Hardening, SIEM, IR |
| Core | 6.5 Digital Forensics & Incident Response | Intermediate | 5 | Evidence, timelines |
| Advanced | 6.6 Red Teaming & Adversary Emulation | Advanced | 7 | TTPs, C2, evasion |
| Advanced | 6.7 Cloud Security | Advanced | 6 | AWS/Azure/GCP |
| Advanced | 6.8 GRC, Risk & Career | Advanced | 4 | Compliance, paths |

### Stage 1 Foundation

#### Course 6.1 Security First Principles `Beginner · ~4h`
**Modules**
- The CIA triad and security goals
- Threats, vulnerabilities, risk, and controls
- Threat modeling basics
- Defense in depth and least privilege
- The security landscape: red, blue, and purple teams

**You'll be able to:** speak the language of security and reason about risk.
**Practice:** Threat-model a simple web app.

#### Course 6.2 Applied Cryptography `Beginner · ~4h`
**Modules**
- Symmetric vs asymmetric encryption
- Hashing and message integrity
- Digital signatures and certificates (PKI)
- TLS in practice
- Common crypto mistakes to avoid

**You'll be able to:** choose and reason about cryptographic building blocks.
**Practice:** Verify a file's signature and inspect a TLS certificate.

### Stage 2 Core

#### Course 6.3 Offensive Security & the Kill Chain `Intermediate · ~7h`
**Modules**
- The Cyber Kill Chain and MITRE ATT&CK
- Reconnaissance and OSINT
- Scanning and enumeration (`nmap`, service discovery)
- Exploitation fundamentals (using Metasploit responsibly in a lab)
- Post-exploitation, pivoting, and privilege escalation (concepts)
- Reporting your findings

**You'll be able to:** run a structured, ethical penetration test against a lab network.
**Tools:** `nmap`, Metasploit, a vulnerable lab (e.g., Metasploitable, HTB).
**Practice:** Compromise a deliberately vulnerable lab box and document the path.

#### Course 6.4 Defensive Security & Blue Team `Intermediate · ~6h`
**Modules**
- System and network hardening
- Logging, monitoring, and SIEM (Splunk/ELK overview)
- Detection engineering basics and writing alerts
- Endpoint protection and EDR concepts
- Threat intelligence fundamentals

**You'll be able to:** detect and respond to activity a red team would generate.
**Practice:** Build a detection for a simulated attack in a SIEM.

#### Course 6.5 — Digital Forensics & Incident Response `Intermediate · ~5h`
**Modules**
- The incident response lifecycle
- Evidence handling and chain of custody
- Disk, memory, and network forensics basics
- Building an incident timeline
- Writing an incident report

**You'll be able to:** investigate an incident methodically and preserve evidence.
**Practice:** Analyze a memory/disk image and reconstruct what happened.

### Stage 3 — Advanced

#### Course 6.6 — Red Teaming & Adversary Emulation `Advanced · ~7h`
**Modules**
- Red team vs pentest: goals and rules of engagement
- Emulating real adversary TTPs (MITRE ATT&CK mapping)
- Command-and-control concepts and OPSEC
- Defense evasion at a conceptual level
- Purple teaming: closing the loop with defenders
- Engagement planning and reporting

**You'll be able to:** plan and reason about a goal-based adversary emulation, ethically.
**Practice:** Design a rules-of-engagement doc and an ATT&CK-mapped test plan for a lab.

#### Course 6.7 — Cloud Security `Advanced · ~6h`
**Modules**
- Shared responsibility model
- Identity and access management in the cloud
- Common cloud misconfigurations (storage, IAM, networking)
- Container and Kubernetes security basics
- Cloud logging, monitoring, and posture management

**You'll be able to:** assess and harden a basic cloud environment.
**Practice:** Audit a lab cloud account for misconfigurations.

#### Course 6.8 — GRC, Risk & Career `Advanced · ~4h`
**Modules**
- Governance, risk, and compliance overview
- Major frameworks (ISO 27001, NIST CSF, SOC 2)
- Risk assessment and management
- Building a security program
- Certifications and career roadmaps (Security+ → PNPT/OSCP → specialization)

**You'll be able to:** connect technical work to business risk and plan your career.
**Practice:** Draft a lightweight risk register for a small organization.

### ★ Capstone — Full Security Engagement
Run an end-to-end engagement on a lab network: recon, exploitation, and post-exploitation from the offensive side; then switch hats to detect the activity, respond, and write both a **penetration test report** and an **incident report**.

---
---

## Practice platforms & resources

Free places to apply every track (use only what you're authorized to):

- **General / CTF:** picoCTF, TryHackMe, Hack The Box, OverTheWire
- **Web:** PortSwigger Web Security Academy, OWASP Juice Shop, DVWA
- **Exploit dev / pwn:** pwn.college, ROP Emporium, exploit.education
- **Web3:** Cyfrin Updraft, Ethernaut, Damn Vulnerable DeFi
- **Blue team / forensics:** CyberDefenders, Blue Team Labs Online
- **Linux / networking:** OverTheWire (Bandit), your own VM lab

---

## How this maps to Hexploit-Labs

Inside the platform, this curriculum becomes real content:

- Each **domain** above = one **Roadmap** (Admin → Roadmaps).
- Each **course** = one **Course**, with its **Difficulty** and **Est. hours** set from the tables.
- Each **module** = one **Lesson** (YouTube video + downloadable resources + optional command block + optional lab/CTF link).
- Each course's **Practice** = the lesson's **"Practice this"** lab link; each **Capstone** can be its own final lesson or a bonus course.
- Add a **quiz** per course to gate understanding, and chain courses into the **combined career paths** above using Roadmaps.

Suggested build order for the platform itself: **Linux → Networking → Web Security → Exploit Development → Web3 → Cyber Security**, mirroring the dependency map.

---

## A note on ethics

Every offensive technique in this curriculum is taught for **defensive understanding, authorized testing, security research, and CTFs**. Only test systems you own or have **explicit written permission** to test. Unauthorized access is illegal. Learn to break things so you can build and defend them better.

---

*Hexploit-Labs — free offensive-security training. Contributions and course suggestions welcome.*
