# Nikto

February 18, 2014

[Information Gathering](https://tools.kali.org/category/information-gathering), [Web Applications](https://tools.kali.org/category/web-applications)

## Nikto Package Description

Nikto is an Open Source (GPL) web server scanner which performs comprehensive tests against web servers for multiple items, including over 6700 potentially dangerous files/programs, checks for outdated versions of over 1250 servers, and version specific problems on over 270 servers. It also checks for server configuration items such as the presence of multiple index files, HTTP server options, and will attempt to identify installed web servers and software. Scan items and plugins are frequently updated and can be automatically updated.

Nikto is not designed as a stealthy tool. It will test a web server in the quickest time possible, and is obvious in log files or to an IPS/IDS. However, there is support for LibWhisker’s anti-IDS methods in case you want to give it a try (or test your IDS system).

Not every check is a security problem, though most are. There are some items that are “info only” type checks that look for things that may not have a security flaw, but the webmaster or security engineer may not know are present on the server. These items are usually marked appropriately in the information printed. There are also some checks for unknown items which have been seen scanned for in log files.

Features:

- Here are some of the major features of Nikto. See the documentation for a full list of features and how to use them.
- SSL Support (Unix with OpenSSL or maybe Windows with ActiveState’s Perl/NetSSL)
- Full HTTP proxy support
- Checks for outdated server components
- Save reports in plain text, XML, HTML, NBE or CSV
- Template engine to easily customize reports
- Scan multiple ports on a server, or multiple servers via input file (including nmap output)
- LibWhisker’s IDS encoding techniques
- Easily updated via command line
- Identifies installed software via headers, favicons and files
- Host authentication with Basic and NTLM
- Subdomain guessing
- Apache and cgiwrap username enumeration
- Mutation techniques to “fish” for content on web servers
- Scan tuning to include or exclude entire classes of vulnerability checks
- Guess credentials for authorization realms (including many default id/pw combos)
- Authorization guessing handles any directory, not just the root directory
- Enhanced false positive reduction via multiple methods: headers,
- page content, and content hashing
- Reports “unusual” headers seen
- Interactive status, pause and changes to verbosity settings
- Save full request/response for positive tests
- Replay saved positive requests
- Maximum execution time per target
- Auto-pause at a specified time
- Checks for common “parking” sites
- Logging to Metasploit
- Thorough documentation

Source: https://www.cirt.net/Nikto2
[Nikto Homepage](https://www.cirt.net/Nikto2) | [Nikto Documentation](https://cirt.net/nikto2-docs/) | [Kali nikto Repo](https://gitlab.com/kalilinux/packages/nikto.git)

- Author: Chris Sullo & David Lodge
- License: GNU General Public License (GPL)

### Nikto Help

```
root@kali:~# nikto -Help

  Options:
    -ask+        Whether to ask about submitting updates
                yes  Ask about each (default)
                no   Don't ask, don't send
                auto  Don't ask, just send
    -Cgidirs+      Scan these CGI dirs: "none", "all", or values like "/cgi/ /cgi-a/"
    -config+       Use this config file
    -Display+      Turn on/off display outputs:
                1   Show redirects
                2   Show cookies received
                3   Show all 200/OK responses
                4   Show URLs which require authentication
                D   Debug output
                E   Display all HTTP errors
                P   Print progress to STDOUT
                S   Scrub output of IPs and hostnames
                V   Verbose output
    -dbcheck      Check database and other key files for syntax errors
    -evasion+      Encoding technique:
                1   Random URI encoding (non-UTF8)
                2   Directory self-reference (/./)
                3   Premature URL ending
                4   Prepend long random string
                5   Fake parameter
                6   TAB as request spacer
                7   Change the case of the URL
                8   Use Windows directory separator (\)
                A   Use a carriage return (0x0d) as a request spacer
                B   Use binary value 0x0b as a request spacer
    -Format+      Save file (-o) format:
                csv  Comma-separated-value
                htm  HTML Format
                nbe  Nessus NBE format
                sql  Generic SQL (see docs for schema)
                txt  Plain text
                xml  XML Format
                (if not specified the format will be taken from the file extension passed to -output)
    -Help        Extended help information
    -host+       Target host
    -404code      Ignore these HTTP codes as negative responses (always). Format is "302,301".
    -404string     Ignore this string in response body content as negative response (always). Can be a regular expression.
    -id+        Host authentication to use, format is id:pass or id:pass:realm
    -key+        Client certificate key file
    -list-plugins    List all available plugins, perform no testing
    -maxtime+      Maximum testing time per host (e.g., 1h, 60m, 3600s)
    -mutate+      Guess additional file names:
                1   Test all files with all root directories
                2   Guess for password file names
                3   Enumerate user names via Apache (/~user type requests)
                4   Enumerate user names via cgiwrap (/cgi-bin/cgiwrap/~user type requests)
                5   Attempt to brute force sub-domain names, assume that the host name is the parent domain
                6   Attempt to guess directory names from the supplied dictionary file
    -mutate-options   Provide information for mutates
    -nointeractive   Disables interactive features
    -nolookup      Disables DNS lookups
    -nossl       Disables the use of SSL
    -no404       Disables nikto attempting to guess a 404 page
    -Option       Over-ride an option in nikto.conf, can be issued multiple times
    -output+      Write output to this file ('.' for auto-name)
    -Pause+       Pause between tests (seconds, integer or float)
    -Plugins+      List of plugins to run (default: ALL)
    -port+       Port to use (default 80)
    -RSAcert+      Client certificate file
    -root+       Prepend root value to all requests, format is /directory
    -Save        Save positive responses to this directory ('.' for auto-name)
    -ssl        Force ssl mode on port
    -Tuning+      Scan tuning:
                1   Interesting File / Seen in logs
                2   Misconfiguration / Default File
                3   Information Disclosure
                4   Injection (XSS/Script/HTML)
                5   Remote File Retrieval - Inside Web Root
                6   Denial of Service
                7   Remote File Retrieval - Server Wide
                8   Command Execution / Remote Shell
                9   SQL Injection
                0   File Upload
                a   Authentication Bypass
                b   Software Identification
                c   Remote Source Inclusion
                d   WebService
                e   Administrative Console
                x   Reverse Tuning Options (i.e., include all except specified)
    -timeout+      Timeout for requests (default 10 seconds)
    -Userdbs      Load only user databases, not the standard databases
                all  Disable standard dbs and load only user dbs
                tests Disable only db_tests and load udb_tests
    -useragent     Over-rides the default useragent
    -until       Run until the specified time or duration
    -update       Update databases and plugins from CIRT.net
    -useproxy      Use the proxy defined in nikto.conf, or argument http://server:port
    -Version      Print plugin and database versions
    -vhost+       Virtual host (for Host header)
   \+ requires a value

root@kali:~#
```

### Nikto Usage Example

```
root@kali:~# nikto -Display 1234EP -o report.html -Format htm -Tuning 123bde -host 192.168.0.102
\- Nikto v2.1.6
\---------------------------------------------------------------------------
\+ Target IP:      192.168.0.102
\+ Target Hostname:   192.168.0.102
\+ Target Port:     80
\+ Start Time:     2018-03-23 10:49:04 (GMT0)
\---------------------------------------------------------------------------
\+ Server: Apache/2.2.22 (Ubuntu)
\+ Server leaks inodes via ETags, header found with file /, inode: 287, size: 11832, mtime: Fri Feb  2 15:27:56 2018
\+ The anti-clickjacking X-Frame-Options header is not present.
\+ The X-XSS-Protection header is not defined. This header can hint to the user agent to protect against some forms of XSS
\+ The X-Content-Type-Options header is not set. This could allow the user agent to render the content of the site in a different fashion to the MIME type
\+ No CGI Directories found (use '-C all' to force check all possible dirs)
\+ "robots.txt" contains 1 entry which should be manually viewed.
\+ Uncommon header 'tcn' found, with contents: list
\+ Apache mod_negotiation is enabled with MultiViews, which allows attackers to easily brute force file names. See http://www.wisec.it/sectou.php?id=4698ebdc59d15. The following alternatives for 'index' were found: index.html
\+ Apache/2.2.22 appears to be outdated (current is at least Apache/2.4.12). Apache 2.0.65 (final release) and 2.2.29 are also current.
\+ Allowed HTTP Methods: GET, HEAD, POST, OPTIONS
\+ 371 requests: 0 error(s) and 9 item(s) reported on remote host
\+ End Time:      2018-03-23 10:50:44 (GMT0) (100 seconds)
\---------------------------------------------------------------------------
\+ 1 host(s) tested
root@kali:~#
root@kali:~# firefox report.html
```

[webapps](https://tools.kali.org/tag/webapps)

#### Related Posts

[Arachni](https://tools.kali.org/web-applications/arachni)

19 Feb 2014

[SSLyze](https://tools.kali.org/information-gathering/sslyze)

18 Feb 2014

[DirBuster](https://tools.kali.org/web-applications/dirbuster)

18 Feb 2014