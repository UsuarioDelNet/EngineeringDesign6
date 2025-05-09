# Engineering Design VI `CPE 322-A`
## Lab 7 — ThingSpeak and Google Sheets
---

- [`making the cpu_loop channel`](#1)
- [`running thingspeak_feed.py`](#2)
- [`setting up cpudata`](#3)
- [`running cpu_spreadsheet.py`](#4)


To go to the postscript, click [`HERE`](#100)

---
<h3 id="1">making the cpu_loop channel</h3>


<h3 id="2">running thingspeak_feed.py</h3>

```
C:\Users\mrdan>pip3 install -U psutil
Requirement already satisfied: psutil in c:\users\mrdan\appdata\local\programs\python\python313\lib\site-packages (7.0.0)
PS C:\Users\mrdan> cd iot
PS C:\Users\mrdan\iot> cd demo
PS C:\Users\mrdan\iot\demo> cp ~/iot/lesson7/thingspeak_cpu_loop.py .
PS C:\Users\mrdan\iot\demo> cp ~/iot/lesson7/thingspeak_feed.py .
PS C:\Users\mrdan\iot\demo> ls


    Directory: C:\Users\mrdan\iot\demo


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----         4/28/2025   2:36 AM             36 file1
-a----         4/28/2025   2:26 AM            981 thingspeak_cpu_loop.py
-a----         4/28/2025   2:26 AM           2533 thingspeak_feed.py

PS C:\Users\mrdan\iot\demo> python thingspeak_feed.py
An API key savefile was not found. Enter Write API Key >>> QUUKEQUZNLGCNVSU
Should we save this key for future use? [y/N] >>> y
13.5
16401.5703125
Thu, 08 May 2025 23:50:11
200 OK
14.9
16423.10546875
Thu, 08 May 2025 23:51:11
200 OK
12.2
16432.4453125
Thu, 08 May 2025 23:52:11
200 OK
18.5
16219.17578125
Thu, 08 May 2025 23:53:11
200 OK
```

<h3 id="3">setting up cpudata</h3>

```
PS C:\Users\mrdan> pip install -U gspread oauth2client
Collecting gspread
  Downloading gspread-6.2.0-py3-none-any.whl.metadata (11 kB)
Collecting oauth2client
  Downloading oauth2client-4.1.3-py2.py3-none-any.whl.metadata (1.2 kB)
Collecting google-auth>=1.12.0 (from gspread)
  Downloading google_auth-2.40.1-py2.py3-none-any.whl.metadata (6.2 kB)
Collecting google-auth-oauthlib>=0.4.1 (from gspread)
  Downloading google_auth_oauthlib-1.2.2-py3-none-any.whl.metadata (2.7 kB)
Collecting httplib2>=0.9.1 (from oauth2client)
  Downloading httplib2-0.22.0-py3-none-any.whl.metadata (2.6 kB)
Collecting pyasn1>=0.1.7 (from oauth2client)
  Downloading pyasn1-0.6.1-py3-none-any.whl.metadata (8.4 kB)
Collecting pyasn1-modules>=0.0.5 (from oauth2client)
  Downloading pyasn1_modules-0.4.2-py3-none-any.whl.metadata (3.5 kB)
Collecting rsa>=3.1.4 (from oauth2client)
  Downloading rsa-4.9.1-py3-none-any.whl.metadata (5.6 kB)
Requirement already satisfied: six>=1.6.1 in c:\users\mrdan\appdata\local\programs\python\python313\lib\site-packages (from oauth2client) (1.17.0)
Collecting cachetools<6.0,>=2.0.0 (from google-auth>=1.12.0->gspread)
  Downloading cachetools-5.5.2-py3-none-any.whl.metadata (5.4 kB)
Collecting requests-oauthlib>=0.7.0 (from google-auth-oauthlib>=0.4.1->gspread)
  Downloading requests_oauthlib-2.0.0-py2.py3-none-any.whl.metadata (11 kB)
Requirement already satisfied: pyparsing!=3.0.0,!=3.0.1,!=3.0.2,!=3.0.3,<4,>=2.4.2 in c:\users\mrdan\appdata\local\programs\python\python313\lib\site-packages (from httplib2>=0.9.1->oauth2client) (3.2.3)
Collecting oauthlib>=3.0.0 (from requests-oauthlib>=0.7.0->google-auth-oauthlib>=0.4.1->gspread)
  Downloading oauthlib-3.2.2-py3-none-any.whl.metadata (7.5 kB)
Requirement already satisfied: requests>=2.0.0 in c:\users\mrdan\appdata\local\programs\python\python313\lib\site-packages (from requests-oauthlib>=0.7.0->google-auth-oauthlib>=0.4.1->gspread) (2.32.3)
Requirement already satisfied: charset-normalizer<4,>=2 in c:\users\mrdan\appdata\local\programs\python\python313\lib\site-packages (from requests>=2.0.0->requests-oauthlib>=0.7.0->google-auth-oauthlib>=0.4.1->gspread) (3.4.1)
Requirement already satisfied: idna<4,>=2.5 in c:\users\mrdan\appdata\local\programs\python\python313\lib\site-packages (from requests>=2.0.0->requests-oauthlib>=0.7.0->google-auth-oauthlib>=0.4.1->gspread) (3.10)
Requirement already satisfied: urllib3<3,>=1.21.1 in c:\users\mrdan\appdata\local\programs\python\python313\lib\site-packages (from requests>=2.0.0->requests-oauthlib>=0.7.0->google-auth-oauthlib>=0.4.1->gspread) (2.4.0)
Requirement already satisfied: certifi>=2017.4.17 in c:\users\mrdan\appdata\local\programs\python\python313\lib\site-packages (from requests>=2.0.0->requests-oauthlib>=0.7.0->google-auth-oauthlib>=0.4.1->gspread) (2025.4.26)
Downloading gspread-6.2.0-py3-none-any.whl (59 kB)
Downloading oauth2client-4.1.3-py2.py3-none-any.whl (98 kB)
Downloading google_auth-2.40.1-py2.py3-none-any.whl (216 kB)
Downloading cachetools-5.5.2-py3-none-any.whl (10 kB)
Downloading rsa-4.9.1-py3-none-any.whl (34 kB)
Downloading google_auth_oauthlib-1.2.2-py3-none-any.whl (19 kB)
Downloading httplib2-0.22.0-py3-none-any.whl (96 kB)
Downloading pyasn1-0.6.1-py3-none-any.whl (83 kB)
Downloading pyasn1_modules-0.4.2-py3-none-any.whl (181 kB)
Downloading requests_oauthlib-2.0.0-py2.py3-none-any.whl (24 kB)
Downloading oauthlib-3.2.2-py3-none-any.whl (151 kB)
Installing collected packages: pyasn1, oauthlib, httplib2, cachetools, rsa, requests-oauthlib, pyasn1-modules, oauth2client, google-auth, google-auth-oauthlib, gspread
Successfully installed cachetools-5.5.2 google-auth-2.40.1 google-auth-oauthlib-1.2.2 gspread-6.2.0 httplib2-0.22.0 oauth2client-4.1.3 oauthlib-3.2.2 pyasn1-0.6.1 pyasn1-modules-0.4.2 requests-oauthlib-2.0.0 rsa-4.9.1
```



<h3 id="4">running cpu_spreadsheet.py</h3>

```
PS C:\Users\mrdan> cd iot
PS C:\Users\mrdan\iot> cd demo
PS C:\Users\mrdan\iot\demo> cp ~/iot/lesson3/system_info.py
PS C:\Users\mrdan\iot\demo> cp ~/iot/lesson7/cpu_spreadsheet.py
PS C:\Users\mrdan\iot\demo> cp C:\Users\mrdan\Downloads\cpudata-459312-429f0b20086c.json
PS C:\Users\mrdan\iot\demo> ls


    Directory: C:\Users\mrdan\iot\demo


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----          5/9/2025   8:19 AM                __pycache__
-a----          5/8/2025  11:50 PM             44 API_KEY.pickle
-a----          5/9/2025   8:33 AM           2350 cpudata-459312-429f0
                                                  b20086c.json
-a----          5/9/2025   8:42 AM           2120 cpu_spreadsheet.py
-a----         4/28/2025   2:36 AM             36 file1
-a----         4/28/2025   2:26 AM           2490 system_info.py
-a----         4/28/2025   2:26 AM            981 thingspeak_cpu_loop.
                                                  py
-a----         4/28/2025   2:26 AM           2533 thingspeak_feed.py
```

```
PS C:\Users\mrdan\iot\demo> nano cpu_spreadsheet.py
PS C:\Users\mrdan\iot\demo> python cpu_spreadsheet.py
Logging sensor measurements to cpudata every 10 seconds.
Press Ctrl-C to quit.
2025-05-09 08:46:56.568199
CPU Usage:        3.7%
Memory Available: 17.2 GB
Wrote a row to cpudata
2025-05-09 08:47:06.944274
CPU Usage:        2.6%
Memory Available: 17.2 GB
Wrote a row to cpudata
2025-05-09 08:47:17.215194
CPU Usage:        1.7%
Memory Available: 17.2 GB
Wrote a row to cpudata
2025-05-09 08:47:27.442238
CPU Usage:        2.7%
Memory Available: 17.2 GB
Wrote a row to cpudata
2025-05-09 08:47:37.722494
CPU Usage:        3.5%
Memory Available: 17.2 GB
Wrote a row to cpudata
2025-05-09 08:47:47.928806
CPU Usage:        1.5%
Memory Available: 17.2 GB
Wrote a row to cpudata
2025-05-09 08:47:58.266512
CPU Usage:        1.8%
Memory Available: 17.2 GB
Wrote a row to cpudata
2025-05-09 08:48:08.520329
CPU Usage:        1.6%
Memory Available: 17.2 GB
Wrote a row to cpudata
2025-05-09 08:48:18.753014
CPU Usage:        3.5%
Memory Available: 17.5 GB
Wrote a row to cpudata
2025-05-09 08:48:28.957804
CPU Usage:        3.6%
Memory Available: 17.5 GB
Wrote a row to cpudata
```

---
<h4 id="100">Postscript</h4>

- All my source files were initially obtained in [`Dr. Lu's GitHub`](https://github.com/kevinwlu/iot/tree/master/lesson4)
- Please note, I replaced all the instances of "python3" with "python" in the commands for the lab, as I had Python downloaded on my system already.
- I pledge my honor that I have abided by the Stevens Honor System: Daniel A. Liss
