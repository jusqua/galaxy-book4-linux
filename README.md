# Samsung Galaxy Book4 for Linux

Running Fedora 41 KDE Spin on my Samsung Galaxy Book4 ([NP750XGJ-KG2BR](https://www.samsung.com/br/computers/samsung-book/galaxy-book4-15-6-inch-i5-16gb-512gb-np750xgj-kg2br/buy)).

## Benchmarks

Those benchmarks are made with [Geekbench 6](https://www.geekbench.com/), comparing Windows 11 23h2 and Fedora 41 KDE Spin:
- [CPU](https://browser.geekbench.com/v6/cpu/compare/8575258?baseline=8570923)
- [Vulkan](https://browser.geekbench.com/v6/compute/compare/3030419?baseline=3031886)
- [OpenCL](https://browser.geekbench.com/v6/compute/compare/3030439?baseline=3031877)

Only Vulkan and OpenCL benchmarks are outliers results, probably because Xe Iris Kernel Modules still in early development and the Linux Kernel use i915 Kernel Module by default.
Even if `xe.force_probe=XXXX` and `i915.force_probe=!XXXX` are used as kernel parameters the results are worst than leave the default values.

The only way is wait for new kernel module update in Linux Kernel.

## Solutions

### Really slow charging / Almost no charging rate / Slow wake from sleep

The problem is solved when the firmware is updated. You can update to the latest version through Windows Update.

If no Windows is installed or firmware can't be updated, see issue [#1](https://github.com/jusqua/galaxy-book4-linux/issues/1) for a workaround.

### ACPI dedicated hotkeys (Power profiles, Allow recording and Fn Lock) and platform settings

The latest firmware is needed, so update through Windows Update.

See the [samsung-galaxybook-extras](https://github.com/joshuagrisham/samsung-galaxybook-extras) platform driver to enable platform hotkeys and settings.

## Known issues

### Built-in speakers volume are too quiet

The built-in speaker volume is almost inaudible when lower than 20%.

The same issue occurs when using a Samsung USB-C Earphone for some reason.

Maybe [this discussion](https://github.com/thesofproject/linux/issues/4055) is useful to find a way to solve the problem.

### Built-in monitor screen brightness changes struggles

When the screen brightness change hotkey is pressed the screen brightness takes a second to apply.
If the hotkey is kept pressed the brightness screen intensity jumps to a higher intensity instead of increasing gradually.
