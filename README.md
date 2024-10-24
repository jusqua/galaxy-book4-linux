# Samsung Galaxy Book4 for Linux

Running Fedora 40 on my Samsung Galaxy Book4 ([NP750XGJ-KG2BR](https://www.samsung.com/br/computers/samsung-book/galaxy-book4-15-6-inch-i5-16gb-512gb-np750xgj-kg2br/)).

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
