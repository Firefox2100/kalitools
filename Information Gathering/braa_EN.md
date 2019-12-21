## braa Package Description

Braa is a mass snmp scanner. The intended usage of such a tool is of course making SNMP queries – but unlike snmpget or snmpwalk from net-snmp, it is able to query dozens or hundreds of hosts simultaneously, and in a single process. Thus, it consumes very few system resources and does the scanning VERY fast.

Braa implements its OWN snmp stack, so it does NOT need any SNMP libraries like net-snmp. The implementation is very dirty, supports only several data types, and in any case cannot be stated ‘standard-conforming’! It was designed to be fast, and it is fast. For this reason (well, and also because of my laziness ;), there is no ASN.1 parser in braa – you HAVE to know the numerical values of OID’s (for instance .1.3.6.1.2.1.1.5.0 instead of system.sysName.0).

Source: braa README

[braa Homepage](http://s-tech.elsat.net.pl/) | [Kali braa Repo](https://gitlab.com/kalilinux/packages/braa.git;a=summary)

- Author: Mateusz ‘mteg’ Golicz
- License: GPLv2

### Tools included in the braa package

##### braa – Mass SNMP scanner

```
[/vc_column_text][/vc_column][/vc_row][vc_row][vc_column][vc_column_text]root@kali:~# braa -hbraa 0.81 - Mateusz 'mteg' Golicz &lt;mtg@elsat.net.pl&gt;, 2003 - 2006usage: braa [options] [query1] [query2] ...-h Show this help.-2 Claim to be a SNMP2C agent.-v Show short summary after doing all queries.-x Hexdump octet-strings-t <s> Wait <s> seconds for responses.-d <s> Wait <s> microseconds after sending each packet.-p <s> Wait <s> miliseconds between subsequent passes.-f Load queries from file (one by line).-a <time> Quit after <time> seconds, independent on what happens.-r Retry count (default: 3).</time></time></s></s></s></s></s></s>Query format:GET: [community@]iprange[:port]:oid[/id]WALK: [community@]iprange[:port]:oid.*[/id]SET: [community@]iprange[:port]:oid=value[/id]Examples:public@10.253.101.1:161:.1.3.6.*10.253.101.1-10.253.101.255:.1.3.6.1.2.1.1.4.0=sme10.253.101.1:.1.3.6.1.2.1.1.1.0/descriptionIt is also possible to specify multiple queries at once:10.253.101.1-10.253.101.255:.1.3.6.1.2.1.1.4.0=sme,.1.3.6.*(Will set .1.3.6.1.2.1.1.4.0 to 'me' and do a walk starting from .1.3.6)Values for SET queries have to be prepended with a character specifying the value type:i is INTEGERa is IPADDRESSs is OCTET STRINGo is OBJECT IDENTIFIERIf the type specifier is missing, the value type is auto-detected
```

### braa Usage Example

Walk the SNMP tree on ***192.168.1.215*** using the community string of ***public***, querying all OIDs under ***.1.3.6***:

```
[/vc_column_text][/vc_column][/vc_row][vc_row][vc_column][vc_column_text]
root@kali:~# braa public@192.168.1.215:.1.3.6.*
192.168.1.215:122ms:.1.3.6.1.2.1.1.1.0:Linux redhat.biz.local 2.4.20-8 #1 Thu Mar 13 17:54:28 EST 2003 i686
192.168.1.215:143ms:.1.3.6.1.2.1.1.2.0:.1.3.6.1.4.1.8072.3.2.10
192.168.1.215:122ms:.1.3.6.1.2.1.1.3.0:4051218219
192.168.1.215:122ms:.1.3.6.1.2.1.1.4.0:Root &lt;root@localhost&gt; (configure /etc/snmp/snmp.local.conf)
192.168.1.215:143ms:.1.3.6.1.2.1.1.5.0:redhat.biz.local
```