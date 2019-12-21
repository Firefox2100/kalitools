## ace-voip Package Description

ACE (Automated Corporate Enumerator) is a simple yet powerful VoIP Corporate Directory enumeration tool that mimics the behavior of an IP Phone in order to download the name and extension entries that a given phone can display on its screen interface. In the same way that the “corporate directory” feature of VoIP hardphones enables users to easily dial by name via their VoIP handsets, ACE was developed as a research idea born from “VoIP Hopper” to automate VoIP attacks that can be targeted against names in an enterprise Directory. The concept is that in the future, attacks will be carried out against users based on their name, rather than targeting VoIP traffic against random RTP audio streams or IP addresses. ACE works by using DHCP, TFTP, and HTTP in order to download the VoIP corporate directory. It then outputs the directory to a text file, which can be used as input to other VoIP assessment tools.

Source: http://ucsniff.sourceforge.net/ace.html
[ace-voip Homepage](http://ucsniff.sourceforge.net/ace.html) | [Kali ace-voip Repo](https://gitlab.com/kalilinux/packages/ace-voip.git;a=summary)

- Author: Sipera VIPER Lab
- License: GPLv3

### Tools included in the ace-voip package

##### ace – A simple VoIP corporate directory enumeration tool

```
root@kali:~# ace
ACE v1.10: Automated Corporate (Data) Enumerator
Usage: ace [-i interface] [ -m mac address ] [ -t tftp server ip address | -c cdp mode | -v voice vlan id | -r vlan interface | -d verbose mode ]

-i (Mandatory) Interface for sniffing/sending packets
-m (Mandatory) MAC address of the victim IP phone
-t (Optional) tftp server ip address
-c (Optional) 0 CDP sniff mode, 1 CDP spoof mode
-v (Optional) Enter the voice vlan ID
-r (Optional) Removes the VLAN interface
-d (Optional) Verbose | debug mode

Example Usages:
Usage requires MAC Address of IP Phone supplied with -m option
Usage: ace -t -m

Mode to automatically discover TFTP Server IP via DHCP Option 150 (-m)
Example: ace -i eth0 -m 00:1E:F7:28:9C:8e

Mode to specify IP Address of TFTP Server
Example: ace -i eth0 -t 192.168.10.150 -m 00:1E:F7:28:9C:8e

Mode to specify the Voice VLAN ID
Example: ace -i eth0 -v 96 -m 00:1E:F7:28:9C:8E

Verbose mode
Example: ace -i eth0 -v 96 -m 00:1E:F7:28:9C:8E -d

Mode to remove vlan interface
Example: ace -r eth0.96

Mode to auto-discover voice vlan ID in the listening mode for CDP
Example: ace -i eth0 -c 0 -m 00:1E:F7:28:9C:8E

Mode to auto-discover voice vlan ID in the spoofing mode for CDP
Example: ace -i eth0 -c 1 -m 00:1E:F7:28:9C:8E
```

### ace Usage Example

```
root@kali:~# coming soon
```