## theharvester Package Description

The objective of this program is to gather emails, subdomains, hosts, employee names, open ports and banners from different public sources like search engines, PGP key servers and SHODAN computer database.

This tool is intended to help Penetration testers in the early stages of the penetration test in order to understand the customer footprint on the Internet. It is also useful for anyone that wants to know what an attacker can see about their organization.

This is a complete rewrite of the tool with new features like:

- Time delays between request
- All sources search
- Virtual host verifier
- Active enumeration (DNS enumeration, Reverse lookups, TLD expansion)
- Integration with SHODAN computer database, to get the open ports and banners
- Save to XML and HTML
- Basic graph with stats
- New sources

Source: https://github.com/laramies/theHarvester/
[theHarvester Homepage](https://github.com/laramies/theHarvester) | [Kali theHarvester Repo](https://gitlab.com/kalilinux/packages/theharvester.git;a=summary)

- Author: Christian Martorella
- License: GPLv2

### Tools included in the theharvester package

##### theharvester – A tool for gathering e-mail accounts and subdomain names from public sources

```
root@kali:~# theharvester

*******************************************************************
\*                                 *
\* | |_| |__  ___   /\  /\__ _ _ ____  _____  ___| |_ ___ _ __  *
\* | __| '_ \ / _ \  / /_/ / _` | '__\ \ / / _ \/ __| __/ _ \ '__| *
\* | |_| | | |  __/ / __  / (_| | |  \ V /  __/\__ \ ||  __/ |   *
\*  \__|_| |_|\___| \/ /_/ \__,_|_|   \_/ \___||___/\__\___|_|   *
\*                                 *
\* TheHarvester Ver. 3.0.0                     *
\* Coded by Christian Martorella                  *
\* Edge-Security Research                      *
\* cmartorella@edge-security.com                  *
*******************************************************************


Usage: theharvester options

    -d: Domain to search or company name
    -b: data source: baidu, bing, bingapi, dogpile, google, googleCSE,
            googleplus, google-profiles, linkedin, pgp, twitter, vhost,
            virustotal, threatcrowd, crtsh, netcraft, yahoo, all

    -s: start in result number X (default: 0)
    -v: verify host name via dns resolution and search for virtual hosts
    -f: save the results into an HTML and XML file (both)
    -n: perform a DNS reverse query on all ranges discovered
    -c: perform a DNS brute force for the domain name
    -t: perform a DNS TLD expansion discovery
    -e: use this DNS server
    -p: port scan the detected hosts and check for Takeovers (80,443,22,21,8080)
    -l: limit the number of results to work with(bing goes from 50 to 50 results,
      google 100 to 100, and pgp doesn't use this option)
    -h: use SHODAN database to query discovered hosts

Examples:
    theharvester -d microsoft.com -l 500 -b google -h myresults.html
    theharvester -d microsoft.com -b pgp
    theharvester -d microsoft -l 200 -b linkedin
    theharvester -d apple.com -b googleCSE -l 500 -s 300
```

### theharvester Usage Example

Search from email addresses from a domain ***(-d kali.org)***, limiting the results to 500 ***(-l 500)***, using Google ***(-b google)***:

```
root@kali:~# theharvester -d kali.org -l 500 -b google

*******************************************************************
*                                 *
* | |_| |__  ___   /\  /\__ _ _ ____  _____  ___| |_ ___ _ __  *
* | __| '_ \ / _ \  / /_/ / _` | '__\ \ / / _ \/ __| __/ _ \ '__| *
* | |_| | | |  __/ / __  / (_| | |  \ V /  __/\__ \ ||  __/ |   *
*  \__|_| |_|\___| \/ /_/ \__,_|_|   \_/ \___||___/\__\___|_|   *
*                                 *
* TheHarvester Ver. 3.0.0                     *
* Coded by Christian Martorella                  *
* Edge-Security Research                      *
* cmartorella@edge-security.com                  *
*******************************************************************


[-] Starting harvesting process for domain: kali.org

[-] Searching in Google:
  Searching 0 results...
  Searching 100 results...
  Searching 200 results...
  Searching 300 results...
  Searching 400 results...
  Searching 500 results...

 Harvesting results
...
```