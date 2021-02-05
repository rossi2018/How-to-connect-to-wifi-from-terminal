
How to Connect to WiFi from the Terminal in Ubuntu Linux
=
In this tutorial, I’ll show the steps to connect to WiFi using terminal in Ubuntu Linux. 

## Connect to WiFi from terminal in Ubuntu

It is easy when you are using Ubuntu desktop because you have the GUI to easily do that. It’s not the same when you are using Ubuntu server and restricted to the command line.

## Network Manager
NetworkManager is a program for providing detection and configuration for systems to automatically connect to networks. NetworkManager's functionality can be useful for both wireless and wired networks. For wireless networks, NetworkManager prefers known wireless networks and has the ability to switch to the most reliable network. NetworkManager-aware applications can switch from online and offline mode. NetworkManager also prefers wired connections over wireless ones, has support for modem connections and certain types of VPN. NetworkManager was originally developed by Red Hat and now is hosted by the GNOME project.

## Installation
NetworkManager can be installed with the package networkmanager, which contains a daemon, a command line interface ``(nmcli) `` and a curses‐based interface ``(nmtui)``.

## Enable NetworkManager

After installation, you should *start/enable*  ``NetworkManager.service``. Once the NetworkManager daemon is started, it will automatically connect to any available "system connections" that have already been configured. Any "user connections" or unconfigured connections will need nmcli or an applet to configure and connect.

## Usage of NetworkManager
NetworkManager comes with ``nmcli(1)`` and ``nmtui(1).``

##  nmcli examples
1. List nearby Wi-Fi networks:
``$ nmcli device wifi list``

2. Connect to a Wi-Fi network:  `$ nmcli device wifi connect  <SSID or BSSID> password <password>`

3. Connect to a hidden Wi-Fi network:  `$ nmcli device wifi connect <SSID_or_BSSID> password <password> hidden yes`
4. Connect to a Wi-Fi on the *wlan1* interface: `$ nmcli device wifi connect <SSID_or_BSSID> password <password> ifname wlan1 <profile_name>`

5. Disconnect an interface: `$ nmcli device disconnect ifname eth0`

6. Get a list of connections with their names, UUIDs, types and backing devices: `$ nmcli connection show`

7. Activate a connection (i.e. connect to a network with an existing profile): `$ nmcli connection up <name_or_uuid>`

8. Delete a connection: `$ nmcli connection delete <name_or_uuid>`

9. See a list of network devices and their state: `$ nmcli device`

10. Turn off Wi-Fi: `$ nmcli radio wifi off`


If you want to connect to a network called *PrettyFlyForAWiFi-5G*
`$ nmcli -a d wifi connect PrettyFlyForAWiFi-5G `

*-a* (or *--ask*) means it will ask you for the password. The connection will be saved and should connect automatically if you restart your computer.

You could append `password <your password> `to the end (the literal word `password` followed by the actual password)

`$ nmcli d wifi connect PrettyFlyForAWiFi-5G password 12345678`
