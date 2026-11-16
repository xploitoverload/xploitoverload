<div align="center">

<img width="100%" src="https://capsule-render.vercel.app/api?type=waving&color=0:0a0a0a,50:990000,100:e50914&height=250&section=header&text=Kalpesh%20Solanki&fontSize=52&fontColor=ffffff&animation=twinkling&fontAlignY=38&desc=Linux%20Kernel%20Security%20%7C%20Ring%200%20Researcher%20%7C%20Exploit%20Hunter&descSize=18&descAlignY=55&descAlign=50"/>

<br/>

<p align="center">
  <a href="https://github.com/xploitoverload">
    <img src="https://img.shields.io/badge/GitHub-xploitoverload-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub"/>
  </a>
  <a href="https://linkedin.com/in/kalpesh11111">
    <img src="https://img.shields.io/badge/LinkedIn-Kalpesh_Solanki-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn"/>
  </a>
  <a href="https://instagram.com/_kalpesh.solanki_">
    <img src="https://img.shields.io/badge/Instagram-_kalpesh.solanki_-E4405F?style=for-the-badge&logo=instagram&logoColor=white" alt="Instagram"/>
  </a>
  <a href="mailto:skalpesh942@gmail.com">
    <img src="https://img.shields.io/badge/Email-skalpesh942@gmail.com-D14836?style=for-the-badge&logo=gmail&logoColor=white" alt="Email"/>
  </a>
  <a href="https://github.com/xploitoverload/upstream-contributions-tracker">
    <img src="https://img.shields.io/badge/Upstream_Tracker-8_Patches-E50914?style=for-the-badge&logo=git&logoColor=white" alt="Upstream Tracker"/>
  </a>
</p>

<p align="center">
  <img src="https://readme-typing-svg.herokuapp.com?font=Fira+Code&weight=600&size=22&duration=3000&pause=1000&color=E50914&center=true&vCenter=true&width=650&lines=Operating+in+Ring+0+Supervisor+Mode;Linux+Kernel+Security+%26+Vulnerability+Research;Kernel+CNA+CVE-2026-97601;Audit+the+seams.+Hunt+the+races.+Hack+The+Planet!" alt="Typing SVG" />
</p>

</div>

<br/>

<h2><font color="#e50914" size="6">#</font> Kernel Identity & Architecture</h2>

```c
/* Ring 0 Linux Kernel Security Researcher */
static const struct security_researcher kalpesh = {
    .handle        = "xploitoverload",
    .real_name     = "Kalpesh Solanki",
    .privilege     = RING_0_SUPERVISOR,
    .subsystems    = { "netdev", "rtw88", "bonding", "tun/tap", "ieee802154", "mctp" },
    .cve_track     = { "CVE-2026-97601", "8 Upstream Kernel Contributions" },
    .arsenal       = { "Concurrency Exploits", "UAF/Race Elimination", "Device Drivers", "QEMU/GDB" },
    .philosophy    = "Audit the seams. Dissect the protocol. Hack the planet."
};
```

<br/>

<h2><font color="#e50914" size="6">#</font> Upstream Kernel Contributions</h2>

<div align="center">

[![Linux Kernel](https://img.shields.io/badge/Linux_Kernel-Mainline_&_Netdev-blue?logo=linux&logoColor=white)](https://git.kernel.org)
[![CVE-2026-97601](https://img.shields.io/badge/CVE-2026--97601-red?logo=security)](https://git.kernel.org/netdev/net/c/968f2b94a596)
[![Upstream Tracker](https://img.shields.io/badge/Upstream_Tracker-8_Contributions-success?logo=github)](https://github.com/xploitoverload/upstream-contributions-tracker)
[![Contributing Portfolio](https://img.shields.io/badge/Full_Portfolio-CONTRIBUTING.md-orange?logo=git)](CONTRIBUTING.md)

</div>

> 🌟 **[👉 Click here to explore the full Upstream Contributions Portfolio & Technical Case Studies in CONTRIBUTING.md](CONTRIBUTING.md)**  
> 📋 *Or click the **Contributing** tab in the repository navigation bar to view full patch breakdowns, senior maintainer endorsements, and vulnerability analyses.*  
> 🧠 **[👉 Read the Ring 0 Systems & Kernel Interview Playbook](https://github.com/xploitoverload/upstream-contributions-tracker/blob/main/INTERVIEW_PREP_RING0.md)**

```
┌────────────────────────────────────────────────────────────────────────────────────────┐
│                        UPSTREAM LINUX KERNEL & SYSTEMS TRACK RECORD                    │
├───────────────────┬─────────────────────────────────────────────────┬──────────────────┤
│ Category          │ Scope & Subsystems                              │ Status           │
├───────────────────┼─────────────────────────────────────────────────┼──────────────────┤
│ Kernel Security   │ netdev, tun, ieee802154 (CVE-2026-97601)        │ MERGED 🎉        │
│ Wireless Drivers  │ rtw88 (PCIe ASPM DMI Quirk & Recovery Series)   │ COMMITTED / APPR │
│ Core Networking   │ drivers/net/bonding (Link Invariant Guard v2)   │ FORMALLY APPR 🚀 │
│ Protocol Hardening│ drivers/net/tun & net/mctp (SKB Panic On Warn)  │ ACTIVE REVIEW    │
│ Desktop Security  │ xfce4-screensaver (Unlock Bypass & BadWindow)   │ MERGED 🎉        │
└───────────────────┴─────────────────────────────────────────────────┴──────────────────┘
```

> 📌 *Detailed root-cause whitepapers, standalone QEMU reproduction sandboxes, and verification logs are maintained in my [**upstream-contributions-tracker**](https://github.com/xploitoverload/upstream-contributions-tracker).*

<br/>

<h2><font color="#e50914" size="6">#</font> Ring 0 Systems Domain Expertise</h2>

```
╔═══════════════════════════════════════════════════════════════════════════════════════════════════════╗
║                                LINUX KERNEL & RING 0 DOMAIN EXPERTISE                                 ║
╠══════════════════════════╦════════════════════════════════════════════════════════════════════════════╣
║ Subsystems               ║ netdev, mac80211, cfg80211, rtw88, bonding, tun/tap, ieee802154, mctp      ║
║ Concurrency & Locking    ║ Spinlocks (irqsave), Mutexes, RCU, Lockdep, Memory Barriers, Workqueues    ║
║ Execution Contexts       ║ Atomic Context vs Process Context, Top-Half HardIRQs, Bottom-Half SoftIRQs ║
║ Memory & Hardware        ║ SLUB Allocator, GFP Flags (ATOMIC/KERNEL), DMA Coherency, MMIO, PCIe ASPM  ║
║ Kernel Triage & Tooling  ║ QEMU/KVM + GDB, ftrace, bpftrace, dyndbg, KASAN, UBSAN, Syzbot Repro Triage║
║ Security & Exploitation  ║ User Namespaces (CLONE_NEWUSER), ioctl Auditing, Race Exploits, eBPF       ║
╚══════════════════════════╩════════════════════════════════════════════════════════════════════════════╝
```

<br/>

<h2><font color="#e50914" size="6">#</font> Tech Arsenal & Tools</h2>

<div align="center">

<table>
<tr>
<td align="center" width="33%">

**Systems & Low-Level**<br/><br/>
<img src="https://skillicons.dev/icons?i=c,cpp,linux,bash&theme=dark" />

</td>
<td align="center" width="33%">

**Security & Research**<br/><br/>
<img src="https://skillicons.dev/icons?i=python,git,github,regex&theme=dark" />

</td>
<td align="center" width="33%">

**Software & Frameworks**<br/><br/>
<img src="https://skillicons.dev/icons?i=pytorch,java,js,html&theme=dark" />

</td>
</tr>
</table>

</div>

<br/>

<h2><font color="#e50914" size="6">#</font> Open Source Analytics & Metrics</h2>

<div align="center">

<a href="https://next.ossinsight.io/widgets/official/compose-user-dashboard-stats?user_id=184857390" target="_blank" style="display: block" align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://next.ossinsight.io/widgets/official/compose-user-dashboard-stats/thumbnail.png?user_id=184857390&image_size=auto&color_scheme=dark" width="770" height="auto">
    <img alt="Dashboard stats of @xploitoverload" src="https://next.ossinsight.io/widgets/official/compose-user-dashboard-stats/thumbnail.png?user_id=184857390&image_size=auto&color_scheme=light" width="770" height="auto">
  </picture>
</a>

</div>

<br/>

<h2><font color="#e50914" size="6">#</font> Contribution Activity</h2>

<div align="center">

<img src="https://github-readme-activity-graph.vercel.app/graph?username=xploitoverload&bg_color=0a0a0a&color=e50914&line=00f0ff&point=e50914&area=true&hide_border=true" width="100%"/>

<br/><br/>

<a href="https://streak-stats.demolab.com/?user=xploitoverload">
  <img src="https://streak-stats.demolab.com/?user=xploitoverload&theme=radical&hide_border=true&border_radius=8&background=0a0a0a" alt="GitHub Streak" />
</a>

</div>

<br/>

<h2><font color="#e50914" size="6">#</font> Contribution Matrix</h2>

<div align="center">

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/xploitoverload/snk/output/github-contribution-grid-snake-dark.svg">
  <img alt="github contribution grid snake animation" src="https://raw.githubusercontent.com/xploitoverload/snk/output/github-contribution-grid-snake-dark.svg">
</picture>

</div>

<br/>

<div align="center">

<p align="center">
  <img src="https://komarev.com/ghpvc/?username=xploitoverload&label=Profile%20Views&color=e50914&style=flat-square" alt="xploitoverload" />
</p>

<img width="100%" src="https://capsule-render.vercel.app/api?type=waving&color=0:e50914,50:990000,100:0a0a0a&height=140&section=footer&animation=twinkling"/>

</div>
