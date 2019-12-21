## ntop Package Description

ntop is a tool that shows the network usage, similar to what the popular top Unix command does. ntop is based on pcapture (ftp://ftp.ee.lbl.gov/pcapture.tar.Z) and it has been written in a portable way in order to virtually run on every Unix platform.

ntop can be used in both interactive or web mode. In the first case, ntop displays the network status on the user’s terminal whereas in web mode a web browser (e.g. netscape) can attach to ntop (that acts as a web server) and get a dump of the network status. In the latter case, ntop can be seen as a simple RMON-like agent with an embedded web interface.

ntop uses libpcap, a system-independent interface for user-level packet capture.

Source: ntop README
[ntop Homepage](http://www.ntop.org/) | [Kali ntop Repo](https://gitlab.com/kalilinux/packages/ntop.git;a=summary)

- Author: Luca Deri
- License: GPLv2

### Tools included in the ntop package

##### ntop – display network usage in web browser

```
root@kali:~# ntop -h
Welcome to ntop v.4.99.3 (32 bit)
[Configured on Mar  2 2013  6:00:33, built on Mar  2 2013 06:01:55]
Copyright 1998-2012 by Luca Deri <deri@ntop.org>

Get the freshest ntop from http://www.ntop.org/

Usage: ntop [OPTION]

Basic options:
  [-h       | --help]               Display this help and exit
  [-u <user>    | --user <user>]            Userid/name to run ntop under (see man page)
  [-t <number>   | --trace-level <number>]       Trace level [0-6]
  [-P <path>    | --db-file-path <path>]        Path for ntop internal database files
  [-Q <path>    | --spool-file-path <path>]      Path for ntop spool files
  [-w <port>    | --http-server <port>]        Web server (http:) port (or address:port) to listen on

Advanced options:
  [-4       | --ipv4]               Use IPv4 connections
  [-6       | --ipv6]               Use IPv6 connections
  [-a <file>    | --access-log-file <file>]      File for ntop web server access log
  [-b       | --disable-decoders]         Disable protocol decoders
  [-c       | --sticky-hosts]           Idle hosts are not purged from memory
  [-d       | --daemon]              Run ntop in daemon mode
  [-e <number>   | --max-table-rows <number>]      Maximum number of table rows to report
  [-f <file>    | --traffic-dump-file <file>]     Traffic dump file (see tcpdump)
  [-g       | --track-local-hosts]         Track only local hosts
  [-i <name>    | --interface <name>]         Interface name or names to monitor
  [-j       | --create-other-packets]       Create file ntop-other-pkts.XXX.pcap file
  [-l <path>    | --pcap-log <path>]          Dump packets captured to a file (debug only!)
  [-m <addresses> | --local-subnets <addresses>]     Local subnetwork(s) (see man page)
  [-n <mode>    | --numeric-ip-addresses <mode>]    Numeric IP addresses DNS resolution mode:
                             0 - No DNS resolution at all
                             1 - DNS resolution for local hosts only
                             2 - DNS resolution for remote hosts only
  [-p <list>    | --protocols <list>]         List of IP protocols to monitor (see man page)
  [-q       | --create-suspicious-packets]     Create file ntop-suspicious-pkts.XXX.pcap file
  [-r <number>   | --refresh-time <number>]       Refresh time in seconds, default is 120
  [-s       | --no-promiscuous]          Disable promiscuous mode
  [-x <max num hash entries> ]              Max num. hash entries ntop can handle (default 8192)
  [-z       | --disable-sessions]         Disable TCP session tracking
  [-A]                          Ask admin user password and exit
  [        | --set-admin-password=<pass>]     Set password for the admin user to <pass>
  [        | --w3c]                Add extra headers to make better html
  [-B <filter>]  | --filter-expression         Packet filter expression, like tcpdump (for all interfaces)
                             You can also set per-interface filter:
                             eth0=tcp,eth1=udp ....
  [-C <rate>]   | --sampling-rate           Packet capture sampling rate [default: 1 (no sampling)]
  [-D <name>    | --domain <name>]           Internet domain name
  [-F <spec>    | --flow-spec <specs>]         Flow specs (see man page)
  [-K       | --enable-debug]           Enable debug mode
  [-L]                          Do logging via syslog
  [        | --use-syslog=<facility>]       Do logging via syslog, facility ('=' is REQUIRED)
  [-M       | --no-interface-merge]        Don't merge network interfaces (see man page)
  [-O <path>    | --pcap-file-path <path>]       Path for log files in pcap format
  [-U <URL>    | --mapper <URL>]           URL (mapper.pl) for displaying host location
  [-V       | --version]              Output version information and exit
  [-X <max num TCP sessions> ]              Max num. TCP sessions ntop can handle (default 32768)
  [--disable-instantsessionpurge]            Disable instant FIN session purge
  [--disable-mutexextrainfo]               Disable extra mutex info
  [--disable-stopcap]                  Capture packets even if there's no memory left
  [--disable-ndpi]                    Disable nDPI for protocol discovery
  [--disable-python]                   Disable Python interpreter
  [--instance <name>]                  Set log name for this ntop instance
  [--p3p-cp]                       Set return value for p3p compact policy, header
  [--p3p-uri]                      Set return value for p3p policyref header
  [--skip-version-check]                 Skip ntop version check
  [--known-subnets <networks>]              List of known subnets (separated by ,)
                             If the argument starts with @ it is assumed it is a file path
                             E.g. 192.168.0.0/14=home,172.16.0.0/16=private

NOTE
  \* You can configure further ntop options via the web
   interface [Menu Admin -> Config].
  \* The command line options are not permanent, i.e. they
   are not persistent across ntop initializations.
```

### ntop Usage Example

Display network usage, filtering for a specific IP address ***(-B “src host 192.168.1.1”)***:

```
root@kali:~# ntop -B "src host 192.168.1.1"
```