## WOL-E Package Description

WOL-E is a suite of tools for the Wake on LAN feature of network attached computers, this is now enabled by default on many Apple computers. These tools include:

- Bruteforcing the MAC address to wake up clients
- Sniffing WOL attempts on the network and saving them to disk
- Sniffing WOL passwords on the network and saving them to disk
- Waking up single clients (post sniffing attack)
- Scanning for Apple devices on the network for WOL enabling
- Sending bulk WOL requests to all detected Apple clients

Source: https://code.google.com/p/wol-e/
[WOL-E Homepage](http://code.google.com/p/wol-e/) | [Kali WOL-E Repo](https://gitlab.com/kalilinux/packages/wol-e.git;a=summary)

- Author: Nathaniel Carew
- License: GPLv3

### Tools included in the wol-e package

##### wol-e – Wake on LAN Explorer

```
root@kali:~# wol-e -h

[*] WOL-E 1.0
[*] Wake on LAN Explorer - A collection a WOL tools.
[*] by Nathaniel Carew

  -m
    Waking up single computers.
    If a password is required use the -k 00:12:34:56:78:90 at the end of the above command.
    wol-e -m 00:12:34:56:78:90 -b 192.168.1.255 -p <port> -k <pass>
    Defaults:
    Port: 9
    Broadcast: 255.255.255.255
    Pass: empty

  -s
    Sniffing the network for WOL requests and passwords.
    All captured WOL requests will be displayed on screen and written to /usr/share/wol-e/WOLClients.txt.
    wol-e -s -i eth0

  -a
    Bruteforce powering on WOL clients.
    wol-e -a -p <port>
    Place the address ranges into the bfmac.lst that you wish to bruteforce.
    They should be in the following format:
    00:12:34:56
    Default port: 9

  -f
    Detecting Apple devices on the network for WOL enabling.
    This will output to the screen and write to /usr/share/wol-e/AppleTargets.txt for detected Apple MAC's.
    wol-e -f

  -fa
    Attempt to wake all detected Apple targets in /usr/share/wol-e/AppleTargets.txt.
    This will send a single WOL packet to each client in the list and tell you how many clients were attempted.
    wol-e -fa
```

### wol-e Usage Example

Detect Apple devices on the network ***(-f)***:

```
root@kali:~# wol-e -f

  [*] WOL-E 1.0 [*]
  [*] Wake on LAN Explorer - Scan for Apple devices.

  [*] arping 192.168.1.0/24 on eth0
  [*] Apple device detected: de:ad:be:ef:46:32 192.168.1.12. saving to AppleTargets.txt
```