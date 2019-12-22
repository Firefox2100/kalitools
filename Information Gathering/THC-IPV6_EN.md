## THC-IPV6 Package Description

A complete tool set to attack the inherent protocol weaknesses of IPV6 and ICMP6, and includes an easy to use packet factory library.

Source: https://www.thc.org/thc-ipv6/
[THC-IPV6 Homepage](https://www.thc.org/thc-ipv6/) | [Kali THC-IPV6 Repo](https://gitlab.com/kalilinux/packages/thc-ipv6.git;a=summary)

- Author: The Hacker’s Choice
- License: AGPLv3

### Tools included in the thc-ipv6 package

### address6 – Converts a mac or ipv4 address to an ipv6 address

```
root@kali:~# address6
address6 v2.3 (c) 2013 by van Hauser / THC <vh@thc.org> www.thc.org

Syntax:
  address6 mac-address [ipv6-prefix]
  address6 ipv4-address [ipv6-prefix]
  address6 ipv6-address

Converts a mac or ipv4 address to an ipv6 address (link local if no prefix is
given as 2nd option) or, when given an ipv6 address, prints the mac or ipv4
address. Prints all possible variations. Returns -1 on errors or the number of
variations found
```

### alive6 – Shows alive addresses in the segment

```
root@kali:~# alive6
alive6 v2.3 (c) 2013 by van Hauser / THC <vh@thc.org> www.thc.org

Syntax: alive6 [-I srcip6] [-i file] [-o file] [-DM] [-p] [-F] [-e opt] [-s port,..] [-a port,..] [-u port,..] [-W TIME] [-dlrvS] interface [unicast-or-multicast-address [remote-router]]

Shows alive addresses in the segment. If you specify a remote router, the
packets are sent with a routing header prefixed by fragmentation
Options:
 -i file   check systems from input file
 -o file   write results to output file
 -M     enumerate hardware addresses (MAC) from input addresses (slow!)
 -D     enumerate DHCP address space from input addresses
 -p     send a ping packet for alive check (default)
 -e dst,hop send an errornous packets: destination (default), hop-by-hop
 -s port,port,..  TCP-SYN packet to ports for alive check
 -a port,port,..  TCP-ACK packet to ports for alive check
 -u port,port,..  UDP packet to ports for alive check
 -d     DNS resolve alive ipv6 addresses
 -n number  how often to send each packet (default: local 1, remote 2)
 -W time   time in ms to wait after sending a packet (default: 1)
 -S     slow mode, get best router for each remote target or when proxy-NA
 -I srcip6  use the specified IPv6 address as source
 -l     use link-local address instead of global address
 -v     verbose (twice: detailed information, thrice: dumping all packets)
Target address on command line or in input file can include ranges in the form
of 2001:db8::1-fff or 2001:db8::1-2:0-ffff:0:0-ffff, etc.
Returns -1 on errors, 0 if a system was found alive or 1 if nothing was found.
```

### covert_send6 – Sends the content of FILE covertly to the target

```
root@kali:~# covert_send6
covert_send6 v2.3 (c) 2013 by van Hauser / THC <vh@thc.org> www.thc.org

Syntax: covert_send6 [-m mtu] [-k key] [-s resend] interface target file [port]

Options:
 -m mtu   specifies the maximum MTU (default: interface MTU, min: 1000)
 -k key   encrypt the content with Blowfish-160
 -s resend  send each packet RESEND number of times, default: 1

Sends the content of FILE covertly to the target, And its POC - dont except
too much sophistication - its just put into the destination header.
```

### covert_send6d – Writes covertly received content to FILE

```
root@kali:~# covert_send6d
covert_send6d v2.3 (c) 2013 by van Hauser / THC <vh@thc.org> www.thc.org

Syntax: covert_send6d [-k key] interface file

Options:
 -k key   decrypt the content with Blowfish-160

Writes covertly received content to FILE.
```

### denial6 – Performs various denial of service attacks on a target

```
root@kali:~# denial6
denial6 v2.3 (c) 2013 by van Hauser / THC <vh@thc.org> www.thc.org

Syntax: denial6 interface destination test-case-number

Performs various denial of service attacks on a target
If a system is vulnerable, it can crash or be under heavy load, so be careful!
If not test-case-number is supplied, the list of shown.
```

### detect-new-ip6 – This tools detects new ipv6 addresses joining the local network

```
root@kali:~# detect-new-ip6
detect-new-ip6 v2.3 (c) 2013 by van Hauser / THC <vh@thc.org> www.thc.org

Syntax: detect-new-ip6 interface [script]

This tools detects new ipv6 addresses joining the local network.
If script is supplied, it is executed with the detected IPv6 address as first
and the interface as second command line option.
```

### detect_sniffer6 – Tests if systems on the local LAN are sniffing

```
root@kali:~# detect_sniffer6
detect_sniffer6 v2.3 (c) 2013 by van Hauser / THC <vh@thc.org> www.thc.org

Syntax: detect_sniffer6 interface [target6]

Tests if systems on the local LAN are sniffing.
Works against Windows, Linux, OS/X and *BSD
If no target is given, the link-local-all-nodes address is used, which
however rarely works.
```

### dnsdict6 – Enumerates a domain for DNS entries

```
root@kali:~# dnsdict6
dnsdict6 v2.3 (c) 2013 by van Hauser / THC <vh@thc.org> www.thc.org

Syntax: dnsdict6 [-d46] [-s|-m|-l|-x] [-t THREADS] [-D] domain [dictionary-file]

Enumerates a domain for DNS entries, it uses a dictionary file if supplied
or a built-in list otherwise. This tool is based on dnsmap by gnucitizen.org.

Options:
 -4    also dump IPv4 addresses
 -t NO  specify the number of threads to use (default: 8, max: 32).
 -D    dump the selected built-in wordlist, no scanning.
 -d    display IPv6 information on NS and MX DNS domain information.
 -S    perform SRV service name guessing
 -[smlx] choose the dictionary size by -s(mall=50), -m(edium=796) (DEFAULT)
      -l(arge=1416), or -x(treme=3211)
```

### dnsrevenum6 – Performs a fast reverse DNS enumeration and is able to cope with slow servers

```
root@kali:~# dnsrevenum6
dnsrevenum6 v2.3 (c) 2013 by van Hauser / THC <vh@thc.org> www.thc.org

Syntax: dnsrevenum6 dns-server ipv6address

Performs a fast reverse DNS enumeration and is able to cope with slow servers.
Examples:
 dnsrevenum6 dns.test.com 2001:db8:42a8::/48
 dnsrevenum6 dns.test.com 8.a.2.4.8.b.d.0.1.0.0.2.ip6.arpa
```

### dnssecwalk – Perform DNSSEC NSEC walking

```
root@kali:~# dnssecwalk
dnssecwalk v1.2 (c) 2013 by Marc Heuse <mh@mh-sec.de> http://www.mh-sec.de

Syntax: dnssecwalk [-e46] dns-server domain

Options:
 -e  ensure that the domain is present in found addresses, quit otherwise
 -4  resolve found entries to IPv4 addresses
 -6  resolve found entries to IPv6 addresses

Perform DNSSEC NSEC walking.

Example: dnssecwalk dns.test.com test.com
```

### dos-new-ip6 – This tools prevents new ipv6 interfaces to come up

```
root@kali:~# dos-new-ip6
dos-new-ip6 v2.3 (c) 2013 by van Hauser / THC <vh@thc.org> www.thc.org

Syntax: dos-new-ip6 interface

This tools prevents new ipv6 interfaces to come up, by sending answers to
duplicate ip6 checks (DAD). This results in a DOS for new ipv6 devices.
```

### dump_router6 – Dumps all local routers and their information

```
root@kali:~# dump_router6
dump_router6 v2.3 (c) 2013 by van Hauser / THC <vh@thc.org> www.thc.org

Syntax: dump_router6 interface

Dumps all local routers and their information
```

### exploit6 – Performs exploits of various CVE known IPv6 vulnerabilities on the destination

```
root@kali:~# exploit6
exploit6 v2.3 (c) 2013 by van Hauser / THC <vh@thc.org> www.thc.org

Syntax: exploit6 interface destination [test-case-number]

Performs exploits of various CVE known IPv6 vulnerabilities on the destination
Note that for exploitable overflows only 'AAA...' strings are used.
If a system is vulnerable, it will crash, so be careful!
```

### extract_hosts6.sh – prints the host parts of IPv6 addresses in FILE

```
root@kali:~# extract_hosts6.sh
/usr/bin/extract_hosts6.sh FILE
prints the host parts of IPv6 addresses in FILE
```

### extract_networks6.sh – prints the networks found in FILE

```
root@kali:~# extract_networks6.sh
/usr/bin/extract_networks6.sh FILE
prints the networks found in FILE
```

### fake_advertise6 – Advertise ipv6 address on the network

```
root@kali:~# fake_advertise6
fake_advertise6 v2.3 (c) 2013 by van Hauser / THC <vh@thc.org> www.thc.org

Syntax: fake_advertise6 [-DHF] [-Ors] [-n count] [-w seconds] interface ip-address-advertised [target-address [mac-address-advertised [source-ip-address]]]

Advertise ipv6 address on the network (with own mac if not specified),
sending it to the all-nodes multicast address if no target address is set.
Source ip addresss is the address advertised if not set.

Sending options:
 -n count   send how many packets (default: forever)
 -w seconds  wait time between the packets sent (default: 5)
Flag options:
 -O  do NOT set the override flag (default: on)
 -r  DO set the router flag (default: off)
 -s  DO set the solicitate flag (default: off)
ND Security evasion options (can be combined):
 -H  add a hop-by-hop header
 -F  add a one shot fragment header (can be specified multiple times)
 -D  add a large destination header which fragments the packet.
```

### fake_dhcps6 – Fake DHCPv6 server

```
root@kali:~# fake_dhcps6
fake_dhcps6 v2.3 (c) 2013 by van Hauser / THC <vh@thc.org> www.thc.org

Syntax: fake_dhcps6 interface network-address/prefix-length dns-server [dhcp-server-ip-address [mac-address]]

Fake DHCPv6 server. Use to configure an address and set a DNS server
```

### fake_dns6d – Fake DNS server that serves the same ipv6 address to any lookup request

```
root@kali:~# fake_dns6d
fake_dns6d v2.3 (c) 2013 by van Hauser / THC <vh@thc.org> www.thc.org

Syntax: fake_dns6d interface ipv6-address [fake-ipv6-address [fake-mac]]
Fake DNS server that serves the same ipv6 address to any lookup request
You can use this together with parasite6 if clients have a fixed DNS server
Note: very simple server. Does not honor multiple queries in a packet, norNS, MX, etc. lookups.
```

### fake_dnsupdate6 – Fake DNS updater

```
root@kali:~# fake_dnsupdate6
fake_dnsupdate6 v2.3 (c) 2013 by van Hauser / THC <vh@thc.org> www.thc.org

Syntax: fake_dnsupdate6 dns-server full-qualified-host-dns-name ipv6address

Example: fake_dnsupdate6 dns.test.com myhost.sub.test.com ::1
```

### fake_mipv6 – Will redirect all packets for home-address to care-of-address

```
root@kali:~# fake_mipv6
fake_mipv6 v2.3 (c) 2013 by van Hauser / THC <vh@thc.org> www.thc.org

Syntax: fake_mipv6 interface home-address home-agent-address care-of-address

If the mobile IPv6 home-agent is mis-configured to accept MIPV6 updates without
IPSEC, this will redirect all packets for home-address to care-of-address
```

### fake_mld26

```
root@kali:~# fake_mld26
fake_mld26 v2.3 (c) 2013 by van Hauser / THC <vh@thc.org> www.thc.org

Syntax: fake_mld26 [-l] interface add|delete|query [multicast-address [target-address [ttl [own-ip [own-mac-address [destination-mac-address]]]]]]

This uses the MLDv2 protocol. Only a subset of what the protocol is able to
do is possible to implement via a command line. Code it if you need something.
Ad(d)vertise or delete yourself - or anyone you want - in a multicast group of your choice
Query ask on the network who is listening to multicast addresses
Use -l to loop and send (in 5s intervals) until Control-C is pressed.
```

### fake_mld6 – Ad(d)vertise or delete yourself – or anyone you want

```
root@kali:~# fake_mld6
fake_mld6 v2.3 (c) 2013 by van Hauser / THC <vh@thc.org> www.thc.org

Syntax: fake_mld6 [-l] interface add|delete|query [multicast-address [target-address [ttl [own-ip [own-mac-address [destination-mac-address]]]]]]

Ad(d)vertise or delete yourself - or anyone you want - in a multicast group of your choice
Query ask on the network who is listening to multicast addresses
Use -l to loop and send (in 5s intervals) until Control-C is pressed.
```

### fake_mldrouter6 – Announce, delete or soliciated MLD router

```
root@kali:~# fake_mldrouter6
fake_mldrouter6 v2.3 (c) 2013 by van Hauser / THC <vh@thc.org> www.thc.org

Syntax: fake_mldrouter6 [-l] interface advertise|solicitate|terminate [own-ip [own-mac-address]]

Announce, delete or soliciated MLD router - yourself or others.
Use -l to loop and send (in 5s intervals) until Control-C is pressed.
```

### fake_pim6

```
root@kali:~# fake_pim6
fake_pim6 v2.3 (c) 2013 by van Hauser / THC <vh@thc.org> www.thc.org

Syntax:
 fake_pim6 [-t ttl] [-s src6] [-d dst6] interface hello [dr_priority]
 fake_pim6 [-t ttl] [-s src6] [-d dst6] interface join|prune neighbor6 multicast6 target6

The hello command takes optionally the DR priority (default: 0).
The join and prune commands need the multicast group to modify, the target
address that joins or leavs and the neighbor PIM router
Use -s to spoof the source ip6, -d to send to another address than ff02::d,
and -t to set a different TTL (default: 1)
```

### fake_router26 – Announce yourself as a router and try to become the default router

```
root@kali:~# fake_router26
fake_router26 v2.3 (c) 2013 by van Hauser / THC <vh@thc.org> www.thc.org

Syntax: fake_router26 [-E type] [-A network/prefix] [-R network/prefix] [-D dns-server] [-s sourceip] [-S sourcemac] [-ardl seconds] [-Tt ms] [-n no] [-i interval] interface

Options:
 -A network/prefix  add autoconfiguration network (up to 16 times)
 -a seconds     valid lifetime of prefix -A (defaults to 99999)
 -R network/prefix  add a route entry (up to 16 times)
 -r seconds     route entry lifetime of -R (defaults to 4096)
 -D dns-server    specify a DNS server (up to 16 times)
 -L searchlist    specify the DNS domain search list, seperate entries with ,
 -d seconds     dns entry lifetime of -D (defaults to 4096
 -M mtu       the MTU to send, defaults to the interface setting
 -s sourceip     the source ip of the router, defaults to your link local
 -S sourcemac    the source mac of the router, defaults to your interface
 -l seconds     router lifetime (defaults to 2048)
 -T ms        reachable timer (defaults to 0)
 -t ms        retrans timer (defaults to 0)
 -p priority     priority "low", "medium", "high" (default), "reserved"
 -F flags      Set one or more of the following flags: managed, other,
          homeagent, proxy, reserved; seperate by comma
 -E type       Router Advertisement Guard Evasion option. Types:
   H       simple hop-by-hop header
   1       simple one-shot fragmentation header (can add multiple)
   D       insert a large destination header so that it fragments
   O       overlapping fragments for keep-first targets (Win, BSD, Mac)
   o       overlapping fragments for keep-last targets (Linux, Solaris)
          Examples: -E H111, -E D
 -m mac-address   if only one machine should receive the RAs (not with -E DoO)
 -i interval    time between RA packets (default: 5)
 -n number     number of RAs to send (default: unlimited)

Announce yourself as a router and try to become the default router.
If a non-existing link-local or mac address is supplied, this results in a DOS.
```

### fake_router6 – Announce yourself as a router and try to become the default router.

```
root@kali:~# fake_router6
fake_router6 v2.3 (c) 2013 by van Hauser / THC <vh@thc.org> www.thc.org

Syntax: fake_router6 [-HFD] interface network-address/prefix-length [dns-server [router-ip-link-local [mtu [mac-address]]]]

Announce yourself as a router and try to become the default router.
If a non-existing link-local or mac address is supplied, this results in a DOS.
Option -H adds hop-by-hop, -F fragmentation header and -D dst header.
```

### fake_solicitate6 – Solicate ipv6 address on the network

```
root@kali:~# fake_solicitate6
fake_solicitate6 v2.3 (c) 2013 by van Hauser / THC <vh@thc.org> www.thc.org

Syntax: fake_solicitate6 [-DHF] interface ip-address-solicitated [target-address [mac-address-solicitated [source-ip-address]]]

Solicate ipv6 address on the network, sending it to the all-nodes multicast address
```

### firewall6 – Performs various ACL bypass attempts to check implementations

```
root@kali:~# firewall6
firewall6 v2.3 (c) 2013 by van Hauser / THC <vh@thc.org> www.thc.org

Syntax: firewall6 [-u] interface destination port [test-case-no]

Performs various ACL bypass attempts to check implementations.
Defaults to TCP ports, option -u switches to UDP.
For all test cases to work, ICMPv6 ping to thhe destination must be allowed.
```

### flood_advertise6 – Flood the local network with neighbor advertisements

```
root@kali:~# flood_advertise6
flood_advertise6 v2.3 (c) 2013 by van Hauser / THC <vh@thc.org> www.thc.org

Syntax: flood_advertise6 interface

Flood the local network with neighbor advertisements.
```

### flood_dhcpc6 – DHCP client flooder

```
root@kali:~# flood_dhcpc6
flood_dhcpc6 v2.3 (c) 2013 by van Hauser / THC <vh@thc.org> www.thc.org

Syntax: flood_dhcpc6 [-n|-N] [-1] [-d] interface [domain-name]

DHCP client flooder. Use to deplete the IP address pool a DHCP6 server is
offering. Note: if the pool is very large, this is rather senseless. :-)

By default the link-local IP MAC address is random, however this won't work
in some circumstances. -n will use the real MAC, -N the real MAC and
link-local address. -1 will only solicate an address but not request it.
If -N is not used, you should run parasite6 in parallel.
Use -d to force DNS updates, you can specify a domain name on the commandline.
```

### flood_mld26 – Flood the local network with MLDv2 reports

```
root@kali:~# flood_mld26
flood_mld26 v2.3 (c) 2013 by van Hauser / THC <vh@thc.org> www.thc.org

Syntax: flood_mld26 interface

Flood the local network with MLDv2 reports.
```

### flood_mld6 – Flood the local network with MLD reports

```
root@kali:~# flood_mld6
flood_mld6 v2.3 (c) 2013 by van Hauser / THC <vh@thc.org> www.thc.org

Syntax: flood_mld6 interface

Flood the local network with MLD reports.
```

### flood_mldrouter6 – Flood the local network with MLD router advertisements

```
root@kali:~# flood_mldrouter6
flood_mldrouter6 v2.3 (c) 2013 by van Hauser / THC <vh@thc.org> www.thc.org

Syntax: flood_mldrouter6 interface

Flood the local network with MLD router advertisements.
```

### flood_router26 – Flood the local network with router advertisements

```
root@kali:~# flood_router26
flood_router26 v2.3 (c) 2013 by van Hauser / THC <vh@thc.org> www.thc.org

Syntax: flood_router26 [-HFD] [-s] [-RPA] interface

Flood the local network with router advertisements.
Each packet contains 17 prefix and route enries
-F/-D/-H add fragment/destination/hopbyhop header to bypass RA guard security.
-R does only send routing entries, no prefix information.
-P does only send prefix information, no routing entries.
-A is like -P but implements an attack by George Kargiotakis to disable privacy extensions
The option -s uses small lifetimes, resulting in a more devasting impact
```

### flood_router6 – Flood the local network with router advertisements

```
root@kali:~# flood_router6
flood_router6 v2.3 (c) 2013 by van Hauser / THC <vh@thc.org> www.thc.org

Syntax: flood_router6 [-HFD] interface

Flood the local network with router advertisements.
-F/-D/-H add fragment/destination/hopbyhop header to bypass RA guard security.
```

### flood_solicitate6 – Flood the network with neighbor solicitations

```
root@kali:~# flood_solicitate6
flood_solicitate6 v2.3 (c) 2013 by van Hauser / THC <vh@thc.org> www.thc.org

Syntax: flood_solicitate6 interface [target]

Flood the network with neighbor solicitations.
```

### fragmentation6 – Performs fragment firewall and implementation checks

```
root@kali:~# fragmentation6
fragmentation6 v2.3 (c) 2013 by van Hauser / THC <vh@thc.org> www.thc.org

Syntax: fragmentation6 [-fp] [-n number] interface destination [test-case-no]

-f activates flooding mode, no pauses between sends; -p disables first and
final pings, -n number specifies how often each test is performed

Performs fragment firewall and implementation checks, incl. denial-of-service.
```

### fuzz_ip6 – Fuzzes an icmp6 packet

```
root@kali:~# fuzz_ip6
fuzz_ip6 v2.3 (c) 2013 by van Hauser / THC <vh@thc.org> www.thc.org

Syntax: fuzz_ip6 [-x] [-t number | -T number] [-p number] [-IFSDHRJ] [-X|-1|-2|-3|-4|-5|-6|-7|-8|-9|-0 port] interface unicast-or-multicast-address [address-in-data-pkt]

Fuzzes an icmp6 packet
Options:
 -X     do not add any ICMP/TCP header (tranport laye)
 -1     fuzz ICMP6 echo request (default)
 -2     fuzz ICMP6 neighbor solicitation
 -3     fuzz ICMP6 neighbor advertisement
 -4     fuzz ICMP6 router advertisement
 -5     fuzz multicast listener report packet
 -6     fuzz multicast listener done packet
 -7     fuzz multicast listener query packet
 -8     fuzz multicast listener v2 report packet
 -9     fuzz multicast listener v2 query packet
 -0     fuzz node query packet
 -s port   fuzz TCP-SYN packet against port
 -x     tries all 256 values for flag and byte types
 -t number  continue from test no. number
 -T number  only performs test no. number
 -p number  perform an alive check every number of tests (default: none)
 -a     do not perform initial and final alive test
 -n number  how many times to send each packet (default: 1)
 -I     fuzz the IP header too
 -F     add one-shot fragmentation, and fuzz it too (for 1)
 -S     add source-routing, and fuzz it too (for 1)
 -D     add destination header, and fuzz it too (for 1)
 -H     add hop-by-hop header, and fuzz it too (for 1 and 5-9)
 -R     add router alert header, and fuzz it too (for 5-9 and all)
 -J     add jumbo packet header, and fuzz it too (for 1)
You can only define one of -0 ... -9 and -s, defaults to -1.
Returns -1 on error, 0 on tests done and targt alive or 1 on target crash.
```

### implementation6 – Performs some ipv6 implementation checks

```
root@kali:~# implementation6
implementation6 v2.3 (c) 2013 by van Hauser / THC <vh@thc.org> www.thc.org

Syntax: implementation6 [-p] [-s sourceip6] interface destination [test-case-number]

Options:
 -s sourceip6  use the specified source IPv6 address
 -p       do not perform an alive check at the beginning and end
Performs some ipv6 implementation checks, can be used to test some
firewall features too. Takes approx. 2 minutes to complete.
```

### implementation6d – Identifies test packets by the implementation6 tool

```
root@kali:~# implementation6d
implementation6d v2.3 (c) 2013 by van Hauser / THC <vh@thc.org> www.thc.org

Syntax: implementation6d interface

Identifies test packets by the implementation6 tool, useful to check what
packets passed a firewall
```

### inject_alive6 – This tool answers to keep-alive requests on PPPoE and 6in4 tunnels

```
root@kali:~# inject_alive6
inject_alive6 v2.3 (c) 2013 by van Hauser / THC <vh@thc.org> www.thc.org

Syntax: inject_alive6 [-ap] interface

This tool answers to keep-alive requests on PPPoE and 6in4 tunnels; for PPPoE
it also sends keep-alive requests.
Note that the appropriate environment variable THC_IPV6_{PPPOE|6IN4} must be set
Option -a will actively send alive requests every 15 seconds.
Option -p will not send replies to alive requests.
```

### inverse_lookup6 – Performs an inverse address query

```
root@kali:~# inverse_lookup6
inverse_lookup6 v2.3 (c) 2013 by van Hauser / THC <vh@thc.org> www.thc.org

Syntax: inverse_lookup6 interface mac-address

Performs an inverse address query, to get the IPv6 addresses that are assigned
to a MAC address. Note that only few systems support this yet.
```

### kill_router6 – Announce that a target a router going down to delete it from the routing tables

```
root@kali:~# kill_router6
kill_router6 v2.3 (c) 2013 by van Hauser / THC <vh@thc.org> www.thc.org

Syntax: kill_router6 [-HFD] interface router-address [srcmac [dstmac]]

Announce that a target a router going down to delete it from the routing tables.
If you supply a '*' as router-address, this tool will sniff the network for any
RA packet and immediately send the kill packet.
Option -H adds hop-by-hop, -F fragmentation header and -D dst header.
```

### ndpexhaust26 – Flood the target /64 network with ICMPv6 TooBig error messages

```
root@kali:~# ndpexhaust26
ndpexhaust26 v2.3 (c) 2013 by van Hauser / THC <vh@thc.org> www.thc.org

Syntax: ndpexhaust26 [-acpPTUrR] [-s sourceip6] interface target-network

Options:
 -a    add a hop-by-hop header with router alert
 -c    do not calculate the checksum to save time
 -p    send ICMPv6 Echo Requests
 -P    send ICMPv6 Echo Reply
 -T    send ICMPv6 Time-to-live-exeeded
 -U    send ICMPv6 Unreachable (no route)
 -r    randomize the source from your /64 prefix
 -R    randomize the source fully
 -s sourceip6  use this as source ipv6 address

Flood the target /64 network with ICMPv6 TooBig error messages.
This tool version is manyfold more effective than ndpexhaust6.
```

### ndpexhaust6 – Flood the target /64 network with ICMPv6 TooBig error messages

```
root@kali:~# ndpexhaust26
ndpexhaust26 v2.3 (c) 2013 by van Hauser / THC <vh@thc.org> www.thc.org

Syntax: ndpexhaust26 [-acpPTUrR] [-s sourceip6] interface target-network

Options:
 -a    add a hop-by-hop header with router alert
 -c    do not calculate the checksum to save time
 -p    send ICMPv6 Echo Requests
 -P    send ICMPv6 Echo Reply
 -T    send ICMPv6 Time-to-live-exeeded
 -U    send ICMPv6 Unreachable (no route)
 -r    randomize the source from your /64 prefix
 -R    randomize the source fully
 -s sourceip6  use this as source ipv6 address

Flood the target /64 network with ICMPv6 TooBig error messages.
This tool version is manyfold more effective than ndpexhaust6.
root@kali:~# ndpexhaust6
ndpexhaust6 by mario fleischmann <mario.fleischmann@1und1.de>

Syntax: ndpexhaust6 interface destination-network [sourceip]

Randomly pings IPs in target network
```

### node_query6 – Sends an ICMPv6 node query request to the target

```
root@kali:~# node_query6
node_query6 v2.3 (c) 2013 by van Hauser / THC <vh@thc.org> www.thc.org

Syntax: node_query6 interface target

Sends an ICMPv6 node query request to the target and dumps the replies.
```

### parasite6 – This is an “ARP spoofer” for IPv6

```
root@kali:~# parasite6
parasite6 v2.3 (c) 2013 by van Hauser / THC <vh@thc.org> www.thc.org

Syntax: parasite6 [-lRFHD] interface [fake-mac]

This is an "ARP spoofer" for IPv6, redirecting all local traffic to your own
system (or nirvana if fake-mac does not exist) by answering falsely to
Neighbor Solitication requests
Option -l loops and resends the packets per target every 5 seconds.
Option -R will also try to inject the destination of the solicitation
NS security bypass: -F fragment, -H hop-by-hop and -D large destination header
```

### passive_discovery6 – Passively sniffs the network and dump all client’s IPv6 addresses

```
root@kali:~# passive_discovery6
passive_discovery6 v2.3 (c) 2013 by van Hauser / THC <vh@thc.org> www.thc.org

Syntax: passive_discovery6 [-Ds] [-m maxhop] [-R prefix] interface [script]

Options:
 -D      do also dump destination addresses (does not work with -m)
 -s      do only print the addresses, no other output
 -m maxhop  the maximum number of hops a target which is dumped may be away.
       0 means local only, the maximum amount to make sense is usually 5
 -R prefix  exchange the defined prefix with the link local prefix

Passively sniffs the network and dump all client's IPv6 addresses detected.
Note that in a switched environment you get better results when additionally
starting parasite6, however this will impact the network.
If a script name is specified after the interface, it is called with the
detected ipv6 address as first and the interface as second option.
```

### randicmp6 – Sends all ICMPv6 type and code combinations to destination

```
root@kali:~# randicmp6
Syntax: randicmp6 [-s sourceip] interface destination [type [code]]

Sends all ICMPv6 type and code combinations to destination.
Option -s  sets the source ipv6 address.
```

### redir6 – Implant a route into victim-ip, which redirects all traffic to target-ip

```
root@kali:~# redir6
redir6 v2.3 (c) 2013 by van Hauser / THC <vh@thc.org> www.thc.org

Syntax: redir6 interface victim-ip target-ip original-router new-router [new-router-mac] [hop-limit]

Implant a route into victim-ip, which redirects all traffic to target-ip to
new-ip. You must know the router which would handle the route.
If the new-router-mac does not exist, this results in a DOS.
If the TTL of the target is not 64, then specify this is the last option.
```

### redirsniff6 – Implant a route into victim-ip, which redirects all traffic to destination-ip

```
root@kali:~# redirsniff6
redirsniff6 v2.3 (c) 2013 by van Hauser / THC <vh@thc.org> www.thc.org

Syntax: redirsniff6 interface victim-ip destination-ip original-router [new-router [new-router-mac]]

Implant a route into victim-ip, which redirects all traffic to destination-ip to
new-router. This is done on all traffic that flows by that matches
victim->target. You must know the router which would handle the route.
If the new-router/-mac does not exist, this results in a DOS.
You can supply a wildcard ('*') for victim-ip and/or destination-ip.
```

### rsmurf6 – Smurfs the local network of the victim

```
root@kali:~# rsmurf6
rsmurf6 v2.3 (c) 2013 by van Hauser / THC <vh@thc.org> www.thc.org

Syntax: rsmurf6 interface victim-ip

Smurfs the local network of the victim. Note: this depends on an
implementation error, currently only verified on Linux.
Evil: "ff02::1" as victim will DOS your local LAN completely
```

### sendpees6 – Send SEND neighbor solicitation messages

```
root@kali:~# sendpees6
sendpees6 by willdamn <willdamn@gmail.com>

usage: sendpees6 <inf> <key_length> <prefix> <victim>

Send SEND neighbor solicitation messages and make target to verify a lota CGA and RSA signatures
```

### sendpeesmp6 – Send SEND neighbor solicitation messages

```
root@kali:~# sendpeesmp6
original sendpees by willdamn <willdamn@gmail.com>
modified sendpeesMP by Marcin Pohl <marcinpohl@gmail.com>
Code based on thc-ipv6

usage: sendpeesmp6 <inferface> <key_length> <prefix> <victim>

Send SEND neighbor solicitation messages and make target to verify a lota CGA and RSA signatures
Example: sendpeesmp6 eth0 2048 fe80:: fe80::1
```

### smurf6 – Smurf the target with icmp echo replies

```
root@kali:~# smurf6
smurf6 v2.3 (c) 2013 by van Hauser / THC <vh@thc.org> www.thc.org

Syntax: smurf6 interface victim-ip [multicast-network-address]

Smurf the target with icmp echo replies. Target of echo request is the
local all-nodes multicast address if not specified
```

### thcping6 – Craft your special icmpv6 echo request packet

```
root@kali:~# thcping6
thcping6 v2.3 (c) 2013 by van Hauser / THC <vh@thc.org> www.thc.org

Syntax: thcping6 [-af] [-H o:s:v] [-D o:s:v] [-F dst] [-t ttl] [-c class] [-l label] [-d size] [-S port|-U port] interface src6 dst6 [srcmac [dstmac [data]]]

Craft your special icmpv6 echo request packet.
You can put an "x" into src6, srcmac and dstmac for an automatic value.
Options:
 -a        add a hop-by-hop header with router alert option.
 -q        add a hop-by-hop header with quickstart option.
 -E        send as ethertype IPv4
 -H o:s:v     add a hop-by-hop header with special content
 -D o:s:v     add a destination header with special content
 -D "xxx"     add a large destination header which fragments the packet
 -f        add a one-shot fragementation header
 -F ipv6address  use source routing to this final destination
 -t ttl      specify TTL (default: 64)
 -c class     specify a class (0-4095)
 -l label     specify a label (0-1048575)
 -d data_size   define the size of the ping data buffer
 -S port     use a TCP SYN packet on the defined port instead of ping
 -U port     use a UDP packet on the defined port instead of ping
o:s:v syntax: option-no:size:value, value is in hex, e.g. 1:2:feab
Returns -1 on error or no reply, 0 on normal reply or 1 on error reply.
```

### thcsyn6 – Flood the target port with TCP-SYN packets

```
root@kali:~# thcsyn6
thcsyn6 v2.3 (c) 2013 by van Hauser / THC <vh@thc.org> www.thc.org

Syntax: thcsyn6 [-AcDrRS] [-p port] [-s sourceip6] interface target port

Options:
 -A    send TCP-ACK packets
 -S    send TCP-SYN-ACK packets
 -r    randomize the source from your /64 prefix
 -R    randomize the source fully
 -s sourceip6  use this as source ipv6 address
 -D    randomize the destination (treat as /64)
 -p port    use fixed source port

Flood the target port with TCP-SYN packets. If you supply "x" as port, it
is randomized.
```

### toobig6 – Implants the specified mtu on the target

```
root@kali:~# toobig6
toobig6 v2.3 (c) 2013 by van Hauser / THC <vh@thc.org> www.thc.org

Syntax: toobig6 [-u] interface target-ip existing-ip mtu [hop-limit]

Implants the specified mtu on the target.
If the TTL of the target is not 64, then specify this as the last option.
Option -u will send the TooBig without the spoofed ping6 from existing-ip.
```

### trace6 – A basic but very fast traceroute6 program

```
root@kali:~# trace6
trace6 v2.3 (c) 2013 by van Hauser / THC <vh@thc.org> www.thc.org

Syntax: trace6 [-abdt] [-s src6] interface targetaddress [port]

Options:
 -a    insert a hop-by-hop header with router alert option.
 -D    insert a destination extension header
 -E    insert a destination extension header with an invalid option
 -F    insert a one-shot fragmentation header
 -b    instead of an ICMP6 Ping, use TooBig (you will not see the target)
 -B    instead of an ICMP6 Ping, use PingReply (you will not see the target)
 -d    resolves the IPv6 addresses to DNS.
 -t    enables tunnel detection
 -s src6  specifies the source IPv6 address
Maximum hop reach: 31

A basic but very fast traceroute6 program.
If no port is specified, ICMP6 Ping requests are used, otherwise TCP SYN
packets to the specified port. Options D, E and F can be use multiple times.
```

### address6 Usage Example

```
Convert an IPv6 address to a MAC address and vice-versa:

root@kali:~# address6 fe80::76d4:35ff:fe4e:39c8
74:d4:35:4e:39:c8
root@kali:~# address6 74:d4:35:4e:39:c8
fe80::76d4:35ff:fe4e:39c8
```

### alive6 Usage Example

```
root@kali:~# alive6 eth0
Alive: fd77:7c68:420a:1:426c:8fff:fe1b:cb90 [ICMP parameter problem]
Alive: fd77:7c68:420a:1:20c:29ff:fee5:5bf4 [ICMP echo-reply]
Alive: fd77:7c68:420a:1:75d9:4f39:a46a:6f83 [ICMP echo-reply]
Alive: fd77:7c68:420a:1:6912:8e80:e02f:1969 [ICMP echo-reply]
Alive: fd77:7c68:420a:1:201:6cff:fe6f:ddd1 [ICMP echo-reply]
```

### detect-new-ip6 Usage Example

```
root@kali:~# detect-new-ip6 eth0
Started ICMP6 DAD detection (Press Control-C to end) ...
Detected new ip6 address: fe80::85d:9879:9251:853a
```

### dnsdict6 Usage Example

```
root@kali:~# dnsdict6 example.com
Starting DNS enumeration work on example.com. ...
Starting enumerating example.com. - creating 8 threads for 798 words...
Estimated time to completion: 1 to 2 minutes
www.example.com. => 2606:2800:220:6d:26bf:1447:1097:aa7
```