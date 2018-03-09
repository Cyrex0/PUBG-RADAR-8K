# PUBG-Radar 

## С компьютера, на котором запущена игра не запускать!

### Скачать скомпилированную версию

https://github.com/FutureXpo/PUBG-RADAR-8K/releases

![Imgur](https://i.imgur.com/9yh84NO.png)

### Небольшая заметка

Нельзя фильтровать третий сет брони и пламегаситель на AR

#### Item Filter - Фильтры:
>NUMPAD_0 -> Filter Weapon - Показать/Скрыть оружие

>NUMPAD_1 -> Filter Attachments - Показать/Скрыть обвесы

>NUMPAD_2 -> Filter Scopes - Показать/Скрыть прицелы

>NUMPAD_3 -> Filter Ammo - Показать/Скрыть патроны

>NUMPAD_4 -> Filter Level 2 - Показать/Скрыть броню второго уровня

>NUMPAD_5 -> Filter Heals - Показать/Скрыть хилы

>NUMPAD_6 -> Filter Grenades - Показать/Скрыть гранаты

>DEL -> Filter Names - Показать/Скрыть имена игроков

#### Zooms:
>NUMPAD_7 -> Driving - Вождение машины с хорошим обзором

>NUMPAD_8 -> Finding a car - Поиск машины со средним обзором

>NUMPAD_9 -> Looting - Лут с большим приближением

>F9 -> Zoom- - Отдалить

>F10 -> Zoom+ - Приблизить

#### UI - Интерфейс:
>F11 -> Players sight - Направление движения



### Online Mode:

`java -jar target\pubg-radar-1.0-SNAPSHOT-jar-with-dependencies.jar 192.168.1.70 PortFilter 192.168.1.67`

### Offline Mode:

`java -jar target\pubg-radar-1.0-SNAPSHOT-jar-with-dependencies.jar 192.168.1.70 PortFilter 192.168.1.67 Offline`

## Build
Using [maven](https://maven.apache.org/) or [JetBrains](https://www.jetbrains.com/idea/)

## Install and Run

1. Install VMWare Workstation
2. Setup your VM in Bridged Mode, replicate physical.
3. Install [Maven](https://maven.apache.org/install.html) on your VM
4. Add Maven to your environment PATH, screenshot below.
4. Add MAVEN_OPTS environment variable, screenshot below.
4. Install [JDK8](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html) on your VM and 
5. Add JAVA_HOME to your Environment Path, screenshot below.
5. Install [Wireshark + WinPCap](https://www.wireshark.org/) on your VM
6. Change your IP addresses in the batch file, It will crash if they are wrong.
7. Do the extra step below in the Compatibility tab in the Properties.
8. Run the batch file.

#### MAVEN_OPTS
![Imgur](https://i.imgur.com/aWCdgUX.png)

#### Path (Java and Maven)
![Imgur](https://i.imgur.com/hSCYrCM.png)

#### JAVA_HOME
![Imgur](https://i.imgur.com/4zT1YNR.png)


#### You can find detailed instructions on how to run a maven project [here](https://maven.apache.org/run.html)

