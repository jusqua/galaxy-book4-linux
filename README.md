# Samsung Galaxy Book4 workarounds for Linux

Running Fedora 40 on my Samsung Galaxy Book4 (NP750XGJ-KG2BR).

## Known issues

- Volume below 10% is inaudible and at 100% isn't high enough (probably Dolby Atmos module fault, can be workarounded by increasing the volume over 100%)
- Dedicated buttons does not works (probably ACPI dedicated buttons, can be rebinded in some useful way)
- When integrated monitor brightness changes the system struggles
- Intel Xe Iris not seem to be activated, in the setting shows in graphics section **Intel® Graphics (RPL-U)** instead of **Intel® Iris® Xe Graphics**, maybe not related but can be associated with Xe Iris "poor implementation"?
- Slow charging, needs to plug charger before boot to be able to fast charge
- Sometimes boot slowly accusing `ACPI Error` and in boot logs
- Slow wakeup from sleep, takes from 1s to 20s to wakeup
