# Engineering Design VI `CPE 322-A`
## Lab 3 — Python
---

<ins>Commands to Input into Terminal</ins> 
- [`$ cd ~/iot`](#1)
- [`$ cd *3`](#2)
- [`$ python3 julian.py`](#3) 
- [`$ python3 date_example.py`](#4) 
- [`$ python3 datetime_example.py`](#5) 
- [`$ python3 time_example.py`](#6) 
- [`$ python3 sun.py "New York"`](#7) 
- [`$ python3 moon.py`](#8) 
- [`$ python3 coordinates.py "Samuel C. Williams Library"`](#9) 
- [`$ python3 address.py "40.74480675, -74.02532861159351"`](#10) 
- [`$ python3 cpu.py`](#11) 
- [`$ python3 battery.py`](#12) 
- [`$ python3 documentstats.py document.txt`](#13) 
---


<h3 id="1">cd ~/iot</h3>

> 
```
C:\Users\mrdan>cd iot

C:\Users\mrdan\iot>
```

<h3 id="2">cd *3</h3>

> 
```
C:\Users\mrdan\iot>cd *3

C:\Users\mrdan\iot\lesson3>
```


<h3 id="3">python3 julian.py</h3>

> 
```
C:\Users\mrdan\iot\lesson3>python julian.py
Calendar Date: 2025-04-29
Julian Date: 2460794.5
Modified Julian Date: 60794.0
```


<h3 id="4">python3 date_example.py</h3>

> 
```
C:\Users\mrdan\iot\lesson3>python date_example.py
Date: 2025-04-29
Date: 04-29-25
Day of Week: Tuesday
Month: April
Year: 2025
98 days after the first day of classes
8 days before the last day of classes
```


<h3 id="5">python3 datetime_example.py</h3>

> 
```
C:\Users\mrdan\iot\lesson3>python datetime_example.py
2025-04-29 23:44:16.717907
2025-04-29 23:44:16.718215
C:\Users\mrdan\iot\lesson3\datetime_example.py:4: DeprecationWarning: datetime.datetime.utcnow() is deprecated and scheduled for removal in a future version. Use timezone-aware objects to represent datetimes in UTC: datetime.datetime.now(datetime.UTC).
  print(datetime.datetime.utcnow())
2025-04-30 03:44:16.749679
1745984656.7501037
Tue Apr 29 23:44:16 2025
2025-04-29 23:44:16.750844
C:\Users\mrdan\iot\lesson3\datetime_example.py:8: DeprecationWarning: datetime.datetime.utcfromtimestamp() is deprecated and scheduled for removal in a future version. Use timezone-aware objects to represent datetimes in UTC: datetime.datetime.fromtimestamp(timestamp, datetime.UTC).
  print(datetime.datetime.utcfromtimestamp(time.time()))
2025-04-30 03:44:16.751168
```


<h3 id="6">python3 time_example.py</h3>

> 
```
C:\Users\mrdan\iot\lesson3>python time_example.py
Tue Apr 29 23:45:09 2025
Tue Apr 29 23:45:19 2025
Tue Apr 29 23:45:29 2025
Tue Apr 29 23:45:39 2025
Tue Apr 29 23:45:49 2025
Tue Apr 29 23:45:59 2025
Tue Apr 29 23:46:09 2025
```


<h3 id="7">python3 sun.py "New York"</h3>

> To complete this, i needed to pip install pytz
```
C:\Users\mrdan\iot\lesson3>python sun.py "New York"
Information for New York/USA

Timezone: US/Eastern
Latitude: 40.72; Longitude: -74.00

Dawn:    2025-04-29 05:26:58.133350-04:00
Sunrise: 2025-04-29 05:57:03.856809-04:00
Noon:    2025-04-29 12:53:23-04:00
Sunset:  2025-04-29 19:50:12.285136-04:00
Dusk:    2025-04-29 20:20:24.471803-04:00
```


<h3 id="8">python3 moon.py</h3>

> 
```
C:\Users\mrdan\iot\lesson3>python moon.py
2025-04-29 Moon Phase: 1
2025-04-30 Moon Phase: 2
2025-05-01 Moon Phase: 3
2025-05-02 Moon Phase: 4
2025-05-03 Moon Phase: 5
2025-05-04 Moon Phase: 6
2025-05-05 Moon Phase: 7
2025-05-06 Moon Phase: 8
2025-05-07 Moon Phase: 9
2025-05-08 Moon Phase: 10
2025-05-09 Moon Phase: 11
2025-05-10 Moon Phase: 12
2025-05-11 Moon Phase: 13
2025-05-12 Moon Phase: 13
2025-05-13 Moon Phase: 14
2025-05-14 Moon Phase: 15
2025-05-15 Moon Phase: 16
2025-05-16 Moon Phase: 17
2025-05-17 Moon Phase: 18
2025-05-18 Moon Phase: 19
2025-05-19 Moon Phase: 20
2025-05-20 Moon Phase: 20
2025-05-21 Moon Phase: 21
2025-05-22 Moon Phase: 22
2025-05-23 Moon Phase: 23
2025-05-24 Moon Phase: 25
2025-05-25 Moon Phase: 26
2025-05-26 Moon Phase: 27
2025-05-27 Moon Phase: 0
2025-05-28 Moon Phase: 1
```


<h3 id="9">python3 coordinates.py "Samuel C. Williams Library"</h3>

> 
```
C:\Users\mrdan\iot\lesson3>python coordinates.py "Samuel C. Williams Library"
Samuel C. Williams Library, Field House Road, Uptown, Hoboken, Hudson County, New Jersey, 07030, United States
(40.7448068, -74.0253286)
```


<h3 id="10">python3 address.py "40.74480675, -74.02532861159351"</h3>

> 
```
C:\Users\mrdan\iot\lesson3>python address.py "40.74480675, -74.02532861159351"
Stevens Institute of Technology, 1, Wittpenn Walk, Uptown, Hoboken, Hudson County, New Jersey, 07030, United States
(40.7448096, -74.0252392)
```


<h3 id="11">python3 cpu.py</h3>

> 
```
C:\Users\mrdan\iot\lesson3>python cpu.py
The number of physical cores =  14
The number of logical CPUs =  20
The utilization per second as a percentage for each CPU
[0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 16.9, 0.0, 0.0, 0.0, 0.0, 0.0, 3.1, 0.0, 0.0, 3.1, 0.0, 0.0, 0.0, 0.0]
[0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 12.5, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 1.6, 4.7, 0.0, 0.0, 0.0, 0.0]
[0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 3.1, 0.0, 4.6, 4.6, 0.0, 0.0, 0.0, 0.0]
[0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 13.4, 0.0, 1.6, 0.0, 0.0, 0.0]
[1.5, 0.0, 0.0, 0.0, 1.5, 0.0, 0.0, 0.0, 1.5, 0.0, 1.5, 0.0, 6.3, 6.2, 6.2, 25.8, 13.6, 0.0, 9.2, 4.7]
[1.6, 0.0, 0.0, 0.0, 17.5, 1.6, 10.9, 0.0, 6.5, 0.0, 0.0, 0.0, 1.6, 10.6, 6.2, 15.6, 1.6, 0.0, 0.0, 10.9]
[0.0, 0.0, 0.0, 0.0, 1.5, 0.0, 24.6, 0.0, 0.0, 0.0, 0.0, 0.0, 3.1, 0.0, 4.6, 1.6, 0.0, 0.0, 0.0, 0.0]
[0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 16.4, 0.0, 0.0, 0.0, 0.0, 0.0, 6.2, 1.6, 9.4, 4.6, 0.0, 0.0, 0.0, 0.0]
[0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 3.1, 0.0, 0.0, 0.0, 0.0, 0.0, 4.7, 0.0, 9.2, 9.0, 0.0, 0.0, 0.0, 0.0]
[0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 7.8, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 16.9, 3.1, 0.0, 0.0, 0.0, 0.0]
```


<h3 id="12">python3 battery.py</h3>

> 
```
C:\Users\mrdan\iot\lesson3>python battery.py
sbattery(percent=100, secsleft=<BatteryTime.POWER_TIME_UNLIMITED: -2>, power_plugged=True)
```
```
C:\Users\mrdan\iot\lesson3>python battery.py
sbattery(percent=100, secsleft=4294967295, power_plugged=False)
```


<h3 id="13">python3 documentstats.py document.txt</h3>

> 
```
C:\Users\mrdan\iot\lesson3>python documentstats.py document.txt
Word Count: 1343
Top Ten Words: [('our', 26), ('their', 20), ('has', 20), ('he', 19), ('them', 15), ('these', 13), ('have', 11), ('we', 11), ('us', 11), ('people', 10)]
```


---
#### Postscript
- To see the screenshots I took of my Terminal, please go to [the Readme file within SourcesLab3](https://github.com/UsuarioDelNet/EngineeringDesign6/blob/main/Labs/Lab3/SourcesLab3/README.md). They are in the same order as this file.
- I pledge my honor that I have abided by the Stevens Honor System: Daniel A. Liss
