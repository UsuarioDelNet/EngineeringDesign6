# Engineering Design VI `CPE 322-A`
## Lab 2 — Command Line
---

<ins>Commands to Input into Terminal</ins> 
- [`$ hostname`](#hostname)
- [`$ env`](#env)
- [`$ ps`](#ps)
- [`$ pwd`](#pwd)
- [`$ git clone https://github.com/kevinwlu/iot.git`](#git-clone)
- [`$ cd iot`](#cd-iot)
- [`$ ls`](#ls)
- [`$ cd`](#cd)
- [`$ df`](#df)
- [`$ mkdir demo`](#mkdir-demo)
- [`$ cd demo`](#cd-demo)
- [`$ nano file`](#nano-file)
- [`$ cat file`](#cat-file)
- [`$ cp file file1`](#cp-file-file1)
- [`$ mv file file2`](#mv-file-file2)
- [`$ rm file2`](#rm-file2)
- [`$ clear`](#clear)
- [`$ man uname`](#man-uname)
- [`$ uname -a`](#uname--a)
- [`$ ifconfig`](#ifconfig)
- [`$ ping localhost`](#ping-localhost)
- [`$ netstat`](#netstat)
---
### hostname
```hostname
C:\Users\mrdan>hostname
DAL_Laptop
```
### env
```env
C:\Users\mrdan>env
!::=::\
!C:=C:\Users\mrdan
!ExitCode=00000000
ALLUSERSPROFILE=C:\ProgramData
ANDROID_HOME=C:\Users\mrdan\AppData\Local\Android\Sdk
APPDATA=C:\Users\mrdan\AppData\Roaming
COMMONPROGRAMFILES=C:\Program Files\Common Files
CommonProgramFiles(x86)=C:\Program Files (x86)\Common Files
CommonProgramW6432=C:\Program Files\Common Files
COMPUTERNAME=DAL_LAPTOP
COMSPEC=C:\WINDOWS\system32\cmd.exe
DriverData=C:\Windows\System32\Drivers\DriverData
EFC_15924=1
HOMEDRIVE=C:
HOMEPATH=\Users\mrdan
IGCCSVC_DB=AQAAANCMnd8BFdERjHoAwE/Cl+sBAAAAO23rTt09XUORfV8Sw1ZASAQAAAACAAAAAAAQZgAAAAEAACAAAABWr+elVTEOIWinn+1STbq6/rDrxL93kPXyoXlE793AHgAAAAAOgAAAAAIAACAAAACLtMBBtIG4zVopiTY9AxFd8wzHL6RHlRO6roxC28AzfmAAAABgDLmsScQihaHPvI1SePUxbtQJP1qmEeZS/8hWjEb35NJa7VEr36zHw1tonrAVlGbVKJ/ZoK9x+8UxtfN7uYiKCPQHka8u2u+0AHAiCmEWZAlhdzB+G34e0nm+3iVLW1BAAAAA844+R1TjoPLxG7JjziGZQIQkARVkrSnDZcE0u1h4qeHtV4ySxT37G55uQkMY1tRpVk2Fw2ZKp1PGF+EQpiZanA==
LOCALAPPDATA=C:\Users\mrdan\AppData\Local
LOGONSERVER=\\DAL_LAPTOP
NIDAQmxSwitchDir=C:\Program Files (x86)\National Instruments\NI-DAQ\Switch\
NIEXTCCOMPILERSUPP=C:\Program Files (x86)\National Instruments\Shared\ExternalCompilerSupport\C\
NUMBER_OF_PROCESSORS=20
OneDrive=C:\Users\mrdan\OneDrive - stevens.edu
OneDriveCommercial=C:\Users\mrdan\OneDrive - stevens.edu
OneDriveConsumer=C:\Users\mrdan\OneDrive
OS=Windows_NT
PATH=/c/WINDOWS/system32:/c/WINDOWS:/c/WINDOWS/System32/Wbem:/c/WINDOWS/System32/WindowsPowerShell/v1.0:/c/WINDOWS/System32/OpenSSH:/c/Program Files/dotnet:/c/Program Files/Microsoft SQL Server/Client SDK/ODBC/110/Tools/Binn:/c/Program Files (x86)/Microsoft SQL Server/120/Tools/Binn:/c/Program Files/Microsoft SQL Server/120/Tools/Binn:/c/Program Files/Microsoft SQL Server/120/DTS/Binn:/c/Program Files (x86)/Windows Kits/8.1/Windows Performance Toolkit:/c/eda/ghdl/bin:/c/eda/gtkwave/bin:/c/Program Files/MATLAB/R2023b/bin:/mingw64/bin:/usr/bin:/c/Users/mrdan/AppData/Local/Microsoft/WindowsApps:/c/Users/mrdan/AppData/Local/Programs/Microsoft VS Code/bin:/c/Users/mrdan/AppData/Local/Android/Sdk/platform-tools:/c/eda/ghdl/bin:/c/eda/gtkwave/bin
PATHEXT=.COM;.EXE;.BAT;.CMD;.VBS;.VBE;.JS;.JSE;.WSF;.WSH;.MSC
PROCESSOR_ARCHITECTURE=AMD64
PROCESSOR_IDENTIFIER=Intel64 Family 6 Model 154 Stepping 3, GenuineIntel
PROCESSOR_LEVEL=6
PROCESSOR_REVISION=9a03
ProgramData=C:\ProgramData
PROGRAMFILES=C:\Program Files
ProgramFiles(x86)=C:\Program Files (x86)
ProgramW6432=C:\Program Files
PROMPT=$P$G
PSModulePath=C:\Program Files\WindowsPowerShell\Modules;C:\WINDOWS\system32\WindowsPowerShell\v1.0\Modules;C:\Program Files (x86)\Microsoft SQL Server\120\Tools\PowerShell\Modules\
PUBLIC=C:\Users\Public
SESSIONNAME=Console
SW_SIM_HYDRA=C:\Program Files\Common Files\SolidWorks Shared\Simulation Worker Agent\
SW_SIM_MPIT=INTELMPI
SW_SIM_TEMP=C:\ProgramData\SOLIDWORKS\SW_net_sim_temp\
SYSTEMDRIVE=C:
SYSTEMROOT=C:\WINDOWS
TEMP=/c/Users/mrdan/AppData/Local/Temp
TMP=/c/Users/mrdan/AppData/Local/Temp
USERDOMAIN=DAL_LAPTOP
USERDOMAIN_ROAMINGPROFILE=DAL_LAPTOP
USERNAME=mrdan
USERPROFILE=C:\Users\mrdan
WINDIR=C:\WINDOWS
ZES_ENABLE_SYSMAN=1
TERM=xterm-256color
HOME=/home/mrdan
```
### ps
```ps
C:\Users\mrdan>ps
      PID    PPID    PGID     WINPID   TTY         UID    STIME COMMAND
     1878       1    1878      37716  cons0     197609 02:19:53 /usr/bin/ps
```
### pwd
```pwd
C:\Users\mrdan>pwd
/c/Users/mrdan
```
<h3 id="git-clone">git clone https://github.com/kevinwlu/iot.git</h3>

```git clone
C:\Users\mrdan>git clone https://github.com/kevinwlu/iot.git
Cloning into 'iot'...
remote: Enumerating objects: 25595, done.
remote: Counting objects: 100% (16/16), done.
remote: Compressing objects: 100% (14/14), done.
remote: Total 25595 (delta 5), reused 0 (delta 0), pack-reused 25579 (from 1)
Receiving objects: 100% (25595/25595), 33.54 MiB | 5.05 MiB/s, done.
Resolving deltas: 100% (16572/16572), done.
Updating files: 100% (408/408), done.
```
### cd iot
```cd iot
C:\Users\mrdan>cd iot

C:\Users\mrdan\iot>
```
### ls
```ls
C:\Users\mrdan\iot>ls
README.md  design     hype      lesson11  lesson4  lesson7  make              standards
apps       economics  lesson1   lesson2   lesson5  lesson8  projects          systems
cases      health     lesson10  lesson3   lesson6  lesson9  special_problems  tools
```
### cd
```cd
C:\Users\mrdan\iot>cd
C:\Users\mrdan\iot
```
### df
```df
C:\Users\mrdan\iot>df
Filesystem     1K-blocks      Used Available Use% Mounted on
C:/msys64      497186812 415980248  81206564  84% /
```
### mkdir demo
```mkdir demo
C:\Users\mrdan\iot>mkdir demo
```
### cd demo
```cd demo
C:\Users\mrdan\iot>cd demo

C:\Users\mrdan\iot\demo>
```
### nano file
```nano file
  GNU nano 5.8                                              file                                                        

























                                                      [ New File ]
^G Help        ^O Write Out   ^W Where Is    ^K Cut         ^T Execute     ^C Location    M-U Undo       M-A Set Mark
^X Exit        ^R Read File   ^\ Replace     ^U Paste       ^J Justify     ^/ Go To Line  M-E Redo       M-6 Copy
```
### cat file
```cat file
C:\Users\mrdan\iot\demo>cat file
Exit
Exit
How do i leave this file?
```
### cp file file1
```cp file file1
C:\Users\mrdan\iot\demo>cp file file1
```
```file1
PS C:\Users\mrdan\iot\demo> cat file1
Exit
Exit
How do i leave this file?
```
### mv file file2
```mv file file2
C:\Users\mrdan\iot\demo>mv file file2
```
```file2
PS C:\Users\mrdan\iot\demo> dir


    Directory: C:\Users\mrdan\iot\demo


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----         4/28/2025   2:36 AM             36 file1
-a----         4/28/2025   2:36 AM             36 file2
```
### rm file2
```rm file2
C:\Users\mrdan\iot\demo>rm file2
```
```file2rm
PS C:\Users\mrdan\iot\demo> dir


    Directory: C:\Users\mrdan\iot\demo


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----         4/28/2025   2:36 AM             36 file1
```
### clear
```clear
C:\Users\mrdan\iot\demo>
```
### man uname
```man uname
C:\Users\mrdan\iot\demo>man uname
'man' is not recognized as an internal or external command,
operable program or batch file.
```
```uname --help
C:\Users\mrdan\iot\demo>uname --help
Usage: uname [OPTION]...
Print certain system information.  With no OPTION, same as -s.

  -a, --all                print all information, in the following order,
                             except omit -p and -i if unknown:
  -s, --kernel-name        print the kernel name
  -n, --nodename           print the network node hostname
  -r, --kernel-release     print the kernel release
  -v, --kernel-version     print the kernel version
  -m, --machine            print the machine hardware name
  -p, --processor          print the processor type (non-portable)
  -i, --hardware-platform  print the hardware platform (non-portable)
  -o, --operating-system   print the operating system
      --help     display this help and exit
      --version  output version information and exit

GNU coreutils online help: <https://www.gnu.org/software/coreutils/>
Report any translation bugs to <https://translationproject.org/team/>
Full documentation <https://www.gnu.org/software/coreutils/uname>
or available locally via: info '(coreutils) uname invocation'
```
### uname -a
```uname -a
C:\Users\mrdan\iot\demo>uname -a
MSYS_NT-10.0-22631 DAL_Laptop 3.3.6-341.x86_64 2022-09-06 08:02 UTC x86_64 Msys
```
### ifconfig
```ifconfig
C:\Users\mrdan\iot\demo>ifconfig
'ifconfig' is not recognized as an internal or external command,
operable program or batch file.
```
```ipconfig
C:\Users\mrdan\iot\demo>ipconfig

Windows IP Configuration


Ethernet adapter vEthernet (Default Switch):

   Connection-specific DNS Suffix  . :
   Link-local IPv6 Address . . . . . : fe80::93b5:d68e:f436:e0d6%29
   IPv4 Address. . . . . . . . . . . : 172.30.112.1
   Subnet Mask . . . . . . . . . . . : 255.255.240.0
   Default Gateway . . . . . . . . . :

Wireless LAN adapter Local Area Connection* 1:

   Media State . . . . . . . . . . . : Media disconnected
   Connection-specific DNS Suffix  . :

Wireless LAN adapter Local Area Connection* 2:

   Media State . . . . . . . . . . . : Media disconnected
   Connection-specific DNS Suffix  . :

Wireless LAN adapter Wi-Fi:

   Connection-specific DNS Suffix  . : campus.stevens-tech.edu
   Link-local IPv6 Address . . . . . : fe80::733a:4570:1497:6d1%14
   IPv4 Address. . . . . . . . . . . : 10.156.3.78
   Subnet Mask . . . . . . . . . . . : 255.255.224.0
   Default Gateway . . . . . . . . . : 10.156.0.1

Ethernet adapter Bluetooth Network Connection:

   Media State . . . . . . . . . . . : Media disconnected
   Connection-specific DNS Suffix  . :
```
### ping localhost
```ping localhost
C:\Users\mrdan\iot\demo>ping localhost

Pinging DAL_Laptop [::1] with 32 bytes of data:
Reply from ::1: time<1ms
Reply from ::1: time<1ms
Reply from ::1: time<1ms
Reply from ::1: time<1ms

Ping statistics for ::1:
    Packets: Sent = 4, Received = 4, Lost = 0 (0% loss),
Approximate round trip times in milli-seconds:
    Minimum = 0ms, Maximum = 0ms, Average = 0ms
```
### netstat
```netstat
C:\Users\mrdan\iot\demo>netstat

Active Connections

  Proto  Local Address          Foreign Address        State
  TCP    10.156.3.78:49414      52.159.127.243:https   ESTABLISHED
  TCP    10.156.3.78:53482      52.159.127.243:https   ESTABLISHED
  TCP    10.156.3.78:53483      52.159.127.243:https   ESTABLISHED
  TCP    10.156.3.78:55555      30:https               ESTABLISHED
  TCP    10.156.3.78:55806      40.78.245.37:8883      ESTABLISHED
  TCP    10.156.3.78:56818      a23-51-58-97:https     CLOSE_WAIT
  TCP    10.156.3.78:57803      a23-44-201-12:https    CLOSE_WAIT
  TCP    10.156.3.78:57834      a23-44-201-15:https    CLOSE_WAIT
  TCP    10.156.3.78:58207      20.75.60.91:https      ESTABLISHED
  TCP    10.156.3.78:61011      162.159.133.234:https  ESTABLISHED
  TCP    10.156.3.78:61063      52.96.88.114:https     TIME_WAIT
  TCP    10.156.3.78:61172      pd-in-f188:5228        ESTABLISHED
  TCP    10.156.3.78:61175      52.96.88.114:https     TIME_WAIT
  TCP    10.156.3.78:61190      lb-140-82-114-21-iad:https  ESTABLISHED
  TCP    10.156.3.78:61203      lb-140-82-113-26-iad:https  ESTABLISHED
  TCP    10.156.3.78:61265      199.250.161.129:https  ESTABLISHED
  TCP    10.156.3.78:61295      199.232.38.248:https   ESTABLISHED
  TCP    10.156.3.78:61304      a23-209-72-139:https   ESTABLISHED
  TCP    10.156.3.78:61310      199.232.38.248:https   ESTABLISHED
  TCP    10.156.3.78:61331      a23-209-72-139:https   ESTABLISHED
  TCP    10.156.3.78:61335      a23-200-0-44:https     ESTABLISHED
  TCP    10.156.3.78:61420      172.66.134.99:https    ESTABLISHED
  TCP    10.156.3.78:61426      lga34s36-in-f8:https   ESTABLISHED
  TCP    10.156.3.78:61432      172.67.34.118:https    TIME_WAIT
  TCP    10.156.3.78:61442      20.189.173.18:https    TIME_WAIT
  TCP    10.156.3.78:61459      sitult:domain          TIME_WAIT
  TCP    10.156.3.78:61460      sitult:domain          TIME_WAIT
  TCP    10.156.3.78:61461      sitult:domain          TIME_WAIT
  TCP    10.156.3.78:61462      sitult:domain          TIME_WAIT
  TCP    10.156.3.78:61465      nrac:domain            TIME_WAIT
  TCP    10.156.3.78:61466      nrac:domain            TIME_WAIT
  TCP    10.156.3.78:61467      nrac:domain            TIME_WAIT
  TCP    10.156.3.78:61468      nrac:domain            TIME_WAIT
  TCP    10.156.3.78:61469      nrac:domain            TIME_WAIT
  TCP    10.156.3.78:61470      nrac:domain            TIME_WAIT
  TCP    10.156.3.78:61471      nrac:domain            TIME_WAIT
  TCP    10.156.3.78:61472      nrac:domain            TIME_WAIT
  TCP    10.156.3.78:61473      9:https                ESTABLISHED
  TCP    10.156.3.78:61474      1drv:https             ESTABLISHED
  TCP    10.156.3.78:61475      nrac:domain            TIME_WAIT
  TCP    10.156.3.78:61476      nrac:domain            TIME_WAIT
  TCP    10.156.3.78:61477      24:https               ESTABLISHED
  TCP    10.156.3.78:61478      nrac:domain            TIME_WAIT
  TCP    10.156.3.78:61479      nrac:domain            TIME_WAIT
  TCP    10.156.3.78:61480      nrac:domain            TIME_WAIT
  TCP    10.156.3.78:61481      nrac:domain            TIME_WAIT
  TCP    10.156.3.78:61482      nrac:domain            TIME_WAIT
  TCP    10.156.3.78:61483      nrac:domain            TIME_WAIT
  TCP    10.156.3.78:61484      20.189.173.18:https    ESTABLISHED
  TCP    10.156.3.78:61485      52.96.88.114:https     ESTABLISHED
  TCP    10.156.3.78:61486      20.190.152.88:https    ESTABLISHED
  TCP    10.156.3.78:61487      20.190.152.88:https    ESTABLISHED
  TCP    10.156.3.78:61488      20.190.152.88:https    ESTABLISHED
  TCP    10.156.3.78:61489      a23-44-201-28:https    ESTABLISHED
  TCP    10.156.3.78:61490      52.96.88.114:https     ESTABLISHED
  TCP    10.156.3.78:61491      13.89.179.9:https      ESTABLISHED
  TCP    10.156.3.78:61492      51.132.193.104:https   ESTABLISHED
  TCP    10.156.3.78:61493      13.107.213.254:https   ESTABLISHED
  TCP    10.156.3.78:61494      172.202.65.254:https   ESTABLISHED
  TCP    10.156.3.78:61495      20.24.15.224:https     ESTABLISHED
  TCP    10.156.3.78:61496      204.79.197.222:https   ESTABLISHED
  TCP    127.0.0.1:49685        DAL_Laptop:49686       ESTABLISHED
  TCP    127.0.0.1:49686        DAL_Laptop:49685       ESTABLISHED
  TCP    127.0.0.1:49692        DAL_Laptop:49801       ESTABLISHED
  TCP    127.0.0.1:49692        DAL_Laptop:53141       ESTABLISHED
  TCP    127.0.0.1:49693        DAL_Laptop:49694       ESTABLISHED
  TCP    127.0.0.1:49694        DAL_Laptop:49693       ESTABLISHED
  TCP    127.0.0.1:49695        DAL_Laptop:49704       ESTABLISHED
  TCP    127.0.0.1:49695        DAL_Laptop:49710       ESTABLISHED
  TCP    127.0.0.1:49695        DAL_Laptop:49712       ESTABLISHED
  TCP    127.0.0.1:49695        DAL_Laptop:49714       ESTABLISHED
  TCP    127.0.0.1:49695        DAL_Laptop:49715       ESTABLISHED
  TCP    127.0.0.1:49695        DAL_Laptop:49806       ESTABLISHED
  TCP    127.0.0.1:49704        DAL_Laptop:49695       ESTABLISHED
  TCP    127.0.0.1:49705        DAL_Laptop:49829       ESTABLISHED
  TCP    127.0.0.1:49705        DAL_Laptop:53148       ESTABLISHED
  TCP    127.0.0.1:49710        DAL_Laptop:49695       ESTABLISHED
  TCP    127.0.0.1:49712        DAL_Laptop:49695       ESTABLISHED
  TCP    127.0.0.1:49714        DAL_Laptop:49695       ESTABLISHED
  TCP    127.0.0.1:49715        DAL_Laptop:49695       ESTABLISHED
  TCP    127.0.0.1:49718        DAL_Laptop:49719       ESTABLISHED
  TCP    127.0.0.1:49719        DAL_Laptop:49718       ESTABLISHED
  TCP    127.0.0.1:49720        DAL_Laptop:61900       ESTABLISHED
  TCP    127.0.0.1:49721        DAL_Laptop:49722       ESTABLISHED
  TCP    127.0.0.1:49722        DAL_Laptop:49721       ESTABLISHED
  TCP    127.0.0.1:49723        DAL_Laptop:49724       ESTABLISHED
  TCP    127.0.0.1:49724        DAL_Laptop:49723       ESTABLISHED
  TCP    127.0.0.1:49725        DAL_Laptop:61900       ESTABLISHED
  TCP    127.0.0.1:49726        DAL_Laptop:49727       ESTABLISHED
  TCP    127.0.0.1:49727        DAL_Laptop:49726       ESTABLISHED
  TCP    127.0.0.1:49728        DAL_Laptop:49729       ESTABLISHED
  TCP    127.0.0.1:49729        DAL_Laptop:49728       ESTABLISHED
  TCP    127.0.0.1:49730        DAL_Laptop:61900       ESTABLISHED
  TCP    127.0.0.1:49731        DAL_Laptop:49732       ESTABLISHED
  TCP    127.0.0.1:49732        DAL_Laptop:49731       ESTABLISHED
  TCP    127.0.0.1:49734        DAL_Laptop:49735       ESTABLISHED
  TCP    127.0.0.1:49735        DAL_Laptop:49734       ESTABLISHED
  TCP    127.0.0.1:49780        DAL_Laptop:49781       ESTABLISHED
  TCP    127.0.0.1:49781        DAL_Laptop:49780       ESTABLISHED
  TCP    127.0.0.1:49799        DAL_Laptop:49800       ESTABLISHED
  TCP    127.0.0.1:49800        DAL_Laptop:49799       ESTABLISHED
  TCP    127.0.0.1:49801        DAL_Laptop:49692       ESTABLISHED
  TCP    127.0.0.1:49802        DAL_Laptop:49803       ESTABLISHED
  TCP    127.0.0.1:49803        DAL_Laptop:49802       ESTABLISHED
  TCP    127.0.0.1:49806        DAL_Laptop:49695       ESTABLISHED
  TCP    127.0.0.1:49829        DAL_Laptop:49705       ESTABLISHED
  TCP    127.0.0.1:49836        DAL_Laptop:49837       ESTABLISHED
  TCP    127.0.0.1:49837        DAL_Laptop:49836       ESTABLISHED
  TCP    127.0.0.1:50379        DAL_Laptop:50380       ESTABLISHED
  TCP    127.0.0.1:50380        DAL_Laptop:50379       ESTABLISHED
  TCP    127.0.0.1:50382        DAL_Laptop:50383       ESTABLISHED
  TCP    127.0.0.1:50383        DAL_Laptop:50382       ESTABLISHED
  TCP    127.0.0.1:50384        DAL_Laptop:50385       ESTABLISHED
  TCP    127.0.0.1:50385        DAL_Laptop:50384       ESTABLISHED
  TCP    127.0.0.1:50386        DAL_Laptop:50387       ESTABLISHED
  TCP    127.0.0.1:50387        DAL_Laptop:50386       ESTABLISHED
  TCP    127.0.0.1:50398        DAL_Laptop:50399       ESTABLISHED
  TCP    127.0.0.1:50399        DAL_Laptop:50398       ESTABLISHED
  TCP    127.0.0.1:50400        DAL_Laptop:50401       ESTABLISHED
  TCP    127.0.0.1:50401        DAL_Laptop:50400       ESTABLISHED
  TCP    127.0.0.1:52066        DAL_Laptop:52067       ESTABLISHED
  TCP    127.0.0.1:52067        DAL_Laptop:52066       ESTABLISHED
  TCP    127.0.0.1:53127        DAL_Laptop:53128       ESTABLISHED
  TCP    127.0.0.1:53128        DAL_Laptop:53127       ESTABLISHED
  TCP    127.0.0.1:53129        DAL_Laptop:61900       ESTABLISHED
  TCP    127.0.0.1:53130        DAL_Laptop:53131       ESTABLISHED
  TCP    127.0.0.1:53131        DAL_Laptop:53130       ESTABLISHED
  TCP    127.0.0.1:53139        DAL_Laptop:53140       ESTABLISHED
  TCP    127.0.0.1:53140        DAL_Laptop:53139       ESTABLISHED
  TCP    127.0.0.1:53141        DAL_Laptop:49692       ESTABLISHED
  TCP    127.0.0.1:53142        DAL_Laptop:53143       ESTABLISHED
  TCP    127.0.0.1:53143        DAL_Laptop:53142       ESTABLISHED
  TCP    127.0.0.1:53148        DAL_Laptop:49705       ESTABLISHED
  TCP    127.0.0.1:53165        DAL_Laptop:53166       ESTABLISHED
  TCP    127.0.0.1:53166        DAL_Laptop:53165       ESTABLISHED
  TCP    127.0.0.1:61900        DAL_Laptop:49720       ESTABLISHED
  TCP    127.0.0.1:61900        DAL_Laptop:49725       ESTABLISHED
  TCP    127.0.0.1:61900        DAL_Laptop:49730       ESTABLISHED
  TCP    127.0.0.1:61900        DAL_Laptop:53129       ESTABLISHED
  TCP    [::1]:49688            DAL_Laptop:49691       ESTABLISHED
  TCP    [::1]:49689            DAL_Laptop:49690       ESTABLISHED
  TCP    [::1]:49690            DAL_Laptop:49689       ESTABLISHED
  TCP    [::1]:49691            DAL_Laptop:49688       ESTABLISHED
  TCP    [::1]:49697            DAL_Laptop:49698       ESTABLISHED
  TCP    [::1]:49698            DAL_Laptop:49697       ESTABLISHED
  TCP    [::1]:49700            DAL_Laptop:49701       ESTABLISHED
  TCP    [::1]:49701            DAL_Laptop:49700       ESTABLISHED
```
---
#### Postscript
- To see the screenshots I took of my Terminal, please go to [the Readme file within SourcesLab2](https://github.com/UsuarioDelNet/EngineeringDesign6/blob/main/Labs/Lab2/SourcesLab2/README.md)
- I pledge my honor that I have abided by the Stevens Honor System: Daniel A. Liss
