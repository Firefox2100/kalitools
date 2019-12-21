# DNSRecon

February 18, 2014

[Information Gathering](https://tools.kali.org/category/information-gathering)

## DNSRecon Package Description

DNSRecon provides the ability to perform:

- Check all NS Records for Zone Transfers
- Enumerate General DNS Records for a given Domain (MX, SOA, NS, A, AAAA, SPF and TXT)
- Perform common SRV Record Enumeration. Top Level Domain (TLD) Expansion
- Check for Wildcard Resolution
- Brute Force subdomain and host A and AAAA records given a domain and a wordlist
- Perform a PTR Record lookup for a given IP Range or CIDR
- Check a DNS Server Cached records for A, AAAA and CNAME Records provided a list of host records in a text file to check
- Enumerate Common mDNS records in the Local Network Enumerate Hosts and Subdomains using Google

Source: DNSRecon README
[DNSRecon Homepage](https://github.com/darkoperator/dnsrecon) | [Kali DNSRecon Repo](https://gitlab.com/kalilinux/packages/dnsrecon.git;a=summary)

- Author: Carlos Perez
- License: GPLv2

### Tools included in the dnsrecon package

##### dnsrecon – A powerful DNS enumeration script



<iframe src="https://asciinema.org/a/31190/embed?" id="asciicast-iframe-31190" name="asciicast-iframe-31190" scrolling="no" allowfullscreen="true" style="box-sizing: border-box; max-width: 100%; border: 0px; overflow: hidden; margin: 0px; display: inline-block; width: 622px; float: none; visibility: visible; height: 483px;"></iframe>


```
root@kali:~# dnsrecon -h
usage: dnsrecon.py [-h] [-d DOMAIN] [-n NS_SERVER] [-r RANGE] [-D DICTIONARY]
          [-f] [-t TYPE] [-a] [-s] [-g] [-b] [-k] [-w] [-z]
          [--threads THREADS] [--lifetime LIFETIME] [--tcp] [--db DB]
          [-x XML] [-c CSV] [-j JSON] [--iw] [-v]

optional arguments:
 -h, --help       show this help message and exit
 -d DOMAIN, --domain DOMAIN
            Target domain.
 -n NS_SERVER, --name_server NS_SERVER
            Domain server to use. If none is given, the SOA of the
            target will be used.
 -r RANGE, --range RANGE
            IP range for reverse lookup brute force in formats
            (first-last) or in (range/bitmask).
 -D DICTIONARY, --dictionary DICTIONARY
            Dictionary file of subdomain and hostnames to use for
            brute force. Filter out of brute force domain lookup,
            records that resolve to the wildcard defined IP
            address when saving records.
 -f           Filter out of brute force domain lookup, records that
            resolve to the wildcard defined IP address when saving
            records.
 -t TYPE, --type TYPE  Type of enumeration to perform.
 -a           Perform AXFR with standard enumeration.
 -s           Perform a reverse lookup of IPv4 ranges in the SPF
            record with standard enumeration.
 -g           Perform Google enumeration with standard enumeration.
 -b           Perform Bing enumeration with standard enumeration.
 -k           Perform crt.sh enumeration with standard enumeration.
 -w           Perform deep whois record analysis and reverse lookup
            of IP ranges found through Whois when doing a standard
            enumeration.
 -z           Performs a DNSSEC zone walk with standard enumeration.
 --threads THREADS   Number of threads to use in reverse lookups, forward
            lookups, brute force and SRV record enumeration.
 --lifetime LIFETIME  Time to wait for a server to response to a query.
 --tcp         Use TCP protocol to make queries.
 --db DB        SQLite 3 file to save found records.
 -x XML, --xml XML   XML file to save found records.
 -c CSV, --csv CSV   Comma separated value file.
 -j JSON, --json JSON  JSON file.
 --iw          Continue brute forcing a domain even if a wildcard
            records are discovered.
 -v           Enable verbose
```

### dnsrecon Usage Example

Scan a domain ***(-d example.com)***, use a dictionary to brute force hostnames ***(-D /usr/share/wordlists/dnsmap.txt)***, do a standard scan ***(-t std)\***, and save the output to a file ***(–xml dnsrecon.xml)***:

```
root@kali:~# dnsrecon -d example.com -D /usr/share/wordlists/dnsmap.txt -t std --xml dnsrecon.xml
[*] Performing General Enumeration of Domain:example.com
[*] DNSSEC is configured for example.com
[*] DNSKEYs:
```

[dns](https://tools.kali.org/tag/dns), [infogathering](https://tools.kali.org/tag/infogathering), [recon](https://tools.kali.org/tag/recon)

#### Related Posts

[dnmap](https://tools.kali.org/information-gathering/dnmap)

18 Feb 2014

[BlindElephant](https://tools.kali.org/web-applications/blindelephant)

15 Feb 2014

[airgraph-ng](https://tools.kali.org/wireless-attacks/airgraph-ng)

14 Feb 2014