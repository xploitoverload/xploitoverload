# // UPSTREAM CONTRIBUTIONS & SYSTEMS SECURITY PORTFOLIO

**Author:** Kalpesh Solanki ([@xploitoverload](https://github.com/xploitoverload)) `<skalpesh942@gmail.com>`  
**Domain:** Linux Kernel Engineering • Ring 0 Security • Subsystem Concurrency & Race Conditions • Device Drivers • Vulnerability Research  
**Mailing Lists:** `linux-kernel@vger.kernel.org`, `netdev@vger.kernel.org`, `linux-wireless@vger.kernel.org`  
**Tracker Repository:** [`upstream-contributions-tracker`](https://github.com/xploitoverload/upstream-contributions-tracker)

---

## // 0x01: UPSTREAM CONTRIBUTIONS SCORECARD

Below is the verified scorecard of upstream contributions, bug fixes, security hardening, and driver enhancements submitted to the Linux kernel and core systems software:

| # | Subsystem / Project | Patch Title / Vulnerability Fixed | Key Reviewers & Maintainers | Upstream Status | Verification & Links |
| :-: | :--- | :--- | :--- | :--- | :--- |
| **1** | **Linux Kernel**<br>`drivers/net/tun`<br>`net/ieee802154` | **Unprivileged Supervisor NULL Dereference & Mutex Deadlock Fix**<br>Disallows setting `ARPHRD_IEEE802154` and `6LOWPAN` link types via `TUNSETLINK`. Prevents unprivileged users in user namespaces from crashing the kernel and permanently locking `rtnl_lock` / `genl_mutex`. | **Jakub Kicinski** (`kuba@kernel.org`)<br>**Willem de Bruijn** (`willemb@google.com`)<br>**Miquel Raynal** (`miquel.raynal@bootlin.com`) | `[MERGED // UPSTREAM]`<br>(Applied to `netdev/net.git`) | **Commit:** [`968f2b94a596`](https://git.kernel.org/netdev/net/c/968f2b94a596)<br>**CVE:** `CVE-2026-97601`<br>**Syzbot:** [`9ea34da5ca6100593c90`](https://syzkaller.appspot.com/bug?extid=9ea34da5ca6100593c90) |
| **2** | **Linux Kernel**<br>`drivers/net/wireless/realtek/rtw88` | **HP Laptop 15s-fr5xxx PCIe ASPM L1/L1.2 & Deep LPS DMI Quirk**<br>Resolves RTL8822CE microcontroller clock desynchronization and packet stall caused by aggressive PCIe ASPM power states. | **Ping-Ke Shih** (`pkshih@realtek.com`) | `[COMMITTED]`<br>(In `pkshih/rtw-next` $\rightarrow$ Mainline) | **Commit:** [`04c99841872`](https://git.kernel.org/pub/scm/linux/kernel/git/pkshih/rtw.git/commit/?id=04c9984187228904f222681661c50db3f0c50b71) |
| **3** | **Linux Kernel**<br>`drivers/net/wireless/realtek/rtw88` | **Firmware Recovery & State Machine Concurrency (v6 1/3)**<br>`wifi: rtw88: clear RTW_FLAG_RESTARTING on stop and start failure`<br>Eliminates permanent deadlock of the restart flag during interface shutdown or failed initialization. | **Luka Gejak** (`luka.gejak@linux.dev`)<br>**Ping-Ke Shih** (`pkshih@realtek.com`)<br>**Zong-Zhe Yang** (`kevin_yang@realtek.com`) | `[FORMALLY APPROVED]`<br>(`Reviewed-by: Luka Gejak`<br>Vetted by Realtek) | Queued for merge into `rtw-next` by Ping-Ke Shih<br>[**Lore Archive (v6)**](https://lore.kernel.org/linux-wireless/20261113034704.21283-1-skalpesh942@gmail.com/) |
| **4** | **Linux Kernel**<br>`drivers/net/wireless/realtek/rtw88` | **Station Teardown Idempotency & UAF Fix (v6 2/3)**<br>`wifi: rtw88: skip already reset station in rtw_sta_remove()`<br>Cancels `rc_work` workqueue before checking `!vif`, clears `si->use_cfg_mask = false`, and guarantees safe station removal during async firmware resets. | **Luka Gejak** (`luka.gejak@linux.dev`)<br>**Ping-Ke Shih** (`pkshih@realtek.com`) | `[FORMALLY APPROVED]`<br>(`Reviewed-by: Luka Gejak`) | Queued for merge into `rtw-next` by Ping-Ke Shih<br>[**Lore Archive (v6)**](https://lore.kernel.org/linux-wireless/20261113034704.21283-1-skalpesh942@gmail.com/) |
| **5** | **Linux Kernel**<br>`drivers/net/wireless/realtek/rtw88` | **Consecutive LPS Leave Hang Recovery (v6 3/3)**<br>`wifi: rtw88: ps: trigger firmware recovery only after consecutive LPS leave failures on PCI`<br>Enforces a 3-consecutive-timeout threshold (`RTW_PS_HANG_MAX_CNT = 3`) gated on `FW_FEATURE_LPS_C2H` for PCIe devices, eliminating USB/SDIO atomic scheduling panics. | **Luka Gejak** (`luka.gejak@linux.dev`)<br>**Ping-Ke Shih** (`pkshih@realtek.com`) | `[FORMALLY APPROVED]`<br>(`Reviewed-by: Luka Gejak`) | Queued for merge into `rtw-next` by Ping-Ke Shih<br>[**Lore Archive (v6)**](https://lore.kernel.org/linux-wireless/20261113034704.21283-1-skalpesh942@gmail.com/) |
| **6** | **Linux Kernel**<br>`drivers/net/bonding` | **Link-Layer Invariant Guard in `bond_enslave()` (v2)**<br>`bonding: reject IEEE 802.15.4 and 6LoWPAN devices in bond_enslave`<br>Prevents memory corruption and kernel NULL pointer dereference caused by enslaving non-Ethernet devices to a bonding master. | **Oliver Hartkopp** (`socketcan@hartkopp.net`)<br>**Hangbin Liu** (`liuhangbin@kylinos.cn`)<br>**Jay Vosburgh** (`jv@jvosburgh.net`) | `[FORMALLY APPROVED]`<br>(`Reviewed-by: Oliver Hartkopp`<br>`Reviewed-by: Hangbin Liu`) | Queued for merge into `net-next` by Jay Vosburgh / Jakub Kicinski<br>[**Lore Archive (v2)**](https://lore.kernel.org/netdev/20261112124840.12345-1-skalpesh942@gmail.com/) |
| **7** | **Linux Kernel**<br>`drivers/net/tun`<br>`net/mctp` | **Unprivileged DoS via SKB Magic Panic Fix**<br>`tun: disallow setting ARPHRD_MCTP link type via TUNSETLINK`<br>Disallows `ARPHRD_MCTP` on TUN interfaces, preventing unprivileged users from triggering `panic_on_warn` via `WARN_ON(cb->magic != 0x4d435450)`. | **Willem de Bruijn** (`willemb@google.com`)<br>**Jeremy Kerr** (`jk@ozlabs.org`) | `[UNDER ACTIVE REVIEW]` | Dispatched to `netdev@vger.kernel.org`<br>[**Lore Archive**](https://lore.kernel.org/netdev/20261108143431.489150-1-skalpesh942@gmail.com/) |
| **8** | **Xfce Desktop**<br>`xfce4-screensaver` | **Session Unlock Security Bypass & X11 `BadWindow` Crash**<br>Traps transient X11 protocol errors and synchronizes dialog teardown timers, closing a security bypass where a 60-second dialog timeout caused the screensaver daemon to crash and unlock the desktop without authentication. | **Gaël Bonithon** (`@Tamaranch`) | `[MERGED // UPSTREAM]`<br>(Release 4.20.3) | [**GitLab MR !67**](https://gitlab.xfce.org/apps/xfce4-screensaver/-/merge_requests/67)<br>Closes [Issue #204](https://gitlab.xfce.org/apps/xfce4-screensaver/-/work_items/204) |

---

## // 0x02: SENIOR KERNEL MAINTAINER NETWORK & CO-AUTHORS

Recognition, co-authoring, and formal sign-offs received from lead kernel maintainers across major subsystems:

```
┌────────────────────────────────────────────────────────────────────────────────────────┐
│                        SENIOR KERNEL & SYSTEMS MAINTAINER NETWORK                      │
├──────────────────────────┬─────────────────────────────────────┬───────────────────────┤
│ Maintainer               │ Affiliation / Role                  │ Action & Subsystem    │
├──────────────────────────┼─────────────────────────────────────┼───────────────────────┤
│ Jakub Kicinski           │ Meta / Netdev Co-Lead / TAB Member  │ Signed off & committed│
│ Willem de Bruijn         │ Google / Core Networking Maintainer │ Formal Reviewed-by    │
│ Miquel Raynal            │ Bootlin / IEEE 802.15.4 Co-Lead     │ Formal list consensus │
│ Oliver Hartkopp          │ SocketCAN Author & Maintainer       │ Formal Reviewed-by    │
│ Hangbin Liu              │ Red Hat / Kylin / Bonding Maintainer│ Formal Reviewed-by    │
│ Ping-Ke Shih             │ Realtek / Lead Linux Wi-Fi Driver   │ Tree merge & review   │
│ Jay Vosburgh             │ Linux Bonding Subsystem Lead        │ Net-next integration  │
│ Gaël Bonithon            │ Xfce Security & Screensaver Lead    │ Security MR merged    │
└──────────────────────────┴─────────────────────────────────────┴───────────────────────┘
```

---

## // 0x03: TECHNICAL VULNERABILITY ARCHITECTURE & ROOT CAUSES

### 1. Unprivileged Supervisor NULL Dereference & Netlink Deadlock (`CVE-2026-97601`)
* **Vulnerability Target:** `drivers/net/tun.c` and `net/ieee802154/nl-mac.c`
* **Discovery Context:** Syzbot ExtID `9ea34da5ca6100593c90`
* **Vulnerability Mechanics:**
  An unprivileged local user inside a user + network namespace (`CLONE_NEWUSER | CLONE_NEWNET`) opens `/dev/net/tun` and issues `ioctl(tun_fd, TUNSETLINK, ARPHRD_IEEE802154)`. The `tun` driver changed `dev->type` to `ARPHRD_IEEE802154` without initializing IEEE 802.15.4 private contexts (`dev->ieee802154_ptr` and `dev->ml_priv`).
  When any process subsequently requested a generic Netlink interface dump (`IEEE802154_LLSEC_LIST_KEY`), `ieee802154_llsec_dump_table()` blindly dereferenced `dev->ieee802154_ptr` as NULL while executing inside `genl_dumpit()`:
  ```
  [  112.451029] BUG: kernel NULL pointer dereference, address: 0000000000000010
  [  112.452103] RIP: 0010:ieee802154_llsec_dump_table+0x42/0x180
  ```
* **Impact:** Because the crash occurred while holding the global `genl_mutex`, the entire Netlink subsystem permanently deadlocked, rendering networking commands (`ip`, `ss`, `iw`) unresponsive across all namespaces.
* **Resolution:** Disallowed `ARPHRD_IEEE802154`, `ARPHRD_IEEE802154_MONITOR`, and `ARPHRD_6LOWPAN` link types in `drivers/net/tun.c:__tun_chr_ioctl()` (`Fixes: ff4cc3ac93e1`). Formally endorsed by WPAN maintainer Miquel Raynal and applied to mainline networking by Jakub Kicinski.

---

### 2. Realtek `rtw88` Microcontroller Sleep Recovery & Concurrency Architecture
* **Target:** `drivers/net/wireless/realtek/rtw88/`
* **Hardware:** RTL8822CE PCIe 802.11ac Wi-Fi Adapter (HP Laptop 15s-fr5xxx)
* **Root Cause & Race Conditions:**
  1. **ASPM Desync:** During PCIe Active State Power Management (ASPM L1.2) sleep transitions, the on-chip 8051/ARC microcontroller firmware lost PCIe bus reference clock synchronicity, causing silent frame drops and logging `firmware failed to leave lps state`.
  2. **Teardown Deadlock:** When hardware recovery failed, `RTW_FLAG_RESTARTING` remained set indefinitely, locking future open/close requests.
  3. **Concurrency UAF:** A race between asynchronous `__fw_recovery_work` and `rtw_ops_sta_remove()` caused Use-After-Free reads on rate control contexts (`rc_work`) and NULL pointer crashes in `rtw_rate_mask_cfg()`.
  4. **Atomic Scheduling Panic:** Running full recovery unconditionally tripped `BUG: scheduling while atomic` on USB and SDIO chips where bus transactions require sleepable mutexes while holding spinlocks.
* **Architectural Fix (v6 Series):**
  * Implemented DMI quirk entry in `pci.c` to disable ASPM on affected hardware (`04c99841872`).
  * Structured teardown idempotency in `rtw_sta_remove()`: synchronized workqueue cancellation prior to checking `!vif`, and reset `si->mask = NULL` / `si->use_cfg_mask = false`.
  * Added 3-consecutive-timeout hang threshold (`RTW_PS_HANG_MAX_CNT = 3`) gated strictly on `FW_FEATURE_LPS_C2H` and PCIe transport (`RTW_HCI_TYPE_PCIE`).

---

### 3. Bonding Subsystem Link-Layer Invariant & Type Confusion Enforcement
* **Target:** `drivers/net/bonding/bond_main.c`
* **Vulnerability Mechanics:**
  When enslaving a device into a Linux bonding interface via `bond_enslave()`, the driver assumed Ethernet encapsulation invariants. Enslaving down IEEE 802.15.4 or 6LoWPAN devices caused `bond_setup_by_slave()` to copy non-Ethernet link types to the bond master.
  As a result:
  1. Netlink queries treated the bond device as WPAN, crashing on unallocated `dev->ml_priv`.
  2. The 6LoWPAN notifier (`lowpan_event()`) identified the bond device by `ARPHRD_6LOWPAN` and cast `netdev_priv(dev)` to `struct lowpan_dev`, corrupting `struct bonding` memory on `NETDEV_DOWN`.
* **Resolution:** Extended `bond_enslave()` to reject `ARPHRD_IEEE802154`, `ARPHRD_IEEE802154_MONITOR`, and `ARPHRD_6LOWPAN`. Formally approved by Oliver Hartkopp and Hangbin Liu for `net-next`.

---

### 4. TUN / MCTP SKB Panic on Warn Fix
* **Target:** `drivers/net/tun.c` / `net/mctp/`
* **Vulnerability Mechanics:**
  Userspace processes configured TUN devices with `ARPHRD_MCTP` via `TUNSETLINK` and transmitted `ETH_P_MCTP` frames. In `mctp_pkttype_receive()`, incoming frames evaluated `dev->type == ARPHRD_MCTP` and called `mctp_cb(skb)`. Because TUN frames have cleared `skb->cb` buffers, this tripped:
  ```c
  WARN_ON(cb->magic != 0x4d435450);
  ```
  On kernels running with `panic_on_warn=1`, this unprivileged warning crashed the host system.
* **Resolution:** Enforced `-EINVAL` on `ARPHRD_MCTP` in `TUNSETLINK`.

---

### 5. Xfce Screensaver Session Unlock Bypass
* **Target:** `xfce4-screensaver/src/gs-manager.c`, `gs-listener-x11.c`
* **Vulnerability Mechanics:**
  During an active lock session, user keyboard input opened an authentication dialog. If left unattended for 60 seconds, the dialog timed out and was destroyed. Because X11 window destruction and pointer grab tracking operated asynchronously, an in-flight X11 event sent to the destroyed window generated an uncaught `BadWindow` protocol error. The X11 default error handler terminated the screensaver daemon process, dropping all grabs and exposing the unlocked desktop session to anyone with physical keyboard access.
* **Resolution:** Pushed and popped transient X11 error traps (`gdk_x11_display_error_trap_push/pop`) around dialog teardown and enforced synchronous lock engagement. Merged for Xfce 4.20.3.

---

## // 0x04: AUDITED IN-TREE MAINLINE FINDINGS

Two additional vulnerability and correctness fixes discovered during local code audits and verified against upstream Linux `master`:

```
1. fix/scm-pidfd-prepare-check (net/core/scm.c - ed432b95c00)
   • Bug: Missing error check on pidfd_prepare() failure in scm_pidfd_recv().
   • Impact: Copies negative error code into user cmsg buffer as a valid file descriptor
     without setting MSG_CTRUNC, leaving userspace with corrupt descriptor numbers.
   • Fix: Validate pidfd >= 0 before put_cmsg(), set MSG_CTRUNC, and abort cleanly.

2. fix/splice-uninitialized-ret (fs/splice.c - 30085f5f4af)
   • Bug: In iter_file_splice_write(), if len == 0 on entry, the write loop is skipped.
   • Impact: Function jumps directly to done and returns uninitialized stack variable ret,
     leaking stack garbage or reporting false byte counts.
   • Fix: Explicitly initialize ssize_t ret = 0.
```

---

## // 0x05: KERNEL PATCH DISPATCH PROTOCOLS

When submitting patches or collaborating alongside this work, the following strict kernel guidelines apply:

1. **Plain-Text Formatting Only:** All patches sent to `vger.kernel.org` mailing lists must strictly follow plain-text formatting (RFC 2822). HTML email is rejected by `mlmmj`.
2. **Commit Message Discipline:** Explain *why* the bug exists, provide the exact stack trace or Syzbot ExtID, explain *how* the fix resolves it without regressions, and cite the originating commit with `Fixes: <12-char-hash> ("commit title")`.
3. **Verification Before Submission:** Always run `scripts/checkpatch.pl --strict` and compile cleanly under `KCFLAGS="-Werror"` with `KASAN`, `UBSAN`, and `PROVE_LOCKING` enabled.
4. **Standalone Reproduction:** Where possible, author a minimal standalone C reproducer (using unprivileged namespaces) and verify in QEMU/KVM before submission.

---

## // 0x06: TELEMETRY & REPOSITORY NAVIGATION

* [**Upstream Contributions Tracker Repository**](https://github.com/xploitoverload/upstream-contributions-tracker)
* [**Ring 0 Systems & Kernel Interview Playbook**](https://github.com/xploitoverload/upstream-contributions-tracker/blob/main/INTERVIEW_PREP_RING0.md)
* [**Master Record Scorecard**](https://github.com/xploitoverload/upstream-contributions-tracker/blob/main/MASTER_RECORD.md)
