---
layout: default
title: Tree tilt data
parent: Sensor Data
grand_parent: RealSense
has_toc: true
nav_order: 8
---

## Data of Tree tilt monitoring device

### Device type applicable: 
- SMARTCLEAN#TILT (tree tilt monitoring, type 1)

---

### Data for Tree tilt monitoring, type 1 (TILT)
Format of attribute: *"v"* in the general data formats:
```json
{
    "Xt": <number>, // Angle of tilt on horizontal dimension (X-axis of 3-D space), in degrees.
    "Yt": <number>, // Angle of tilt on vertical dimension (Y-axis of 3-D space), in degrees.
    "Zt": <number>, // Angle of tilt on third dimension (Z-axis of 3-D space), in degrees.
    "v": <number> // Level of sensor battery remaining, in percentage.
}
```

Notes for *Angle of Tilt* (**Xt / Yt / Zt**):

1. The measurement is with respect to the baseline value recorded on the respective axis.

`This baseline value should be set or can be changed after physical examination of the tree and analysis of calibration data from the device installed on the tree.`

2. The value can be positive or negative, which represents the direction of tilt.

`Numeric value represents magnitude of tilt in either direction of the respective dimension.`

**Example use case:**

Raise alarm (to take action) when magnitude of tilt with respect to the recorded baseline value on any of the three dimensions in the 3D space reaches or crosses a threshold value.
   
---
### Example data

#### Example data for Tree tilt monitoring, type 1 (TILT):
```json
{
  "t": "20231117124855",
  "DevType": "SMARTCLEAN#TILT",
  "DevSubType": "1",
  "time": "2023-11-17T12:48:55+0800",
  "unixT": 1700196535702,
  "Region": "Asia/Singapore",
  "DEVID": "<Alias ID of Device Slot>",
  "v": {
    "Tb": "none",
    "Xt": -87.51,
    "Yt": -2.04,
    "Zt": 1.42,
    "v": 100
  },
  "DASSOC": "24E124713D324139",
  "PID": "<ID of Project>",
  "PropId": "<ID of Property>",
  "InsID": "<ID of Installation (location)>",
  "Display": "<Display name for the Device>",
  "utc": 1700196535,
  "expire_at": 1715748535,
  "dow": "5",
  "month": "11",
  "hour": "12",
  "dom": "17",
  "minute": "48",
  "Type": "",
  "unix": 1700196535
}
```

#### Example entity names for a sample installation:

**Organization Name:** *Singapore Zoological Gardens*

- `Mapped to Organization ID in our platform`

**Property (Site) Name:** *Mandai Bird Paradise*

- `Mapped to Property ID ("PropId") in the data`

**Project (Region): Name** *Kuok Group of Wings Asia*

- `Mapped to Project ID ("PID") in the data`

**Installation (Location) Name:** *Bali village entrance*

- `Mapped to Installation ID ("InsID") in the data`

**Device (Tree) Name:** *Rambutan 4*

- `Mapped to Device ID ("DEVID"); and`
- `Represented by Display name ("Display") in the data`