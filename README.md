# No-Name Android Radio Recon Guide

## 1. System Information

### Device Settings
- Record Build number/ID (examples: `YT9216B_00002_V001`, `8227L_demo`)
- Record Android version and Kernel version

### Hardware Info (CPU-Z or AIDA64)
- Identify SoC: Allwinner T3, Rockchip PX30, Mediatek 8227L, etc.
- Check RAM size
- Check storage type (NAND or eMMC)

## 2. Board Identification

Physical inspection of PCB silkscreen. Common board IDs:
- YT9216B, YT9217
- 8227L, AC8227L
- PX30, PX5, PX6

## 3. Firmware Details

### Service Codes
Dial `*#*#2846579#*#*` (varies by unit) for hidden menus.

### ADB Commands
Enable Developer Options → USB Debugging, then run:
```bash
adb shell getprop | grep ro.build
adb shell cat /proc/cpuinfo
```

## 4. Firmware Family Reference

| Platform | Tools | Resources |
|----------|-------|-----------|
| 8227L / YT9216B | SP Flash Tool | GitHub/XDA (ROMs, TWRP, root) |
| Allwinner T3/T8 | PhoenixSuit | 4PDA/XDA firmware dumps |
| Rockchip PX | Rockchip Batch Tool / AndroidTool | XDA forums |
| XYAuto / FYAuto | - | XYGala server (user: `Xyauto` / pass: `123456`) |

## 5. Backup Procedure

### Critical Partitions
```bash
adb pull /system
adb pull /vendor
adb pull /boot
```

### Full Dump
Use platform-specific tools:
- **Mediatek**: SP Flash Tool
- **Rockchip**: AndroidTool

## 6. Required Tools

- ADB + Fastboot
- SP Flash Tool (Mediatek)
- PhoenixSuit (Allwinner)
- Rockchip AndroidTool (PX series)
- USB OTG cable + USB stick
- UART adapter (recovery)

## 7. Research Resources

- XDA Android Head Unit forum
- GitHub search: `[Build_ID] site:github.com`
- Match Build ID to firmware packages exactly
