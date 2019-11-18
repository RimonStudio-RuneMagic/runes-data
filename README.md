# Runes Data

## General
Every rune data object will send its id, a String(21) consisting of family and unique ID.
Also, seconds from last boot are sent as uptime:
```json
{ 
  "id": "00000001-645923A4AE30",
  "uptime": 42
}
```

Each rune can have sensors connected and disconnected at runtime, and they are sent as a list:
```json
{ 
  "id": "00000001-645923A4AE30",
  "uptime": 42,
  "sensors": []
}
```

Every sensor will have an id and might have data:
```json
{
  "id": "00000001-645923A4AE30",
  "uptime": 42,
  "sensors": [
    {"id": 249, "data": [16]}, 
    {"id": 104, "data": [8, 647]}
  ]
}
```

## Sensor Types:

### ID: 104 - Gyro / Accelerometer 
Data contains:
Acceleration X, Y, Z, Temperature (for compensation), Gyro X, Y, Z
```json
{"id": 104, "data": [0, 0, -9.7, 28.95353, 3, 193, 129]}
```

### ID: 249 - Distance
Data contains distance in cm (in a list, like all sensors)
```json
{"id": 249, "data": [16]}
```

### ID: 250 - Sound (Volume)
Data contains distance minimum and maximum volume heard in a fraction of a second, between 0 - 4096.
```json
{"id": 250, "data": [64, 100]}
```


### ID: 251 - Movement (PIR)
Data contains 1 if there was movement 0 otherwise (in a list, like all sensors)
```json
{"id": 251, "data": [1]}
```


### ID: 252 - BT scanner
Data contains all Bluetooth device IDs found around the Rune
```json
{"id": 252, "data": ["68:d9:3c:8e:8d:12", "LG SJ9(EB:F0)"]}
```

