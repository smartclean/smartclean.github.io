---
layout: default
title: Android Security
parent: RealSense
grand_parent: SmartClean Matrix
has_children: false
has_toc: true
nav_order: 4
---
# Android Security
This page describes measures in place for securing our Android based devices

## 1. App sandbox
The Android platform takes advantage of the Linux user-based protection to identify and isolate app resources. To do this, Android assigns a unique user ID (UID) to each Android app and runs it in its own process. Android uses this UID to set up a kernel-level App Sandbox.

## 2. App signing
App signing allows us to identify the author of the app and to update their app without creating complicated interfaces and permissions. Every app that runs on the our devices must be signed by the developer.

## 3. Authentication
Android uses the concept of user-authentication-gated cryptographic keys that requires cryptographic key storage and service provider and user authenticators.

On devices with a fingerprint sensor, users can enroll one or more fingerprints and use those fingerprints to unlock the device and perform other tasks. The Gatekeeper subsystem performs device pattern/password authentication in a Trusted Execution Environment (TEE).

Android 9 and higher includes Protected Confirmation, which gives users a way to formally confirm critical transactions, such as payments.

## 4. Encryption
Once a device is encrypted, all user-created data is automatically encrypted before committing it to disk and all reads automatically decrypt data before returning it to the calling process. Encryption ensures that even if an unauthorized party tries to access the data, they won’t be able to read it.

## 5. Keystore
Android offers a hardware-backed Keystore that provides key generation, import and export of asymmetric keys, import of raw symmetric keys, asymmetric encryption and decryption with appropriate padding modes, and more.

## 6. Security-Enhanced Linux
As part of the Android security model, Android uses Security-Enhanced Linux (SELinux) to enforce mandatory access control (MAC) over all processes, even processes running with root/superuser privileges (Linux capabilities).

## 7. gVerified Boot
Verified Boot strives to ensure all executed code comes from a trusted source (usually device OEMs), rather than from an attacker or corruption. It establishes a full chain of trust, starting from a hardware-protected root of trust to the bootloader, to the boot partition and other verified partitions.



<sub>https://source.android.com/docs/security/features</sub>