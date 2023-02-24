---
layout: default
title: Secure Boot-loader
parent: Hardware Security
grand_parent: RealSense
nav_order: 2
---

# Secure Boot-loader
This measure ensures data loaded from flash is verified on each reset.

**Benefit:** Only authorised code can run on the device's chip.

## Procedure
1. Most data is stored in flash. Flash access does not need to be protected from physical access in order for secure boot to function, 
because critical data is stored (non-software-accessible) in Efuses internal to the chip.
2. Efuses are used to store the secure bootloader key (in efuse BLOCK2), 
and also a single Efuse bit (ABS_DONE_0) is burned (written to 1) to permanently enable secure boot on the chip.
For more details on eFuses, see ESP32 Technical Reference Manual > eFuse Controller (eFuse) [PDF].
3. To understand the secure boot process, first familiarise yourself with the standard ESP-IDF boot process.
4. Both stages of the boot process (initial software bootloader load, and subsequent partition & app loading)
 are verified by the secure boot process, in a “chain of trust” relationship.


For proof of implementation, contact us

**Derived from:** [Documentation by Hardware provider: Espressif](https://docs.espressif.com/projects/esp-idf/en/latest/esp32/security/secure-boot-v1.html)
