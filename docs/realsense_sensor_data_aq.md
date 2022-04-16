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
- SMARTCLEAN#ODRDTR_BATT_V1

Format of attribute: *"v"* in the general data format:
```json
{
  "amm": <number>, // Ammonia channel reading.
  "aqi": <number>, // Air Quality Index (number between 1 - 500), only present for ODRDTR_BATT_V1
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
  "t": "20211210152132",
  "v": {
    "amm": 270,
    "aqi": 180, 
    "rssi": "-47", 
    "amm_expected": 3.426926, 
    "amm_zscore": -0.119488, 
    "alc_expected": 0.168433, 
    "alc_zscore": -0.021021, 
    "alc": 0.168391, 
    "no2_expected": 1.181777, 
    "no2_zscore": 0.001301, 
    "no2": 1.181781
  },
  "unixT": 1639120892,
  "DEVID": "DemoAQ1",
  "Region": "Asia/Singapore",
  "time": "2021-12-10T15:21:32+0800",
  "DevType": "SMARTCLEAN#ODRDTR_BATT_V1",
  "PID": "DemoProject",
  "InsID": "DemoLocation",
  "Display": "Demo Air Quality Light 1",
  "dow": "5",
  "month": "12",
  "hour": "15",
  "dom": "10",
  "minute": "21"
}
```

#### Example use case:
Raise an incident if value of *amm* crosses a threshold.
- *aqi* can also be used to raise an incident depending on single threshold or 
a range of AQI thresholds categorized into bands of AQI values (good to bad)

