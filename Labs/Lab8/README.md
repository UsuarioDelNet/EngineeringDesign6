# Engineering Design VI `CPE 322-A`
## Lab 8 — Data Analysis
---

- [`pip installs`](#1)
- [`running examples`](#2)
- [`running cpudata graphs`](#2)

To go to the postscript, click [`HERE`](#100)

---
<h3 id="1">pip installs</h3>

```
C:\Users\mrdan>docker pull tensorflow/tensorflow
Using default tag: latest
error during connect: Post "http://%2F%2F.%2Fpipe%2FdockerDesktopLinuxEngine/v1.49/images/create?fromImage=docker.io%2Ftensorflow%2Ftensorflow&tag=latest": open //./pipe/dockerDesktopLinuxEngine: The system cannot find the file specified.

C:\Users\mrdan>docker pull tensorflow/tensorflow:latest-py3
latest-py3: Pulling from tensorflow/tensorflow
Digest: sha256:14ec674cefd622aa9d45f07485500da254acaf8adfef80bd0f279db03c735689
Status: Image is up to date for tensorflow/tensorflow:latest-py3
docker.io/tensorflow/tensorflow:latest-py3

C:\Users\mrdan>docker run -it tensorflow/tensorflow bash

________                               _______________
___  __/__________________________________  ____/__  /________      __
__  /  _  _ \_  __ \_  ___/  __ \_  ___/_  /_   __  /_  __ \_ | /| / /
_  /   /  __/  / / /(__  )/ /_/ /  /   _  __/   _  / / /_/ /_ |/ |/ /
/_/    \___//_/ /_//____/ \____//_/    /_/      /_/  \____/____/|__/


WARNING: You are running this container as root, which can cause new files in
mounted volumes to be created as the root user on your host machine.

To avoid this, run the container by specifying your user's userid:

$ docker run -u $(id -u):$(id -g) args...

root@edf037135e0e:/# apt update
... [Too long to include the entire setup process here]
```



<h3 id="2">running examples</h3>


```
PS C:\Users\mrdan\iot\lesson8> python pyplot_simple.py
Matplotlib is building the font cache; this may take a moment.
```
![pyplotsimple](https://github.com/UsuarioDelNet/EngineeringDesign6/blob/main/Labs/Lab8/SourcesLab8/pyplotSimple.png)

```
PS C:\Users\mrdan\iot\lesson8> python simple_plot.py
```
![simpleplot](https://github.com/UsuarioDelNet/EngineeringDesign6/blob/main/Labs/Lab8/SourcesLab8/simplePlot.png)

```
PS C:\Users\mrdan\iot\lesson8> python pyplot_formatstr.py
```
![formastr](https://github.com/UsuarioDelNet/EngineeringDesign6/blob/main/Labs/Lab8/SourcesLab8/pyplotFormatstr.png)

```
PS C:\Users\mrdan\iot\lesson8> python ticklabels_demo_rotation.py
```
![tickLab](https://github.com/UsuarioDelNet/EngineeringDesign6/blob/main/Labs/Lab8/SourcesLab8/tickLablesDemo.png)

```
PS C:\Users\mrdan\iot\lesson8> python pyplot_three.py
```
![3](https://github.com/UsuarioDelNet/EngineeringDesign6/blob/main/Labs/Lab8/SourcesLab8/pyplot3.png)

```
PS C:\Users\mrdan\iot\lesson8> python pyplot_two_subplots.py
```
![2sub](https://github.com/UsuarioDelNet/EngineeringDesign6/blob/main/Labs/Lab8/SourcesLab8/python2sub.png)

```
PS C:\Users\mrdan\iot\lesson8> python major_minor_demo1.py
```
![2sub](https://github.com/UsuarioDelNet/EngineeringDesign6/blob/main/Labs/Lab8/SourcesLab8/majMin.png)

```
PS C:\Users\mrdan\iot\lesson8> python titanic_1.py
Data Columns:
Index(['PassengerId', 'Survived', 'Pclass', 'Name', 'Sex', 'Age', 'SibSp',
       'Parch', 'Ticket', 'Fare', 'Cabin', 'Embarked'],
      dtype='object')
Survived:
Sex
female    0.742038
male      0.188908
Name: Survived, dtype: float64
```
![titanic](https://github.com/UsuarioDelNet/EngineeringDesign6/blob/main/Labs/Lab8/SourcesLab8/titanic1.png)

```
PS C:\Users\mrdan\iot\lesson8> python titanic_2.py
Survived:
Sex     Pclass
female  1         0.968085
        2         0.921053
        3         0.500000
male    1         0.368852
        2         0.157407
        3         0.135447
Name: Survived, dtype: float64
Number of Missing Fare: 1
C:\Users\mrdan\iot\lesson8\titanic_2.py:28: DeprecationWarning: Conversion of an array with ndim > 0 to a scalar is deprecated, and will error in future. Ensure you extract a single element from your array before performing this operation. (Deprecated NumPy 1.25.)
  print('Indices of Missing Fare: %d' % (wh_badfare))
Indices of Missing Fare: 152
Survived:
Sex     Pclass  Fare_Bracket
female  1       2               0.833333
                3               0.977273
        2       1               0.914286
                2               0.900000
                3               1.000000
        3       0               0.593750
                1               0.581395
                2               0.333333
                3               0.125000
male    1       0               0.000000
                2               0.400000
                3               0.383721
        2       0               0.000000
                1               0.158730
                2               0.160000
                3               0.214286
        3       0               0.111538
                1               0.236842
                2               0.125000
                3               0.240000
Name: Survived, dtype: float64
```


<h3 id="3">running cpudata graphs</h3>

![4graph](https://github.com/UsuarioDelNet/EngineeringDesign6/blob/main/Labs/Lab8/SourcesLab8/4graphs.png)

```
PS C:\Users\mrdan\iot\demo> cp C:\Users\mrdan\Downloads\cpudata.csv
PS C:\Users\mrdan\iot\demo> cp ~/iot/lesson8/plt_final.py
PS C:\Users\mrdan\iot\demo> cp ~/iot/lesson8/plt_cv2.py
PS C:\Users\mrdan\iot\demo> ls


    Directory: C:\Users\mrdan\iot\demo


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----          5/9/2025   8:19 AM                __pycache__
-a----          5/8/2025  11:50 PM             44 API_KEY.pickle
-a----          5/9/2025   8:33 AM           2350 cpudata-459312-429f0b20086c.json
-a----          5/9/2025   6:00 PM            482 cpudata.csv
-a----          5/9/2025   8:46 AM           2133 cpu_spreadsheet.py
-a----         4/28/2025   2:36 AM             36 file1
-a----         4/28/2025   2:26 AM            560 plt_cv2.py
-a----         4/28/2025   2:26 AM           1467 plt_final.py
-a----         4/28/2025   2:26 AM           2490 system_info.py
-a----         4/28/2025   2:26 AM            981 thingspeak_cpu_loop.py
-a----         4/28/2025   2:26 AM           2533 thingspeak_feed.py
```
```
PS C:\Users\mrdan\iot\demo> python plt_final.py
C:\Users\mrdan\iot\demo\plt_final.py:35: MatplotlibDeprecationWarning: Passing the notch parameter of boxplot() positionally is deprecated since Matplotlib 3.9; the parameter will become keyword-only in 3.11.
  plt.boxplot(x, 0, '+', 0)
C:\Users\mrdan\iot\demo\plt_final.py:41: MatplotlibDeprecationWarning: Passing the notch parameter of boxplot() positionally is deprecated since Matplotlib 3.9; the parameter will become keyword-only in 3.11.
  plt.boxplot(y, 0, '+')
```
![1](https://github.com/UsuarioDelNet/EngineeringDesign6/blob/main/Labs/Lab8/SourcesLab8/timeSeriesMiddleLegend.png)
![2](https://github.com/UsuarioDelNet/EngineeringDesign6/blob/main/Labs/Lab8/SourcesLab8/memAvaGB.png)
![3](https://github.com/UsuarioDelNet/EngineeringDesign6/blob/main/Labs/Lab8/SourcesLab8/cpusageH.png)
![4](https://github.com/UsuarioDelNet/EngineeringDesign6/blob/main/Labs/Lab8/SourcesLab8/horzBox.png)
![5](https://github.com/UsuarioDelNet/EngineeringDesign6/blob/main/Labs/Lab8/SourcesLab8/VertBox.png)
![6](https://github.com/UsuarioDelNet/EngineeringDesign6/blob/main/Labs/Lab8/SourcesLab8/scatterDig.png)

```
PS C:\Users\mrdan\iot\demo> python plt_cv2.py
```
![cv2](https://github.com/UsuarioDelNet/EngineeringDesign6/blob/main/Labs/Lab8/SourcesLab8/cv2.png)

---
<h4 id="100">Postscript</h4>

- All my source files were initially obtained in [`Dr. Lu's GitHub`](https://github.com/kevinwlu/iot/tree/master/lesson4)
- Please note, I replaced all the instances of "python3" with "python" in the commands for the lab, as I had Python downloaded on my system already.
- I pledge my honor that I have abided by the Stevens Honor System: Daniel A. Liss
