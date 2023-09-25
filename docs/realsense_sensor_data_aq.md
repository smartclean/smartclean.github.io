---
layout: default
title: Air quality device data
parent: Sensor Data
grand_parent: RealSense
has_toc: true
nav_order: 6
---

## Data format for air quality detection devices

### Device types applicable: 
- SMARTCLEAN#ODRDTR (AQ Wired)
- SMARTCLEAN#ODRDTR_BATT_V1 (AQ Lite / Wireless)
- SMARTCLEAN#ODRDTR_10_IN_1

---

### Data format for each device type

#### Data format for AQ 10-in-1 (ODRDTR_10_IN_1)
Format of attribute: *"v"* in the general data formats:
```json
{
  "co2": "<number>", // Level of Carbon di-oxide in surrounding air, Unit: parts per million (PPM)
  "hcho": "<number>",  // Level of Formaldehyde in surrounding air, Unit: milligrams per meter cube (mg/m3)
  "humidity": "<number>", // Level of humidity in surrounding air, Unit: Percentage (%)
  "light_level": "<number>", // Level of lighting (0-3) in surrounding environment
  "pir_trigger": "<number>", // State (1 or 0) of any motion detected in the environment
  "pm_10": "<number>", // Value of particulate matter (10 micrometer), Unit: ug/m3 (microgram per meter cube)
  "pm_2.5": "<number>", // Value of particulate matter <2.5 micrometer measured in ug/m3 (Microgram per meter cube)
  "pressure": "<number>", // Barometric pressure in surrounding air, Unit: In millibars or 100.4 Kilo Pascal
  "temperature": "<number>", // Temperature in surrounding air, Unit: Degree Celcius
  "tvoc": "<number>"  // Total volatile organic compounds in surrounding air, Unit: mg/m3 (milligrams per meter cube)
}
```
Notes:

1. **light_level**: where each value represents the following:
   - 0 (0-5 LUX), 
   - 1 (6 - 50 LUX), 
   - 2 (51 - 100 LUX), 
   - 3 (101 - 500 LUX)
2. **pir_trigger**: This value becomes 1 when any motion is detected in the field of view, otherwise it stays 0


#### Format for AQ Lite (ODRDTR_BATT_V1)
```json
{
  "amm": <number>, // Ammonia channel reading.
  "aqi": <number>, // Air Quality Index (number between 1 - 500)
  "rh": <number>, // Relative humidity (percent, after divided by 10)
  "temp": <number>, // Temperature (degree celcius, after divided by 10)
}
```

Notes:
1. **amm** the value is in parts per billion for ODRDTR_BATT_V1


#### Format for AQ Wired (ODRDTR)

Format of attribute: *"v"* in the general data format:
```json
{
  "amm": <number>, // Ammonia channel reading in parts per million (ppm)
  "rssi": "<number>",  // Received signal strength indicator
  "amm_expected": <number>, // Predicted value for the ammonia channel (used to generate "amm_zscore")
  "amm_zscore": <number>, // Anomaly score attributed to ammonia channel
  "alc_expected": <number>, //Predicted value for the VOC channel (used to generate "alc_zscore")
  "alc_zscore": <number>, // Anomaly score attributed to VOC channel
  "alc": <number>, // VOC channel reading in parts per million (ppm)
  "no2_expected": <number>, // Predicted value for the NOx channel (used to generate "no2_zscore")
  "no2_zscore": <number>, // Anomaly score attributed to NOx channel
  "no2": <number>  // NOx channel reading in parts per million (ppm)
}
```

Notes:
1. The unit of **amm** from this device is parts per million (ppm)
2. **Anomaly scores** characterise the relative deviation of the current ppm reading from the sensor with 
respect to its past sampled data. 
   - The sensor (ODRDTR) samples the readings every 10 seconds for this calculation and attribution. 
   - An anomaly score >= 1.96 can be used when alerting on dynamic thresholding mechanism. 
   - If dynamic thresholding mechanism is not required, the ppm values can be thresholded directly by the applications.

---

### Sample use case for AQ Wired and AQ Lite:
Raise an incident if value of *amm* crosses a threshold.
- *aqi* can also be used to raise an incident depending on single threshold or 
a range of AQI thresholds categorized into bands of AQI values (good to bad)

---

### Example data:

#### Example data for AQ 10-in-1 (ODRDTR_10_IN_1)
```json
{
   "t": "20230911121048",
   "DevType": "SMARTCLEAN#ODRDTR_10_IN_1",
   "DevSubType": "1",
   "time": "2023-09-11T12:10:48+0700",
   "unixT": 1694409048389,
   "Region": "Asia/Jakarta",
   "DEVID": "640423e0305f494a9f604fb87653a4bb",
   "v": {
      "temperature": 27.4,
      "humidity": 69.5,
      "light_level": 3,
      "co2": 918,
      "pir_trigger": 0,
      "tvoc": 0.64,
      "pressure": 1004,
      "hcho": 0.04,
      "pm_25": 18,
      "pm_10": 19
   },
   "DASSOC": "24E124710C409578",
   "PID": "ffaedea26c6242b7801de5285d3fc285",
   "PropId": "6c1fe446a7d2475c9e55c8f58b78d14d",
   "InsID": "b356618ee0b64ceb9fe915f80e15c4f6",
   "Display": "AQ 10in1 Test",
   "utc": 1694409048,
   "expire_at": 1709961048,
   "dow": "1",
   "month": "09",
   "hour": "12",
   "dom": "11",
   "minute": "10",
   "Type": "",
   "unix": 1694409048
}
```

#### Example data for AQ Lite (ODRDTR_BATT_V1)
```json
{
  "AGG": "20220601135945",
  "DASSOC": "4EB721A16F",
  "DEVID": "<Device Alias ID>",
  "DevSubType": "1",
  "DevType": "SMARTCLEAN#ODRDTR_BATT_V1",
  "Display": "Indoor Air Quality",
  "dom": "01",
  "dow": "3",
  "expire_at": 1669615185,
  "hour": "13",
  "ID": "43b3d04a75f3485ebc330d792b037ca7",
  "InsID": "<Zone ID>",
  "minute": "59",
  "month": "06",
  "PID": "<Building ID>",
  "PropId": "<Property ID>",
  "Region": "Asia/Singapore",
  "t": "20220601135945",
  "time": "2022-06-01T13:59:45+0800",
  "Type": null,
  "unix": 1654063185,
  "unixT": 1654063185904,
  "utc": 1654063185,
  "v": {
    "amm": 0,
    "aqi": 103,
    "rh": 730,
    "temp": 304
  }
}
```

#### Example data for AQ Wired (ODRDTR)
```json
{
    "t": "20230725160113",
    "DevType": "ODRDTR",
    "DevSubType": "2.9.3",
    "time": "2023-07-25T16:01:13+0800",
    "unixT": 1690272073800,
    "Region": "Asia/Singapore",
    "DEVID": "<Device Alias ID>",
    "v": {
        "rssi": "-68",
        "amm_expected": 2.48374,
        "amm_zscore": -0.319278,
        "amm": 2.481529,
        "alc_expected": 0.168401,
        "alc_zscore": -0.005464,
        "alc": 0.168391,
        "no2_expected": 0.725154,
        "no2_zscore": 0.177453,
        "no2": 0.725579
    },
    "DASSOC": "191021101735246F2820789C",
    "PID": "<Building ID>",
    "InsID": "<Zone ID>",
    "Display": "Air Quality",
    "stats": {
        "sg.smartclean.thresholding": {
            "AMM": {
                "HEALTH_OP_LOWER": "GE",
                "HEALTH_OP_UPPER": "LT",
                "HEALTH_THRESH_UPPER": 0.2,
                "HEALTH_THRESH_LOWER": 0,
                "HEALTH_STATUS": "INVALID",
                "HEALTH_VALUE": 0
            },
            "aggregatedModelOutput": false,
            "aggregatedModelThreshold": 3,
            "aggregatedModelOp": "GE"
        }
    },
    "utc": 1690272073,
    "expire_at": 1705824073,
    "dow": "2",
    "month": "07",
    "hour": "16",
    "dom": "25",
    "minute": "01"
}
```

