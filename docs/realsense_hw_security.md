---
layout: default
title: Hardware Security
parent: RealSense
grand_parent: SmartClean Matrix
has_children: true
has_toc: true
nav_order: 4
---

# Hardware Security
This page describes measures in place for securing our Sensors

## Summary of security measures:
1. Flash encryption
2. Secure boot-loader
3. Secure interface
4. Secure casing

## 1. Flash encryption

**Summary:** This measure ensures contents on the off-chip flash memory included with certain device types is encrypted.

**Benefit:** Encrypted contents on the flash memory cannot be physically read out.


## 2. Secure boot-loader

**Summary:** This measure ensures data loaded from flash is verified on each reset.

**Benefit:** Only authorised code can run on the device's chip.


## 3. Secure interface

**Summary:** Prevent unauthorized access via programming interface (access port)

**Benefit:** Access port blocks read and write access to all CPU registers and memory-mapped addresses.


## 4. Secure casing

**Summary:** Device enclosures include screws and locks.

**Benefit:** Block/prevent access to sensitive parts of the device and allow manual detection of any tampering done.  

## More info
Please navigate to respective sub-page using table of contents below 
