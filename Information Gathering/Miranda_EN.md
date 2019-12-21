## Miranda Package Description

Miranda is a Python-based Universal Plug-N-Play client application designed to discover, query and interact with UPNP devices, particularly Internet Gateway Devices (aka, routers). It can be used to audit UPNP-enabled devices on a network for possible vulnerabilities. Some of its features include:

- Interactive shell with tab completion and command history
- Passive and active discovery of UPNP devices
- Customizable MSEARCH queries (query for specific devices/services)
- Full control over application settings such as IP addresses, ports and headers
- Simple enumeration of UPNP devices, services, actions and variables
- Correlation of input/output state variables with service actions
- Ability to send actions to UPNP services/devices
- Ability to save data to file for later analysis and collaboration
- Command logging

Miranda was built on and for a Linux system and has been tested on a Linux 2.6 kernel with Python 2.5. However, since it is written in Python, most functionality should be available for any Python-supported platform. Miranda has been tested against IGDs from various vendors, including Linksys, D-Link, Belkin and ActionTec. All Python modules came installed by default on a Linux Mint 5 (Ubuntu 8.04) test system.

Source: https://code.google.com/p/mirandaupnptool/
[Miranda Homepage](http://code.google.com/p/mirandaupnptool/) | [Kali Miranda Repo](https://gitlab.com/kalilinux/packages/miranda.git;a=summary)

- Author: Craig Heffner
- License: MIT

### Tools included in the miranda package

##### miranda – UPNP administration tool

```
root@kali:~# miranda -h

Command line usage: /usr/bin/miranda [OPTIONS]

  -s <struct file>  Load previous host data from struct file
  -l <log file>    Log user-supplied commands to log file
  -i <interface>   Specify the name of the interface to use (Linux only, requires root)
  -u     Disable show-uniq-hosts-only option
  -d     Enable debug mode
  -v     Enable verbose mode
  -h      Show help
```

### miranda Usage Example

Start on interface eth0 ***(-i eth0)*** in verbose mode ***(-v)***, then start discovery mode ***(msearch)***:

```
root@kali:~# miranda -i eth0 -v

Binding to interface eth0 ...

Verbose mode enabled!
upnp> msearch

Entering discovery mode for 'upnp:rootdevice', Ctl+C to stop...

****************************************************************
SSDP notification message from 192.168.1.230:80
XML file is located at http://192.168.1.230:80/description.xml
Device is running FreeRTOS/6.0.5, UPnP/1.0, IpBridge/0.1
```