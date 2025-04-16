# Samsung Galaxy Book4 for Linux

This repository merge information about my Linux usage with Samsung Galaxy Book4 (Base model [NP750XGJ-KG2BR](https://www.samsung.com/br/computers/samsung-book/galaxy-book4-15-6-inch-i5-16gb-512gb-np750xgj-kg2br/buy)).

I'm using Fedora 42 KDE Edition to daily driver, and perform test and benchmarks.

> [!IMPORTANT]
> If you find another issues or solution for these problems, let me know! Contributions are welcome!

## Known issues

### Really slow charging / Slow wake from sleep

#### Description
- AC adapter provides small charging rate while in Linux;
- Pluging AC adapter before Linux boot provides the "correct" charge rate. 

#### Solution
1. Firmware update through Windows Update; or
2. Add kernel parameters to change ACPI behavior (see [related discussion](https://github.com/jusqua/galaxy-book4-linux/discussions/2)).

---

### Fn hotkeys and platform-specific settings doesn't works

#### Description
- Some Fn keys are related to the platform:
  - `Fn + Esc` for Open Samsung Assistance;
  - `Fn + F1` for Open Settings App;
  - `Fn + F5` for Enable/Disable Touchpad;
  - `Fn + F10` for Enable/Disable Mic and Webcam;
  - `Fn + F11` for Change Platform Power Profiles;
  - `Fn + F12` for Enable/Disable Fn Key Lock.
- Cannot read or control fans.
- Cannot change battery charge end threshold, aka Battery Protection.

#### Solution
- Firmware update through Windows Update; and/or
  1. Use kernel version >= 6.15; or
  2. Build and install [samsung-galaxybook-extras](https://github.com/joshuagrisham/samsung-galaxybook-extras) kernel module against kernel version < 6.15;

---

### Built-in speakers volume are too quiet

#### Description
- Built-in speaker is inaudible when volume is lower than 10%.

#### Thoughts
- The same issue occurs when using a Samsung USB-C Earphone in any device, both speakers and earphone are manufatured by AKG.
- Maybe [this discussion](https://github.com/thesofproject/linux/issues/4055) is useful to find a way to solve the problem.

---

### Built-in monitor screen brightness changes struggles

#### Description
- When the screen brightness change hotkey is pressed the screen brightness takes a second to apply.
- If the hotkey is kept pressed the brightness screen intensity jumps to a higher intensity instead of increasing gradually.

#### Thoughts
- It works normally when using an external keyboard shortcut to change the screen brightness.

---

### Battery disconnects from AC when fully charged

#### Description
- While the AC adapter is plugged and the battery is already full, intermittently, the AC disconnects from battery than reconnects again.

#### Thoughts
- This occurs since firmware update `P07CFP.020.250208.HQ`.

---

### Intel Xe Iris have ~50% less GPU performance compared to Windows 11

#### Benchmark
- [Geekbench 6](https://www.geekbench.com/) Windows 11 Pro 23h2 vs Fedora 41 KDE Plasma:
  - [Vulkan](https://browser.geekbench.com/v6/compute/compare/3030419?baseline=3031886)
  - [OpenCL](https://browser.geekbench.com/v6/compute/compare/3030439?baseline=3031877)

#### Description
- GPU intensive apps struggles to open and run (e.g. games, video editor);
- Parallel computing display lower score.

#### Thoughts
- Xe Iris kernel modules still in early development and the Linux kernel still using i915 kernel module by default; and/or
- The Samsung custom firmware makes a lot of changes to perform better on Windows, and not perform well on Linux, i.e. no platform support yet.
