## fragroute Package Description

fragroute intercepts, modifies, and rewrites egress traffic destined for a specified host, implementing most of the attacks described in the Secure Networks “Insertion, Evasion, and Denial of Service: Eluding Network Intrusion Detection” paper of January 1998.

It features a simple ruleset language to delay, duplicate, drop, fragment, overlap, print, reorder, segment, source-route, or otherwise monkey with all outbound packets destined for a target host, with minimal support for randomized or probabilistic behaviour.

This tool was written in good faith to aid in the testing of network intrusion detection systems, firewalls, and basic TCP/IP stack behaviour. Please do not abuse this software.

Source: http://www.monkey.org/~dugsong/fragroute/
[fragroute Homepage](http://www.monkey.org/~dugsong/fragroute/) | [Kali fragroute Repo](https://gitlab.com/kalilinux/packages/fragroute.git;a=summary)

- Author: Dug Song
- License: 3-Clause BSD

### tools included in the fragroute package

##### fragroute – Test a NIDS by attempting to evade using fragmented packets

```
root@kali:~# fragroute
Usage: fragroute [-f file] dst
Rules:
    delay first|last|random <ms>
    drop first|last|random <prob-%>
    dup first|last|random <prob-%>
    echo <string> ...
    ip_chaff dup|opt|<ttl>
    ip_frag <size> [old|new]
    ip_opt lsrr|ssrr <ptr> <ip-addr> ...
    ip_ttl <ttl>
    ip_tos <tos>
    order random|reverse
    print
    tcp_chaff cksum|null|paws|rexmit|seq|syn|<ttl>
    tcp_opt mss|wscale <size>
    tcp_seg <size> [old|new]
```

### fragtest – Test a NIDS by attempting to evade using fragmented packets

```
root@kali:~# fragtest
Usage: fragtest TESTS ... <host>

 where TESTS is any combination of the following (or "all"):

 ping   prerequisite for all tests
 ip-opt  determine supported IP options (BROKEN)
 ip-tracert  determine path to target
 frag   try 8-byte IP fragments
 frag-new try 8-byte fwd-overlapping IP fragments, favoring new data (BROKEN)
 frag-old try 8-byte fwd-overlapping IP fragments, favoring old data
 frag-timeout determine IP fragment reassembly timeout (BROKEN)
```

### fragroute Usage Example

```
root@kali:~# fragroute 192.168.1.123
fragroute: tcp_seg -> ip_frag -> ip_chaff -> order -> print
172.16.79.182.53735 > 192.168.1.123.80: S 617662291:617662291(0) win 29200
```

### fragtest Usage Example

```
root@kali:~# fragtest ip-tracert frag-new 192.168.1.123
ip-tracert: aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa
```