---
layout: default
title: Secure interface
parent: Hardware Security
grand_parent: RealSense
nav_order: 3
---

# Secure interface
Prevent unauthorized access via programming interface (access port)

**Benefit:** Access port blocks read and write access to all CPU registers and memory-mapped addresses.

## Procedure
Set the system variable: UICR.APPROTECT to Enabled in the firmware and perform a reset.

## More Details:
1. When enabled, this mechanism blocks the debugger from read and write access to all CPU registers and memory-mapped addresses. 
2. Accessing these registers and addresses again requires disabling the mechanism and erasing the flash.


For proof of implementation, contact us

[comment]: <> (**Derived from:** [Documentation by Hardware provider: Nordic Semiconductor]&#40;https://developer.nordicsemi.com/nRF_Connect_SDK/doc/latest/nrf/app_dev/ap_protect/index.html&#41;)
