## Nmap Package Description

Nmap (“Network Mapper”) is a free and open source (license) utility for network discovery and security auditing. Many systems and network administrators also find it useful for tasks such as network inventory, managing service upgrade schedules, and monitoring host or service uptime. Nmap uses raw IP packets in novel ways to determine what hosts are available on the network, what services (application name and version) those hosts are offering, what operating systems (and OS versions) they are running, what type of packet filters/firewalls are in use, and dozens of other characteristics. It was designed to rapidly scan large networks, but works fine against single hosts. Nmap runs on all major computer operating systems, and official binary packages are available for Linux, Windows, and Mac OS X. In addition to the classic command-line Nmap executable, the Nmap suite includes an advanced GUI and results viewer (Zenmap), a flexible data transfer, redirection, and debugging tool (Ncat), a utility for comparing scan results (Ndiff), and a packet generation and response analysis tool (Nping).

Nmap was named “Security Product of the Year” by Linux Journal, Info World, LinuxQuestions.Org, and Codetalker Digest. It was even featured in twelve movies, including The Matrix Reloaded, Die Hard 4, Girl With the Dragon Tattoo, and The Bourne Ultimatum.

**Nmap is …**

- Flexible: Supports dozens of advanced techniques for mapping out networks filled with IP filters, firewalls, routers, and other obstacles. This includes many port scanning mechanisms (both TCP & UDP), OS detection, version detection, ping sweeps, and more. See the documentation page.
- Powerful: Nmap has been used to scan huge networks of literally hundreds of thousands of machines.
- Portable: Most operating systems are supported, including Linux, Microsoft Windows, FreeBSD, OpenBSD, Solaris, IRIX, Mac OS X, HP-UX, NetBSD, Sun OS, Amiga, and more.
- Easy: While Nmap offers a rich set of advanced features for power users, you can start out as simply as “nmap -v -A targethost”. Both traditional command line and graphical (GUI) versions are available to suit your preference. Binaries are available for those who do not wish to compile Nmap from source.
- Free: The primary goals of the Nmap Project is to help make the Internet a little more secure and to provide administrators/auditors/hackers with an advanced tool for exploring their networks. Nmap is available for free download, and also comes with full source code that you may modify and redistribute under the terms of the license.
- Well Documented: Significant effort has been put into comprehensive and up-to-date man pages, whitepapers, tutorials, and even a whole book! Find them in multiple languages here.
- Supported: While Nmap comes with no warranty, it is well supported by a vibrant community of developers and users. Most of this interaction occurs on the Nmap mailing lists. Most bug reports and questions should be sent to the nmap-dev list, but only after you read the guidelines. We recommend that all users subscribe to the low-traffic nmap-hackers announcement list. You can also find Nmap on Facebook and Twitter. For real-time chat, join the #nmap channel on Freenode or EFNet.
- Acclaimed: Nmap has won numerous awards, including “Information Security Product of the Year” by Linux Journal, Info World and Codetalker Digest. It has been featured in hundreds of magazine articles, several movies, dozens of books, and one comic book series. Visit the press page for further details.
- Popular: Thousands of people download Nmap every day, and it is included with many operating systems (Redhat Linux, Debian Linux, Gentoo, FreeBSD, OpenBSD, etc). It is among the top ten (out of 30,000) programs at the Freshmeat.Net repository. This is important because it lends Nmap its vibrant development and user support communities.

Source: http://nmap.org/
[Nmap Homepage](http://insecure.org/) | [Kali Nmap Repo](https://gitlab.com/kalilinux/packages/nmap.git;a=summary)

- Author: Fyodor
- License: GPLv2

### Tools included in the nmap package

##### nping – Network packet generation tool / ping utility

```
root@kali:~# nping -h
Nping 0.7.70 ( https://nmap.org/nping )
Usage: nping [Probe mode] [Options] {target specification}

TARGET SPECIFICATION:
 Targets may be specified as hostnames, IP addresses, networks, etc.
 Ex: scanme.nmap.org, microsoft.com/24, 192.168.0.1; 10.0.*.1-24
PROBE MODES:
 --tcp-connect           : Unprivileged TCP connect probe mode.
 --tcp               : TCP probe mode.
 --udp               : UDP probe mode.
 --icmp              : ICMP probe mode.
 --arp               : ARP/RARP probe mode.
 --tr, --traceroute        : Traceroute mode (can only be used with
                   TCP/UDP/ICMP modes).
TCP CONNECT MODE:
  -p, --dest-port <port spec>   : Set destination port(s).
  -g, --source-port <portnumber>  : Try to use a custom source port.
TCP PROBE MODE:
  -g, --source-port <portnumber>  : Set source port.
  -p, --dest-port <port spec>   : Set destination port(s).
  --seq <seqnumber>        : Set sequence number.
  --flags <flag list>       : Set TCP flags (ACK,PSH,RST,SYN,FIN...)
  --ack <acknumber>        : Set ACK number.
  --win <size>           : Set window size.
  --badsum             : Use a random invalid checksum.
UDP PROBE MODE:
  -g, --source-port <portnumber>  : Set source port.
  -p, --dest-port <port spec>   : Set destination port(s).
  --badsum             : Use a random invalid checksum.
ICMP PROBE MODE:
 --icmp-type <type>        : ICMP type.
 --icmp-code <code>        : ICMP code.
 --icmp-id <id>          : Set identifier.
 --icmp-seq <n>          : Set sequence number.
 --icmp-redirect-addr <addr>    : Set redirect address.
 --icmp-param-pointer <pnt>    : Set parameter problem pointer.
 --icmp-advert-lifetime <time>   : Set router advertisement lifetime.
 --icmp-advert-entry <IP,pref>   : Add router advertisement entry.
 --icmp-orig-time  <timestamp>   : Set originate timestamp.
 --icmp-recv-time  <timestamp>   : Set receive timestamp.
 --icmp-trans-time <timestamp>   : Set transmit timestamp.
ARP/RARP PROBE MODE:
 --arp-type <type>         : Type: ARP, ARP-reply, RARP, RARP-reply.
 --arp-sender-mac <mac>      : Set sender MAC address.
 --arp-sender-ip  <addr>      : Set sender IP address.
 --arp-target-mac <mac>      : Set target MAC address.
 --arp-target-ip  <addr>      : Set target IP address.
IPv4 OPTIONS:
 -S, --source-ip          : Set source IP address.
 --dest-ip <addr>         : Set destination IP address (used as an
                   alternative to {target specification} ).
 --tos <tos>            : Set type of service field (8bits).
 --id  <id>            : Set identification field (16 bits).
 --df               : Set Don't Fragment flag.
 --mf               : Set More Fragments flag.
 --ttl <hops>           : Set time to live [0-255].
 --badsum-ip            : Use a random invalid checksum.
 --ip-options <S|R [route]|L [route]|T|U ...> : Set IP options
 --ip-options <hex string>           : Set IP options
 --mtu <size>           : Set MTU. Packets get fragmented if MTU is
                   small enough.
IPv6 OPTIONS:
 -6, --IPv6            : Use IP version 6.
 --dest-ip             : Set destination IP address (used as an
                   alternative to {target specification}).
 --hop-limit            : Set hop limit (same as IPv4 TTL).
 --traffic-class <class> :     : Set traffic class.
 --flow <label>          : Set flow label.
ETHERNET OPTIONS:
 --dest-mac <mac>         : Set destination mac address. (Disables
                   ARP resolution)
 --source-mac <mac>        : Set source MAC address.
 --ether-type <type>        : Set EtherType value.
PAYLOAD OPTIONS:
 --data <hex string>        : Include a custom payload.
 --data-string <text>       : Include a custom ASCII text.
 --data-length <len>        : Include len random bytes as payload.
ECHO CLIENT/SERVER:
 --echo-client <passphrase>    : Run Nping in client mode.
 --echo-server <passphrase>    : Run Nping in server mode.
 --echo-port <port>        : Use custom <port> to listen or connect.
 --no-crypto            : Disable encryption and authentication.
 --once              : Stop the server after one connection.
 --safe-payloads          : Erase application data in echoed packets.
TIMING AND PERFORMANCE:
 Options which take <time> are in seconds, or append 'ms' (milliseconds),
 's' (seconds), 'm' (minutes), or 'h' (hours) to the value (e.g. 30m, 0.25h).
 --delay <time>          : Adjust delay between probes.
 --rate  <rate>          : Send num packets per second.
MISC:
 -h, --help            : Display help information.
 -V, --version           : Display current version number.
 -c, --count <n>          : Stop after <n> rounds.
 -e, --interface <name>      : Use supplied network interface.
 -H, --hide-sent          : Do not display sent packets.
 -N, --no-capture         : Do not try to capture replies.
 --privileged           : Assume user is fully privileged.
 --unprivileged          : Assume user lacks raw socket privileges.
 --send-eth            : Send packets at the raw Ethernet layer.
 --send-ip             : Send packets using raw IP sockets.
 --bpf-filter <filter spec>    : Specify custom BPF filter.
OUTPUT:
 -v                : Increment verbosity level by one.
 -v[level]             : Set verbosity level. E.g: -v4
 -d                : Increment debugging level by one.
 -d[level]             : Set debugging level. E.g: -d3
 -q                : Decrease verbosity level by one.
 -q[N]               : Decrease verbosity level N times
 --quiet              : Set verbosity and debug level to minimum.
 --debug              : Set verbosity and debug to the max level.
EXAMPLES:
 nping scanme.nmap.org
 nping --tcp -p 80 --flags rst --ttl 2 192.168.1.1
 nping --icmp --icmp-type time --delay 500ms 192.168.254.254
 nping --echo-server "public" -e wlan0 -vvv
 nping --echo-client "public" echo.nmap.org --tcp -p1-1024 --flags ack

SEE THE MAN PAGE FOR MANY MORE OPTIONS, DESCRIPTIONS, AND EXAMPLES
```

### ndiff – Utility to compare the results of Nmap scans

```
root@kali:~# ndiff -h
Usage: /usr/bin/ndiff [option] FILE1 FILE2
Compare two Nmap XML files and display a list of their differences.
Differences include host state changes, port state changes, and changes to
service and OS detection.

 -h, --help   display this help
 -v, --verbose  also show hosts and ports that haven't changed.
 --text     display output in text format (default)
 --xml      display output in XML format
```

### ncat – Concatenate and redirect sockets

```
root@kali:~# ncat -h
Ncat 7.70 ( https://nmap.org/ncat )
Usage: ncat [options] [hostname] [port]

Options taking a time assume seconds. Append 'ms' for milliseconds,
's' for seconds, 'm' for minutes, or 'h' for hours (e.g. 500ms).
 -4             Use IPv4 only
 -6             Use IPv6 only
 -U, --unixsock       Use Unix domain sockets only
 -C, --crlf         Use CRLF for EOL sequence
 -c, --sh-exec <command>   Executes the given command via /bin/sh
 -e, --exec <command>    Executes the given command
   --lua-exec <filename>  Executes the given Lua script
 -g hop1[,hop2,...]     Loose source routing hop points (8 max)
 -G <n>           Loose source routing hop pointer (4, 8, 12, ...)
 -m, --max-conns <n>     Maximum <n> simultaneous connections
 -h, --help         Display this help screen
 -d, --delay <time>     Wait between read/writes
 -o, --output <filename>   Dump session data to a file
 -x, --hex-dump <filename>  Dump session data as hex to a file
 -i, --idle-timeout <time>  Idle read/write timeout
 -p, --source-port port   Specify source port to use
 -s, --source addr      Specify source address to use (doesn't affect -l)
 -l, --listen        Bind and listen for incoming connections
 -k, --keep-open       Accept multiple connections in listen mode
 -n, --nodns         Do not resolve hostnames via DNS
 -t, --telnet        Answer Telnet negotiations
 -u, --udp          Use UDP instead of default TCP
   --sctp         Use SCTP instead of default TCP
 -v, --verbose        Set verbosity level (can be used several times)
 -w, --wait <time>      Connect timeout
 -z             Zero-I/O mode, report connection status only
   --append-output     Append rather than clobber specified output files
   --send-only       Only send data, ignoring received; quit on EOF
   --recv-only       Only receive data, never send anything
   --allow         Allow only given hosts to connect to Ncat
   --allowfile       A file of hosts allowed to connect to Ncat
   --deny         Deny given hosts from connecting to Ncat
   --denyfile       A file of hosts denied from connecting to Ncat
   --broker        Enable Ncat's connection brokering mode
   --chat         Start a simple Ncat chat server
   --proxy <addr[:port]>  Specify address of host to proxy through
   --proxy-type <type>   Specify proxy type ("http" or "socks4" or "socks5")
   --proxy-auth <auth>   Authenticate with HTTP or SOCKS proxy server
   --ssl          Connect or listen with SSL
   --ssl-cert       Specify SSL certificate file (PEM) for listening
   --ssl-key        Specify SSL private key (PEM) for listening
   --ssl-verify      Verify trust and domain name of certificates
   --ssl-trustfile     PEM file containing trusted SSL certificates
   --ssl-ciphers      Cipherlist containing SSL ciphers to use
   --ssl-alpn       ALPN protocol list to use.
   --version        Display Ncat's version information and exit

See the ncat(1) manpage for full options, descriptions and usage examples
```

### nmap – The Network Mapper

```
root@kali:~# nmap -h
Nmap 7.70 ( https://nmap.org )
Usage: nmap [Scan Type(s)] [Options] {target specification}
TARGET SPECIFICATION:
 Can pass hostnames, IP addresses, networks, etc.
 Ex: scanme.nmap.org, microsoft.com/24, 192.168.0.1; 10.0.0-255.1-254
 -iL <inputfilename>: Input from list of hosts/networks
 -iR <num hosts>: Choose random targets
 --exclude <host1[,host2][,host3],...>: Exclude hosts/networks
 --excludefile <exclude_file>: Exclude list from file
HOST DISCOVERY:
 -sL: List Scan - simply list targets to scan
 -sn: Ping Scan - disable port scan
 -Pn: Treat all hosts as online -- skip host discovery
 -PS/PA/PU/PY[portlist]: TCP SYN/ACK, UDP or SCTP discovery to given ports
 -PE/PP/PM: ICMP echo, timestamp, and netmask request discovery probes
 -PO[protocol list]: IP Protocol Ping
 -n/-R: Never do DNS resolution/Always resolve [default: sometimes]
 --dns-servers <serv1[,serv2],...>: Specify custom DNS servers
 --system-dns: Use OS's DNS resolver
 --traceroute: Trace hop path to each host
SCAN TECHNIQUES:
 -sS/sT/sA/sW/sM: TCP SYN/Connect()/ACK/Window/Maimon scans
 -sU: UDP Scan
 -sN/sF/sX: TCP Null, FIN, and Xmas scans
 --scanflags <flags>: Customize TCP scan flags
 -sI <zombie host[:probeport]>: Idle scan
 -sY/sZ: SCTP INIT/COOKIE-ECHO scans
 -sO: IP protocol scan
 -b <FTP relay host>: FTP bounce scan
PORT SPECIFICATION AND SCAN ORDER:
 -p <port ranges>: Only scan specified ports
  Ex: -p22; -p1-65535; -p U:53,111,137,T:21-25,80,139,8080,S:9
 --exclude-ports <port ranges>: Exclude the specified ports from scanning
 -F: Fast mode - Scan fewer ports than the default scan
 -r: Scan ports consecutively - don't randomize
 --top-ports <number>: Scan <number> most common ports
 --port-ratio <ratio>: Scan ports more common than <ratio>
SERVICE/VERSION DETECTION:
 -sV: Probe open ports to determine service/version info
 --version-intensity <level>: Set from 0 (light) to 9 (try all probes)
 --version-light: Limit to most likely probes (intensity 2)
 --version-all: Try every single probe (intensity 9)
 --version-trace: Show detailed version scan activity (for debugging)
SCRIPT SCAN:
 -sC: equivalent to --script=default
 --script=<Lua scripts>: <Lua scripts> is a comma separated list of
      directories, script-files or script-categories
 --script-args=<n1=v1,[n2=v2,...]>: provide arguments to scripts
 --script-args-file=filename: provide NSE script args in a file
 --script-trace: Show all data sent and received
 --script-updatedb: Update the script database.
 --script-help=<Lua scripts>: Show help about scripts.
      <Lua scripts> is a comma-separated list of script-files or
      script-categories.
OS DETECTION:
 -O: Enable OS detection
 --osscan-limit: Limit OS detection to promising targets
 --osscan-guess: Guess OS more aggressively
TIMING AND PERFORMANCE:
 Options which take <time> are in seconds, or append 'ms' (milliseconds),
 's' (seconds), 'm' (minutes), or 'h' (hours) to the value (e.g. 30m).
 -T<0-5>: Set timing template (higher is faster)
 --min-hostgroup/max-hostgroup <size>: Parallel host scan group sizes
 --min-parallelism/max-parallelism <numprobes>: Probe parallelization
 --min-rtt-timeout/max-rtt-timeout/initial-rtt-timeout <time>: Specifies
   probe round trip time.
 --max-retries <tries>: Caps number of port scan probe retransmissions.
 --host-timeout <time>: Give up on target after this long
 --scan-delay/--max-scan-delay <time>: Adjust delay between probes
 --min-rate <number>: Send packets no slower than <number> per second
 --max-rate <number>: Send packets no faster than <number> per second
FIREWALL/IDS EVASION AND SPOOFING:
 -f; --mtu <val>: fragment packets (optionally w/given MTU)
 -D <decoy1,decoy2[,ME],...>: Cloak a scan with decoys
 -S <IP_Address>: Spoof source address
 -e <iface>: Use specified interface
 -g/--source-port <portnum>: Use given port number
 --proxies <url1,[url2],...>: Relay connections through HTTP/SOCKS4 proxies
 --data <hex string>: Append a custom payload to sent packets
 --data-string <string>: Append a custom ASCII string to sent packets
 --data-length <num>: Append random data to sent packets
 --ip-options <options>: Send packets with specified ip options
 --ttl <val>: Set IP time-to-live field
 --spoof-mac <mac address/prefix/vendor name>: Spoof your MAC address
 --badsum: Send packets with a bogus TCP/UDP/SCTP checksum
OUTPUT:
 -oN/-oX/-oS/-oG <file>: Output scan in normal, XML, s|<rIpt kIddi3,
   and Grepable format, respectively, to the given filename.
 -oA <basename>: Output in the three major formats at once
 -v: Increase verbosity level (use -vv or more for greater effect)
 -d: Increase debugging level (use -dd or more for greater effect)
 --reason: Display the reason a port is in a particular state
 --open: Only show open (or possibly open) ports
 --packet-trace: Show all packets sent and received
 --iflist: Print host interfaces and routes (for debugging)
 --append-output: Append to rather than clobber specified output files
 --resume <filename>: Resume an aborted scan
 --stylesheet <path/URL>: XSL stylesheet to transform XML output to HTML
 --webxml: Reference stylesheet from Nmap.Org for more portable XML
 --no-stylesheet: Prevent associating of XSL stylesheet w/XML output
MISC:
 -6: Enable IPv6 scanning
 -A: Enable OS detection, version detection, script scanning, and traceroute
 --datadir <dirname>: Specify custom Nmap data file location
 --send-eth/--send-ip: Send using raw ethernet frames or IP packets
 --privileged: Assume that the user is fully privileged
 --unprivileged: Assume the user lacks raw socket privileges
 -V: Print version number
 -h: Print this help summary page.
EXAMPLES:
 nmap -v -A scanme.nmap.org
 nmap -v -sn 192.168.0.0/16 10.0.0.0/8
 nmap -v -iR 10000 -Pn -p 80
SEE THE MAN PAGE (https://nmap.org/book/man.html) FOR MORE OPTIONS AND EXAMPLES
```

### nmap Usage Example

Scan in verbose mode ***(-v)***, enable OS detection, version detection, script scanning, and traceroute ***(-A)***, with version detection ***(-sV)*** against the target IP ***(192.168.1.1)***:

```
root@kali:~# nmap -v -A -sV 192.168.1.1

Starting Nmap 6.45 ( http://nmap.org ) at 2014-05-13 18:40 MDT
NSE: Loaded 118 scripts for scanning.
NSE: Script Pre-scanning.
Initiating ARP Ping Scan at 18:40
Scanning 192.168.1.1 [1 port]
Completed ARP Ping Scan at 18:40, 0.06s elapsed (1 total hosts)
Initiating Parallel DNS resolution of 1 host. at 18:40
Completed Parallel DNS resolution of 1 host. at 18:40, 0.00s elapsed
Initiating SYN Stealth Scan at 18:40
Scanning router.localdomain (192.168.1.1) [1000 ports]
Discovered open port 53/tcp on 192.168.1.1
Discovered open port 22/tcp on 192.168.1.1
Discovered open port 80/tcp on 192.168.1.1
Discovered open port 3001/tcp on 192.168.1.1
```

### nping Usage Example

Using TCP mode ***(–tcp)*** to probe port 22 ***(-p 22)*** using the SYN flag ***(–flags syn)*** with a TTL of 2 ***(–ttl 2)*** on the remote host ***(192.168.1.1)***:

```
root@kali:~# nping --tcp -p 22 --flags syn --ttl 2 192.168.1.1

Starting Nping 0.6.45 ( http://nmap.org/nping ) at 2014-05-13 18:43 MDT
SENT (0.0673s) TCP 192.168.1.15:60125 > 192.168.1.1:22 S ttl=2 id=54240 iplen=40  seq=1720523417 win=1480
RCVD (0.0677s) TCP 192.168.1.1:22 > 192.168.1.15:60125 SA ttl=64 id=0 iplen=44  seq=3377886789 win=5840 <mss 1460>
SENT (1.0678s) TCP 192.168.1.15:60125 > 192.168.1.1:22 S ttl=2 id=54240 iplen=40  seq=1720523417 win=1480
RCVD (1.0682s) TCP 192.168.1.1:22 > 192.168.1.15:60125 SA ttl=64 id=0 iplen=44  seq=3393519366 win=5840 <mss 1460>
SENT (2.0693s) TCP 192.168.1.15:60125 > 192.168.1.1:22 S ttl=2 id=54240 iplen=40  seq=1720523417 win=1480
RCVD (2.0696s) TCP 192.168.1.1:22 > 192.168.1.15:60125 SA ttl=64 id=0 iplen=44  seq=3409166569 win=5840 <mss 1460>
SENT (3.0707s) TCP 192.168.1.15:60125 > 192.168.1.1:22 S ttl=2 id=54240 iplen=40  seq=1720523417 win=1480
RCVD (3.0710s) TCP 192.168.1.1:22 > 192.168.1.15:60125 SA ttl=64 id=0 iplen=44  seq=3424813300 win=5840 <mss 1460>
SENT (4.0721s) TCP 192.168.1.15:60125 > 192.168.1.1:22 S ttl=2 id=54240 iplen=40  seq=1720523417 win=1480
RCVD (4.0724s) TCP 192.168.1.1:22 > 192.168.1.15:60125 SA ttl=64 id=0 iplen=44  seq=3440460772 win=5840 <mss 1460>

Max rtt: 0.337ms | Min rtt: 0.282ms | Avg rtt: 0.296ms
Raw packets sent: 5 (200B) | Rcvd: 5 (230B) | Lost: 0 (0.00%)
Nping done: 1 IP address pinged in 4.13 seconds
```

### ndiff Usage Example

Compare yesterday’s port scan ***(yesterday.xml)*** with the scan from today ***(today.xml)***:

```
root@kali:~# ndiff yesterday.xml today.xml
-Nmap 6.45 scan initiated Tue May 13 18:46:43 2014 as: nmap -v -F -oX yesterday.xml 192.168.1.1
+Nmap 6.45 scan initiated Tue May 13 18:47:58 2014 as: nmap -v -F -oX today.xml 192.168.1.1

 endian.localdomain (192.168.1.1, 00:01:6C:6F:DD:D1):
-Not shown: 96 filtered ports
+Not shown: 97 filtered ports
 PORT  STATE SERVICE VERSION
-22/tcp open  ssh
```

### ncat Usage Example

Be verbose ***(-v)***, running /bin/bash on connect ***(–exec “/bin/bash”)***, only allowing 1 IP address ***(–allow 192.168.1.123)***, listen on TCP port 4444 ***(-l 4444)***, and keep the listener open on disconnect ***(–keep-open)***:

```
root@kali:~# ncat -v --exec "/bin/bash" --allow 192.168.1.123 -l 4444 --keep-open
Ncat: Version 6.45 ( http://nmap.org/ncat )
Ncat: Listening on :::4444
Ncat: Listening on 0.0.0.0:4444
Ncat: Connection from 192.168.1.123.
Ncat: Connection from 192.168.1.123:39501.
Ncat: Connection from 192.168.1.15.
Ncat: Connection from 192.168.1.15:60393.
Ncat: New connection denied: not allowed
```