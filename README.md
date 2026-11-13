<div align="center">
  <img src="https://readme-typing-svg.herokuapp.com?font=Roboto+Mono&size=30&duration=4000&pause=1000&color=FF0000&center=true&vCenter=true&width=600&lines=Hack+The+Planet!" alt="Typing SVG" />
</div>

# <p align="center"> [𝓗𝓮𝓵𝓵𝓸 ^_^](#-%F0%9D%93%97%F0%9D%93%AE%F0%9D%93%B5%F0%9D%93%B5%F0%9D%93%B8-_-) <img width="45" height="45" src="https://user-images.githubusercontent.com/118815227/218338072-ea477aa8-1374-4e2d-8dfd-dd8cc4e45656.gif"></p>

<img src="https://user-images.githubusercontent.com/118815227/218338455-6034502f-e9dd-42e8-ba74-608fb41cdbaa.gif"> 𝚝𝚘 𝚖𝚢 𝙶𝚒𝚝𝙷𝚞𝚋 𝚙𝚛𝚘𝚏𝚒𝚕𝚎
<br>
## [A̵̺̼̠̫͚͙͎͇͛̈́͑̌b̸̛̮̗̺͉̰̃͌́̏̑̇͋͝͝ò̴̡̪͖̻̱̫͇̪̍͘ų̵͚͙͉̳̱̯̳̩͚͑̋̌̂͛̽̍̌̒̕ẗ̵͖͔̳̜̬̝̝͉̪ ̸̻̦̣͓̪͉̳͖̜̺̉̔̓͌͂͌͛̎́ṃ̷̏̾̓ē̸͇͖̳̲͆̽̾̎̈́̊ ](#a%CC%B5%CD%9B%CD%84%CD%91%CC%8C%CC%BA%CC%BC%CC%A0%CC%AB%CD%9A%CD%99%CD%8E%CD%87b%CC%B8%CC%83%CD%8C%CD%9D%CD%81%CD%9D%CC%8F%CC%91%CC%87%CD%8B%CC%9B%CC%AE%CC%97%CC%BA%CD%89%CC%B0o%CC%B4%CD%80%CD%98%CC%8D%CC%AA%CD%96%CC%A1%CC%BB%CC%B1%CC%AB%CD%87%CC%AAu%CC%B5%CC%95%CD%91%CC%8B%CC%8C%CC%82%CD%9B%CC%BD%CC%8D%CC%8C%CC%92%CD%9A%CD%99%CD%89%CC%B3%CC%A8%CC%B1%CC%AF%CC%B3%CC%A9%CD%9At%CC%B5%CC%88%CD%96%CD%94%CC%B3%CC%9C%CC%AC%CC%9D%CC%9D%CD%89%CC%AA-%CC%B8%CC%89%CC%94%CD%83%CD%8C%CD%82%CD%8C%CD%9B%CC%8E%CD%81%CC%BB%CC%A6%CC%A3%CD%93%CC%AA%CD%89%CC%B3%CD%96%CC%9C%CC%BAm%CC%B7%CC%8F%CC%BE%CD%83%CC%A3e%CC%B8%CC%84%CD%86%CC%BD%CC%BE%CC%8E%CD%84%CC%8A%CD%87%CD%96%CC%B3%CC%B2-) <img src="images/mooshi.gif" width=""/>
<br>

<img align="centre" src="images/file_000000002fcc8208a2ea8a866fe8eaba.png" />

<!-- <div align="center"> -->
<h1 align="center">I'm Kalpesh Solanki (xploitoverload)</h1>
<h3 align="center">Cyber Security Researcher | Hacker | Red Teamer | CTFer | Developer | EC Engineer |<br/> Operating in Ring 0 • Linux Kernel Security • Build the universe with me</h3>
  
---

## 🛡️ Upstream Linux Kernel & Systems Contributions

> 🌟 **[👉 Click here to read the complete technical breakdown & maintainer endorsements in CONTRIBUTIONS.md](CONTRIBUTIONS.md)**  
> 🧠 **[👉 Click here to read the Ring 0 Systems & Kernel Interview Playbook](https://github.com/xploitoverload/upstream-contributions-tracker/blob/main/INTERVIEW_PREP_RING0.md)**

| Subsystem / Project | Technical Impact & Vulnerability Architecture | Senior Maintainers & Reviewers | Artifacts & Proof |
| :--- | :--- | :--- | :--- |
| **Linux Kernel**<br>Core Networking (`netdev`)<br>`drivers/net/tun` & `net/ieee802154` | **Unprivileged Supervisor NULL Dereference & Mutex Deadlock Fix**<br>Prevented container/namespace `CAP_NET_ADMIN` users from triggering supervisor crashes and `rtnl_lock` deadlocks via `TUNSETLINK` link type tampering. | **Jakub Kicinski** (`kuba@kernel.org`)<br>**Willem de Bruijn** (`willemb@google.com`) | **Commit:** [`968f2b94a596`](https://git.kernel.org/netdev/net/c/968f2b94a596)<br>**Syzbot:** [`9ea34da5ca6100593c90`](https://syzkaller.appspot.com/bug?extid=9ea34da5ca6100593c90)<br>[Whitepaper & Analysis](https://github.com/xploitoverload/upstream-contributions-tracker/tree/main/03-ieee802154-unprivileged-null-deref-fix) |
| **Linux Kernel**<br>Wireless Driver (`rtw88`)<br>`drivers/net/wireless/realtek/rtw88` | **HP Laptop 15s-fr5xxx PCIe ASPM L1/L1.2 & Deep LPS DMI Quirk**<br>Resolved microcontroller link desynchronization causing complete Wi-Fi lockup on RTL8822CE upon idling. | **Ping-Ke Shih** (`pkshih@realtek.com`) | **Commit:** [`04c99841872`](https://git.kernel.org/pub/scm/linux/kernel/git/pkshih/rtw.git/commit/?id=04c9984187228904f222681661c50db3f0c50b71)<br>[Analysis](https://github.com/xploitoverload/upstream-contributions-tracker/blob/main/02-rtw88-linux-kernel-wifi-fix/TECHNICAL_ANALYSIS.md) |
| **Linux Kernel**<br>Wireless Stack (`mac80211` / `rtw88`) | **Firmware Recovery & State Machine Concurrency Series**<br>• Fixed permanent deadlock of `RTW_FLAG_RESTARTING` on teardown.<br>• Eliminated UAF, double-free, and NULL dereference races in `rtw_sta_remove()`.<br>• Introduced 3-timeout consecutive LPS hang threshold on PCIe gated by `FW_FEATURE_LPS_C2H`. | **Luka Gejak** (`luka.gejak@linux.dev`)<br>**Ping-Ke Shih** (`pkshih@realtek.com`)<br>**Zong-Zhe Yang** (`kevin_yang@realtek.com`) | [**Lore Archive (v6)**](https://lore.kernel.org/linux-wireless/20261113034704.21283-1-skalpesh942@gmail.com/)<br>[**Patchwork**](https://patchwork.kernel.org/project/linux-wireless/list/?submitter=Kalpesh+Solanki)<br>[Analysis & Patches](https://github.com/xploitoverload/upstream-contributions-tracker/tree/main/02-rtw88-linux-kernel-wifi-fix) |
| **Linux Kernel**<br>Link Aggregation (`bonding`)<br>`drivers/net/bonding` | **IEEE 802.15.4 & 6LoWPAN Device Enslavement Guard**<br>Enforced link-layer encapsulation invariants in `bond_enslave()`, preventing kernel memory corruption and invalid hardware address dereferences. | **Oliver Hartkopp** (`socketcan@hartkopp.net`)<br>**Jay Vosburgh** (`jv@jvosburgh.net`) | [**Lore Archive**](https://lore.kernel.org/netdev/20261108143224.489110-1-skalpesh942@gmail.com/) |
| **Linux Kernel**<br>Core Networking (`tun` / `mctp`) | **Unprivileged DoS via SKB Control Block Panic Fix**<br>Disallowed `ARPHRD_MCTP` link type configuration via `TUNSETLINK`, preventing unprivileged users from triggering `panic_on_warn` local system crash. | **Willem de Bruijn** (`willemb@google.com`)<br>**Jeremy Kerr** (`jk@ozlabs.org`) | [**Lore Archive**](https://lore.kernel.org/netdev/20261108143431.489150-1-skalpesh942@gmail.com/) |
| **Xfce Desktop**<br>Desktop Security<br>`xfce4-screensaver` | **Session Unlock Security Bypass & X11 `BadWindow` Crash**<br>Fixed authentication prompt timeout race condition where an unhandled X11 protocol error crashed the screensaver daemon, unlocking the session without credentials. | **Gaël Bonithon** (`@Tamaranch`) | [**GitLab MR !67**](https://gitlab.xfce.org/apps/xfce4-screensaver/-/merge_requests/67)<br>[**Commit**](https://github.com/xfce-mirror/xfce4-screensaver/commit/bcacc87794192c62fdc2bf5b63f6c3105f9b3eae)<br>[Analysis](https://github.com/xploitoverload/upstream-contributions-tracker/tree/main/01-xfce4-screensaver-security-fix) |

> 📌 *Detailed root-cause whitepapers, standalone QEMU reproduction sandboxes, and verification logs are maintained in my [**upstream-contributions-tracker**](https://github.com/xploitoverload/upstream-contributions-tracker).*

---

## 🔬 Ring 0 & Linux Systems Architecture Arsenal

```
╔═══════════════════════════════════════════════════════════════════════════════════════════════════════╗
║                                LINUX KERNEL & RING 0 DOMAIN EXPERTISE                                ║
╠══════════════════════════╦════════════════════════════════════════════════════════════════════════════╣
║ Subsystems               ║ netdev, mac80211, cfg80211, rtw88, bonding, tun/tap, ieee802154, mctp       ║
║ Concurrency & Locking    ║ Spinlocks (irqsave), Mutexes, RCU, Lockdep, Memory Barriers, Workqueues    ║
║ Execution Contexts       ║ Atomic Context vs Process Context, Top-Half HardIRQs, Bottom-Half SoftIRQs ║
║ Memory & Hardware        ║ SLUB Allocator, GFP Flags (ATOMIC/KERNEL), DMA Coherency, MMIO, PCIe ASPM ║
║ Kernel Triage & Tooling  ║ QEMU/KVM + GDB, ftrace, bpftrace, dyndbg, KASAN, UBSAN, Syzbot Repro Triage ║
║ Security & Exploitation  ║ User Namespaces (CLONE_NEWUSER), ioctl Auditing, Race Exploits, eBPF       ║
╚══════════════════════════╩════════════════════════════════════════════════════════════════════════════╝
```

### ⚙️ Core Technical Capabilities
* **Kernel Concurrency & Race Condition Elimination:** Designing lockless and synchronized teardown flows across interrupt bottom-halves, asynchronous workqueues (`cancel_work_sync`), and state machines to eliminate Use-After-Free (UAF) and deadlocks.
* **Privilege Boundary & Container Attack Surface Auditing:** Identifying and neutralizing privilege escalation primitives accessible to unprivileged namespaces via virtual device ioctls (`TUNSETLINK`).
* **Hardware-Driver Interfacing & Microcontroller Firmware Quirks:** Decoding PCIe low-power states (ASPM L1/L1.2, Deep LPS), ACPI/DMI tables, and register polling state machines to recover frozen Wi-Fi hardware without host kernel panics.
* **Kernel Root-Cause Analysis Without GUI:** Rapid triage from serial netconsole logs, crash dumps, and Syzbot reproducers using GDB over QEMU/KVM, dynamic debugging (`dyndbg`), and sanitizers (`KASAN`, `Lockdep`).

---
  
### Hello world, build the universe with me!!!
![Snake](https://raw.githubusercontent.com/xploitoverload/snk/output/github-contribution-grid-snake-dark.svg?palette=github-dark)

<p align="centre"> <img src="https://komarev.com/ghpvc/?username=xploitoverload&label=Profile%20views&color=FF79BC&style=flat" alt="xploitoverload" /> </p>

<p align="left"> <a href="https://github.com/xploitoverload/github-profile-trophy"><img src="https://trophy.cx330.in/?username=xploitoverload&theme=light" alt="xploitoverload" /></a> </p>

<h3 align="left">Contact me:</h3>
<p align="left">
<a href="https://www.linkedin.com/in/kalpesh11111/" target="blank"><img align="center" src="images/icons/Social/linked-in-alt.svg" alt="loading" height="30" width="40" /></a> <a href="https://www.instagram.com/_kalpesh.solanki_" target="blank"><img align="center" src="images/icons/Social/instagram.svg" alt="loading" height="30" width="40" /></a>
</p>

<h3 align="left">Languages and Tools:</h3>
<p align="left"> 
  <a href="https://www.kernel.org/" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/linux/linux-original.svg" alt="linux" width="40" height="40"/> </a> 
  <a href="https://en.wikipedia.org/wiki/C_(programming_language)" target="_blank" rel="noreferrer"> <img src="images/icons/ProgrammingLanguages/c.svg" alt="c" width="40" height="40"/> </a> 
  <a href="https://git-scm.com/" target="_blank" rel="noreferrer"> <img src="https://www.vectorlogo.zone/logos/git-scm/git-scm-icon.svg" alt="git" width="40" height="40"/> </a> 
  <a href="https://www.gnu.org/software/bash/" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/bash/bash-original.svg" alt="bash" width="40" height="40"/> </a> 
  <a href="https://www.python.org" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/python/python-original.svg" alt="python" width="40" height="40"/> </a> 
  <a href="https://www.sourceware.org/gdb/" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/gdb/gdb-original.svg" alt="gdb" width="40" height="40"/> </a> 
  <a href="https://www.qemu.org/" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/qemu/qemu-original.svg" alt="qemu" width="40" height="40"/> </a> 
  <a href="https://www.wireshark.org/" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/wireshark/wireshark-original.svg" alt="wireshark" width="40" height="40"/> </a> 
  <a href="https://pytorch.org/" target="_blank" rel="noreferrer"> <img src="https://www.vectorlogo.zone/logos/pytorch/pytorch-icon.svg" alt="pytorch" width="40" height="40"/> </a> 
  <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/javascript/javascript-original.svg" alt="javascript" width="40" height="40"/> </a> 
  <a href="https://www.java.com" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/java/java-original.svg" alt="java" width="40" height="40"/> </a> 
</p>

## <p align="center"><img width="45" height="45" src="https://user-images.githubusercontent.com/118815227/218341043-776b003e-90ac-4e00-b6bf-1888c8b7864f.gif"> 𝚂𝚝𝚊𝚝𝚜 <img width="45" height="45" src="https://user-images.githubusercontent.com/118815227/218338229-2516daef-3362-43b5-948b-ea552af00ea2.gif"></p>

<p align="center">
  <a href="https://git.io/streak-stats">
    <img src="https://github-readme-streak-stats.herokuapp.com?user=xploitoverload&theme=microsoft-dark&hide_border=true&border_radius=5&locale=en&timezone=Asia%2FKolkata&date_format=j%20M%5B%20Y%5D" alt="GitHub Streak" />
  </a>
</p>
