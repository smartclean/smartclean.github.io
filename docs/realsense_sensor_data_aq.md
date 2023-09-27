---
layout: default
title: Air quality device data
parent: Sensor Data
grand_parent: RealSense
has_toc: true
nav_order: 6
---

## Data of Air Quality detection devices

### Device types applicable: 
- SMARTCLEAN#ODRDTR (AQ Wired)
- SMARTCLEAN#ODRDTR_BATT_V1 (AQ Lite / Wireless)
- SMARTCLEAN#ODRDTR_10_IN_1

---

### Data for AQ 10-in-1 (ODRDTR_10_IN_1)
Format of attribute: *"v"* in the general data formats:
```json
{
  "co2": "<number>", // Level of Carbon in surrounding air, Unit: parts per million (PPM)
  "hcho": "<number>",  // Level of Formaldehyde in surrounding air, Unit: milligrams per meter cube (mg/m3)
  "humidity": "<number>", // Level of humidity in surrounding air, Unit: Percentage (%)
  "light_level": "<number>", // Level of lighting (0-3) in surrounding environment
  "tvoc": "<number>",  // Level of volatile organic compounds in surrounding air, Unit: mg/m3 (milligrams per meter cube)
  "pm_10": "<number>", // Level of particulate matter (10 micrometer), Unit: ug/m3 (microgram per meter cube)
  "pm_2.5": "<number>", // Level of particulate matter <2.5 micrometer measured in ug/m3 (Microgram per meter cube)
  "pressure": "<number>", // Barometric pressure in surrounding air, Unit: In millibars or 100.4 Kilo Pascal
  "temperature": "<number>", // Temperature in surrounding air, Unit: Degree Celcius
  "pir_trigger": "<number>" // State (1 or 0) of any motion detected in the environment
}
```

Notes:
1. **pir_trigger** (state of motion detected): value becomes 1 when motion is detected in the field of view, else it stays 0
2. **light_level** (lighting level in surrounding area) has the following representation:

| S.No | light_level | Range of light | 
|------|-------------|----------------|
|  1.  |      0      |  0 to 0 Lux    |
|  2.  |      1      |  06 to 50 Lux  | 
|  3.  |      2      |  51 to 100 Lux | 
|  4.  |      3      |  101 to 500 Lux|

---
### Data for AQ Lite (ODRDTR_BATT_V1)
Format of attribute: *"v"* in the general data formats:
```json
{
  "amm": <number>, // Level of Ammonia in surrounding air, Unit: PPM (parts per billion)
  "aqi": <number>, // Air Quality Index (number between 1 - 500)
  "rh": <number>, // Relative humidity (percent, after divided by 10)
  "temp": <number>, // Temperature (degree celcius, after divided by 10)
}
```

**Example use cases:**

1. **Threshold on level of Ammonia:**
   1. Consider the level of ammonia has undesired level when the value of **amm** crosses a maximum limit 
   2. The maximum limit can be changed by users by analysing the historical data (initial value is a suitable default)

2. **Thresholds to categorize Air Quality Index (AQI)** 
   1. Value of **aqi** can be used to categorize air quality based on a single threshold (good vs bad) 
   or a range of thresholds to classify air quality into a set of categories (Excellent to Very bad)
   2. For a standard reference [refer to this image](https://smartclean-public.s3.ap-southeast-1.amazonaws.com/docs/IAQ+Bands+Bosch+V2.png)
      1. Source: Page 9 of [sensor Datasheet at this link](https://www.bosch-sensortec.com/media/boschsensortec/downloads/datasheets/bst-bme680-ds001.pdf) 
      
### Data for AQ Wired (ODRDTR)

Format of attribute: *"v"* in the general data format:
```json
{
  "amm": <number>, // Level of Ammonia in surrounding air, Unit: PPM (parts per million)
  "alc": <number>, // Level of Volatile organic compounds (VOC) in surrounding air, Unit: PPM (parts per million)
  "no2": <number>,  // Level of Nitrogen in surrounding air, Unit: PPM (in parts per million)
  "amm_zscore": <number>, // Anomaly score for level of Ammonia (amm)
  "no2_zscore": <number>, // Anomaly score for level of Nitrogen (no2)
  "alc_zscore": <number>, // Anomaly score for level of VOC (alc)
  "amm_expected": <number>, // Predicted level for Ammonia (used to generate "amm_zscore")
  "alc_expected": <number>, // Predicted level for VOC (used to generate "alc_zscore")
  "no2_expected": <number>, // Predicted value for Nitrogen (used to generate "no2_zscore")
  "rssi": "<number>"  // Received signal strength indicator
}
```

Notes:
1. The unit of **amm** from this device is parts per million (ppm)
2. *Anomaly scores* in the fields **amm_zscore**, **alc_zscore** and **no2_zscore** represent relative deviation of current ppm reading from the sensor with respect to its last sampled data. 
   1. The sensor (ODRDTR) samples the readings every 10 seconds for this calculation and attribution.

**Example use cases:**

1. **Threshold on anomaly scores of each component:**
   1. Consider the component as an anomaly (possibly, undesired) when anomaly score of the respective component  crosses the value _"1.96"_
   
2. **Threshold on level of each component:**
   1. Consider the component has an undesired level, when level of respective component crosses a maximum limit.
   2. The maximum limit can be changed by users, preferably after analysing historical data.
      1. Note: Initial value is set to a suitable default.
   
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

