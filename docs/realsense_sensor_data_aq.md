---
layout: default
title: Air quality device data
parent: Sensor Data
grand_parent: RealSense
has_toc: true
nav_order: 6
---

## Data format for air quality detection devices

Device slot types applicable: 
- SMARTCLEAN#ODRDTR
- SMARTCLEAN#ODRDTR_BATT_V1 (AQ Lite)

Format of attribute: *"v"* in the general data format:
```json
{
  "amm": <number>, // Ammonia channel reading.
  "aqi": <number>, // Air Quality Index (number between 1 - 500), only present for ODRDTR_BATT_V1
  "rh": <number>, // Relative humidity (percent, after divided by 10), only present for ODRDTR_BATT_V1
  "temp": <number>, // Temperature (degree celcius, after divided by 10), only present for ODRDTR_BATT_V1 
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
1. **aqi** is not present in data for the type: ODRDTR
2. **amm** the value is in parts per million for ODRDTR and in parts per billion for ODRDTR_BATT_V1
3. **Anomaly scores** characterise the relative deviation of the current ppm reading from the sensor with 
respect to its past sampled data. 
   - The sensor (ODRDTR) samples the readings every 10 seconds for this calculation and attribution. 
   - An anomaly score >= 1.96 can be used when alerting on dynamic thresholding mechanism. 
   - If dynamic thresholding mechanism is not required, the ppm values can be thresholded directly by the applications.
4. For **more details about our air quality monitoring device** 
please visit our [help center page](https://help.smartclean.io/support/solutions/articles/84000347358-od-wf-1901-how-it-works)

---

#### Example data:
For SMARTCLEAN#ODRDTR_BATT_V1

```json
{
  "AGG": "20220601135945",
  "DASSOC": "4EB721A16F",
  "DEVID": "43b3d04a75f3485ebc330d792b037ca7",
  "DevSubType": "1",
  "DevType": "SMARTCLEAN#ODRDTR_BATT_V1",
  "Display": "Indoor Air Quality",
  "dom": "01",
  "dow": "3",
  "expire_at": 1669615185,
  "hour": "13",
  "ID": "43b3d04a75f3485ebc330d792b037ca7",
  "InsID": "845c7c480e7345ff8e00e302776c7062",
  "minute": "59",
  "month": "06",
  "PID": "45ea1d38775046dbbdc955362b8834b1",
  "PropId": "d2ff1cc0ee104abba3a8ba030c72cd06",
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

#### Example use case:
Raise an incident if value of *amm* crosses a threshold.
- *aqi* can also be used to raise an incident depending on single threshold or 
a range of AQI thresholds categorized into bands of AQI values (good to bad)

