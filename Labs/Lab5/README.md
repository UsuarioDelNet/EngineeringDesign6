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

C:\Users\mrdan>cd iot

C:\Users\mrdan\iot>cd *5

C:\Users\mrdan\iot\lesson5>python client.py
C:\Users\mrdan\iot\lesson5\client.py:15: DeprecationWarning: Callback API version 1 is deprecated, update to latest version
  client = mqtt.Client(mqtt.CallbackAPIVersion.VERSION1)
Connected with result code 0
$SYS/broker/publish/bytes/received 954774984521
$SYS/broker/publish/bytes/sent 20264678858211
$SYS/broker/publish/messages/dropped 49030097567
$SYS/broker/publish/messages/received 5081004246
$SYS/broker/publish/messages/sent 157200447777
$SYS/broker/publish/bytes/received 954778661973
$SYS/broker/publish/bytes/sent 20264864053894
$SYS/broker/publish/messages/dropped 49030866656
$SYS/broker/publish/messages/received 5081034144
$SYS/broker/publish/messages/sent 157201938148
$SYS/broker/publish/bytes/received 954782403010
$SYS/broker/publish/bytes/sent 20265037567568
$SYS/broker/publish/messages/dropped 49031618297
$SYS/broker/publish/messages/received 5081064948
$SYS/broker/publish/messages/sent 157203442633
```

---
<h4 id="100">Postscript</h4>

- All my source files were initially obtained in [`Dr. Lu's GitHub`](https://github.com/kevinwlu/iot/tree/master/lesson4)
- Please note, I replaced all the instances of "python3" with "python" in the commands for the lab, as I had Python downloaded on my system already.
- I pledge my honor that I have abided by the Stevens Honor System: Daniel A. Liss
