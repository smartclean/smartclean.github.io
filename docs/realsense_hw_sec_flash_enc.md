---
layout: default
title: Flash encryption
parent: Hardware Security
grand_parent: RealSense
nav_order: 1
---

# Flash encryption
This measure encrypts the contents of the Device's external flash memory.

**Benefit:** Encrypted contents on the flash memory cannot be physically read out.

## Procedure
1. Once this feature is enabled, firmware is flashed as plaintext
2. Data is encrypted in place on the first boot. 

## More Details
With flash encryption enabled, the following types of data are encrypted by default:

1. Firmware bootloader
2. Partition Table
3. All “app” type partitions 
4. Other types of data can be encrypted conditionally:
   1. Any partition marked with the encrypted flag in the partition table.
   2. Secure Boot bootloader digest if Secure Boot is enabled.

For proof of implementation, contact us

[comment]: <> (**Derived from:** [Documentation by Hardware provider: Espressif]&#40;https://docs.espressif.com/projects/esp-idf/en/latest/esp32/security/flash-encryption.html#introduction&#41;)
