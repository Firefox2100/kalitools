## CDPSnarf Package Description

CDPSnarf is a network sniffer exclusively written to extract information from CDP packets.
It provides all the information a “show cdp neighbors detail” command would return on a Cisco router and even more.

A feature list follows:

- Time intervals between CDP advertisements
- Source MAC address
- CDP Version
- TTL
- Checksum
- Device ID
- Software version
- Platform
- Addresses
- Port ID
- Capabilities
- Duplex
- Save packets in PCAP dump file format
- Read packets from PCAP dump files
- Debugging information (using the “-d” flag)
- Tested with IPv4 and IPv6

Source: https://github.com/Zapotek/cdpsnarf
[CDPSnarf Homepage](https://github.com/Zapotek/cdpsnarf) | [Kali CDPSnarf Repo](https://gitlab.com/kalilinux/packages/cdpsnarf.git;a=summary)

- Author: Tasos “Zapotek” Laskos
- License: GPLv2

### Tools included in the cdpsnarf package

##### cdpsnarf – Network sniffer to extract CDP information

```
root@kali:~# cdpsnarf -h
CDPSnarf v0.1.6 [$Rev: 797 $] initiated.
  Author: Tasos "Zapotek" Laskos
      <tasos.laskos@gmail.com>
       <zapotek@segfault.gr>
  Website: http://github.com/Zapotek/cdpsnarf

cdpsnarf -i <dev> [-h] [-w savefile] [-r dumpfile] [-d]

  -i    define the interface to sniff on
  -w    write packets to PCAP dump file
  -r    read packets from PCAP dump file
  -d    show debugging information
  -h    show help message and exit
```

### cdpsnarf Usage Example

Sniff on interface ***eth0 (-i)*** and write the capture to a file named ***cdpsnarf.pcap (-w)***:

```
root@kali:~# cdpsnarf -i eth0 -w cdpsnarf.pcap
CDPSnarf v0.1.6 [$Rev: 797 $] initiated.
  Author: Tasos "Zapotek" Laskos
      <tasos.laskos@gmail.com>
       <zapotek@segfault.gr>
  Website: http://github.com/Zapotek/cdpsnarf

Reading packets from eth0.
Waiting for a CDP packet...
```