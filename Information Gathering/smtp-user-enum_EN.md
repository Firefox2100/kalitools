## smtp-user-enum Package Description

smtp-user-enum is a tool for enumerating OS-level user accounts on Solaris via the SMTP service (sendmail). Enumeration is performed by inspecting the responses to VRFY, EXPN and RCPT TO commands. It could be adapted to work against other vulnerable SMTP daemons, but this hasn’t been done as of v1.0.

Source: http://pentestmonkey.net/tools/user-enumeration/smtp-user-enum
[smtp-user-enum Homepage](http://pentestmonkey.net/tools/user-enumeration/smtp-user-enum) | [Kali smtp-user-enum Repo](https://gitlab.com/kalilinux/packages/smtp-user-enum.git;a=summary)

- Author: pentestmonkey
- License: GPLv2

### Tools included in the smtp-user-enum package

##### smtp-user-enum – Username guessing tool primarily for the SMTP service

```
root@kali:~# smtp-user-enum -h
smtp-user-enum v1.2 ( http://pentestmonkey.net/tools/smtp-user-enum )

Usage: smtp-user-enum.pl [options] ( -u username | -U file-of-usernames ) ( -t host | -T file-of-targets )

options are:
    -m n   Maximum number of processes (default: 5)
  -M mode  Method to use for username guessing EXPN, VRFY or RCPT (default: VRFY)
  -u user  Check if user exists on remote system
  -f addr  MAIL FROM email address.  Used only in "RCPT TO" mode (default: user@example.com)
    -D dom  Domain to append to supplied user list to make email addresses (Default: none)
         Use this option when you want to guess valid email addresses instead of just usernames
         e.g. "-D example.com" would guess foo@example.com, bar@example.com, etc.  Instead of
           simply the usernames foo and bar.
  -U file  File of usernames to check via smtp service
  -t host  Server host running smtp service
  -T file  File of hostnames running the smtp service
  -p port  TCP port on which smtp service runs (default: 25)
  -d    Debugging output
  -t n   Wait a maximum of n seconds for reply (default: 5)
  -v    Verbose
  -h    This help message

Also see smtp-user-enum-user-docs.pdf from the smtp-user-enum tar ball.

Examples:

$ smtp-user-enum.pl -M VRFY -U users.txt -t 10.0.0.1
$ smtp-user-enum.pl -M EXPN -u admin1 -t 10.0.0.1
$ smtp-user-enum.pl -M RCPT -U users.txt -T mail-server-ips.txt
$ smtp-user-enum.pl -M EXPN -D example.com -U users.txt -t 10.0.0.1
```

### smtp-user-enum Usage Example

Use the VRFY method ***(-M VRFY)*** to search for the specified user ***(-u root)*** on the target server ***(-t 192.168.1.25)***:

```
root@kali:~# smtp-user-enum -M VRFY -u root -t 192.168.1.25
Starting smtp-user-enum v1.2 ( http://pentestmonkey.net/tools/smtp-user-enum )

 ----------------------------------------------------------
|          Scan Information            |
 ----------------------------------------------------------

Mode ..................... VRFY
Worker Processes ......... 5
Target count ............. 1
Username count ........... 1
Target TCP port .......... 25
Query timeout ............ 5 secs
Target domain ............

######## Scan started at Tue May 13 16:06:28 2014 #########
192.168.1.25: root exists
######## Scan completed at Tue May 13 16:06:29 2014 #########
1 results.

1 queries in 1 seconds (1.0 queries / sec)
```