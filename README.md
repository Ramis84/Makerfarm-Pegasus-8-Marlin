# Marlin 2.0 on Makerfarm Pegasus 8''

## Summary
1. Original hardware from Makerfarm:
    1. RAMPS 1.4
    1. MK1 heat bed
    1. E3Dv6 Hotend
    1. E3D Titan Extruder
    1. ACME Lead Screws (8mm trapezoidal lead screw) with DRV8825 stepper drivers for Z-motors
1. Upgraded hardware:
    1. Quieter stepper drivers for X, Y, E motors: TMC2208
    1. BLTouch V3.1 for Auto Bed Leveling (replaces Z endstop)
    1. Extruder auto fan using pin on RAMPS board (https://www.youtube.com/watch?v=qEXKQUJnbAU)
    1. Custom Titan mount (https://www.thingiverse.com/thing:4506348)
    1. Better Lead Screw mount (using 2x 8mm 4-start lead screw nuts), to regain som print area lost by badly designed X idler mount (https://www.thingiverse.com/thing:1989637)
    1. 5015 Radial blower print fan (https://www.thingiverse.com/thing:2175956)
  
## Marlin settings
1. TMC2208 drivers running in standalone legacy mode (StealthChop)
1. S-curve acceleration
1. Bilinear Auto Bed Leveling (2 * 2 probe points)
1. Software Min Z endstop (to prevent mistake of ramming nozzle into bed)
1. Z safe homing
1. Save to eeprom
1. LCD bed leveling
1. Enable M73 progress GCODE
1. Enable FAST_PWM_FAN, to remove print fan noice when running on low speed

## Note to self for upgrading
```
git remote -v (should list upstream branch "MarlinFirmware/Marlin")
git fetch upstream
git merge upstream/2.0.x
```

## License

Marlin is published under the [GPL license](/LICENSE) because we believe in open development. The GPL comes with both rights and obligations. Whether you use Marlin firmware as the driver for your open or closed-source product, you must keep Marlin open, and you must provide your compatible Marlin source code to end users upon request. The most straightforward way to comply with the Marlin license is to make a fork of Marlin on Github, perform your modifications, and direct users to your modified fork.

While we can't prevent the use of this code in products (3D printers, CNC, etc.) that are closed source or crippled by a patent, we would prefer that you choose another firmware or, better yet, make your own.
