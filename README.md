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



## Build

* Step 1. Install [Maven](https://maven.apache.org/install.html)
* Step 2. Add Maven to your environment PATH, screenshot below.
* Step 3. Add MAVEN_OPTS environment variable, screenshot below.
* Step 4. Install [JDK8](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)
* Step 5. Add JAVA_HOME to your Environment Path, screenshot below.
* Step 6. Install [Wireshark + WinPCap](https://www.wireshark.org/) on 2nd PC
* Step 7. Use the command prompt to go to your VMRadar directory (with the src folder)
* Step 8. type `mvn verify install` into the command prompt.

----------------- 
#### MAVEN_OPTS
![Imgur](https://i.imgur.com/aWCdgUX.png)

#### Path (Java and Maven)
![Imgur](https://i.imgur.com/hSCYrCM.png)

#### JAVA_HOME
![Imgur](https://i.imgur.com/4zT1YNR.png)


#### You can find detailed instructions on how to run a maven project [here](https://maven.apache.org/run.html)

[IntelliJ IDEA](https://www.jetbrains.com/idea/?fromMenu)

## Install
VM Install - https://www.youtube.com/watch?v=zwe4xDQOAfg

#### On 2nd PC or VMWARE: (This is the pc that will run the radar)
* Step 1. Search and run "cmd" - This should open the command prompt. 
* Step 2. type "ipconfig" and press enter.
* Step 3. Take note of your IPv4 address for VPN Settings on gaming pc. 
* Step 4. Take note of your default gateway. 
* Step 5. Search and run "ncpa.cpl"
* Step 6. Right click your primary internet adapter, then click properties.
* Step 7. Select "Internet Protocol Version 4 (TCP/IPv4)" 
* Step 8. Use "Obatain an IP address automatically" and "Obtain 
DNS server address automatically"
* Step 9. Click "OK"
* Step 10. Uncheck "Internet Protocol Version 6 (TCP/IPv6)
* Step 11. Click OK. - The PC may need up to 10 minutes for settings to refresh.
* Step 12. On your keyboard, Press ALT - File will now appear on the top left.
* Step 13. Click File, Then click "New Incoming Connection"
* Step 14. Add someone (bottom left) - Make username and password - click ok - Then click Next.
* Step 15. Checkmark "Through the Internet" - Then click Next.
* Step 16. Select "Internet Protocol Version 4 (Already selected by default, make sure it is checkmarked" Then select "properties"
* Step 17. Make sure "Network Access" is checked
* Step 18. Under "IP address assignment" Check "Specifiy IP Addresses" 
* Step 19. Use your Default Gateway from earlier, to create a proper IP range for "Specify IP addresses"
For instance: if gateway is 192.168.0.1 - use 192.168.0.2 to 192.168.0.10 for 
the ip range. - Then select "OK"
* Step 20. Select Allow Access
* Step 21. DONE. Now to setup the Gaming PC.

#### On Gaming PC: (This is the PC that will run PUBG)

* Step 1. Search and run "ncpa.cpl"
* Step 2. Right click your primary internet adapter, then click properties.
* Step 3. Select "Internet Protocol Version 4 (TCP/IPv4)" 
* Step 4. Use "Obtain an IP address automatically" and "Obtain DNS server address automatically"
* Step 5. Click "OK"
* Step 6. Uncheck "Internet Protocol Version 6 (TCP/IPv6)
* Step 7. Click OK. - The PC may need up to 10 minutes for settings to refresh. Now close out the "Network Connections" window.
* Step 8. Click your windows button (default location bottom left)
* Step 9. Click the settings cog
* Step 10. Click "Network & Internet"
* Step 11. Click "VPN" on left side
* Step 12. Click "Add a VPN Connection" on the top
* Step 13. Use these settings:
VPN Provider: Windows (built-in)
Connection name: Random name
Server name or address: Insert 2nd PC IPv4 address from cmd prompt on 2nd pc
VPN type: PPTP
User name: User you made on incoming connections on 2nd pc
Password: Password you made on incoming connections on 2nd pc
Click Save.
* Step 14. Connect to the VPN that you created.
* Step 15. If you were able to connect, you are done!

Credits: Windows x64 (https://www.unknowncheats.me/forum/2019485-post220.html)

#### Or use openvpn
https://community.openvpn.net/openvpn/wiki/Easy_Windows_Guide

----------------- 
## Run

### Online Mode:
`java -jar target\pubg-radar-1.0-SNAPSHOT-jar-with-dependencies.jar "Middle PC IP" PortFilter "Game PC IP"`

### Offline Mode:
You can replay a PCAP file in offline mode:

`java -jar target\pubg-radar-1.0-SNAPSHOT-jar-with-dependencies.jar "Middle PC IP" PortFilter "Game PC IP" Offline`

#### Bat with auto get ipv4 on middle pc
```
@echo off
for /f "tokens=14" %%a in ('ipconfig ^| findstr IPv4') do set _IPaddr=%%a
echo YOUR IP ADDRESS IS: %_IPaddr%
echo "RUNNING VMRADAR"
set /p game=ENTER GAMEVM IP:
echo "%game%"
java -jar target\pubg-radar-1.0-SNAPSHOT-jar-with-dependencies.jar %_IPaddr% PortFilter "%game%"
```
or 

```
@echo off
for /f "tokens=14" %%a in ('ipconfig ^| findstr IPv4') do set _IPaddr=%%a
java -jar target\pubg-radar-1.0-SNAPSHOT-jar-with-dependencies.jar %_IPaddr% PortFilter %_IPaddr% Offline

```
