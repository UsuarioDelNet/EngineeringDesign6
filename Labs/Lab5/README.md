# Engineering Design VI `CPE 322-A`
## Lab 5 — Paho-MQTT
---

- [`pip installs`](#1)

To go to the postscript, click [`HERE`](#100)

---
<h3 id="1">pip installs</h3>

```
C:\Users\mrdan>pip install paho-mqtt
Collecting paho-mqtt
  Using cached paho_mqtt-2.1.0-py3-none-any.whl.metadata (23 kB)
Using cached paho_mqtt-2.1.0-py3-none-any.whl (67 kB)
Installing collected packages: paho-mqtt
Successfully installed paho-mqtt-2.1.0
```

<h3 id="2">running paho-mqtt</h3>

```
C:\Users\mrdan>git clone https://github.com/eclipse/paho.mqtt.python.git
Cloning into 'paho.mqtt.python'...
remote: Enumerating objects: 6053, done.
remote: Counting objects: 100% (1513/1513), done.
remote: Compressing objects: 100% (275/275), done.
remote: Total 6053 (delta 1367), reused 1238 (delta 1238), pack-reused 4540 (from 3)
Receiving objects: 100% (6053/6053), 1.68 MiB | 2.15 MiB/s, done.
Resolving deltas: 100% (3394/3394), done.
```

```HELLOOOOO
PS C:\Users\mrdan> cd iot
PS C:\Users\mrdan\iot> cd *5
PS C:\Users\mrdan\iot\lesson5> python sub.py
C:\Users\mrdan\iot\lesson5\sub.py:8: DeprecationWarning: Callback API version 1 is deprecated, update to latest version
  client = mqtt.Client(mqtt.CallbackAPIVersion.VERSION1)
Connected with result code 0
paho/test Hello
```

```mult
PS C:\Users\mrdan\iot\lesson5> python sub-multiple.py
C:\Users\mrdan\iot\lesson5\sub-multiple.py:8: DeprecationWarning: Callback API version 1 is deprecated, update to latest version
  client = mqtt.Client(mqtt.CallbackAPIVersion.VERSION1)
Connected with result code 0
paho/test/multiple multiple 1
paho/test/multiple multiple 2
```

```
PS C:\Users\mrdan\iot\lesson5> python subcpu.py
C:\Users\mrdan\iot\lesson5\subcpu.py:8: DeprecationWarning: Callback API version 1 is deprecated, update to latest version
  client = mqtt.Client(mqtt.CallbackAPIVersion.VERSION1)
Connected with result code 0
MyCPU 2025-05-03 23:52:25
MyCPU CPU Usage:   3.0 %
MyCPU 2025-05-03 23:52:35
MyCPU CPU Usage:   2.5 %
MyCPU 2025-05-03 23:52:45
MyCPU CPU Usage:   2.0 %
MyCPU 2025-05-03 23:52:55
MyCPU CPU Usage:   2.2 %
```

```
PS C:\Users\mrdan\iot\lesson5> python pubcpu.py
C:\Users\mrdan\iot\lesson5\pubcpu.py:6: DeprecationWarning: Callback API version 1 is deprecated, update to latest version
  mqttc = mqtt.Client(mqtt.CallbackAPIVersion.VERSION1)
2025-05-03 23:52:25
CPU Usage:   3.0 %
2025-05-03 23:52:35
CPU Usage:   2.5 %
2025-05-03 23:52:45
CPU Usage:   2.0 %
2025-05-03 23:52:55
CPU Usage:   2.2 %
```

---
<h4 id="100">Postscript</h4>

- All my source files were initially obtained in [`Dr. Lu's GitHub`](https://github.com/kevinwlu/iot/tree/master/lesson4)
  - [`Mosquitto Download`](https://mosquitto.org/download/)
- Please note, I replaced all the instances of "python3" with "python" in the commands for the lab, as I had Python downloaded on my system already.
- I pledge my honor that I have abided by the Stevens Honor System: Daniel A. Liss
