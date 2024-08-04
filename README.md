# Samsung Galaxy Book4 workarounds for Linux

Running Fedora 40 on my Samsung Galaxy Book4 (NP750XGJ-KG2BR).

## Known issues

- Volume below 10% is inaudible and at 100% isn't high enough (probably Dolby Atmos module fault, can be workaround by increasing the volume over 100%)
- Dedicated buttons don't work (probably ACPI dedicated buttons, which can be rebinded in some useful way)
- When integrated monitor brightness changes the system struggles
- Intel Xe Iris does not seem to be activated, maybe unrelated but can be associated with Xe Iris's "poor implementation"?
- Slow charging, needs to plug charger before boot to be able to fast charge
- Sometimes boot slowly accusing `ACPI Error` and in boot logs
- Sometimes slow wake up from sleep, takes from 1s to 20s to wake up
