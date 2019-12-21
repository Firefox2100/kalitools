## enumIAX Package Description

enumIAX is an Inter Asterisk Exchange protocol username brute-force enumerator. enumIAX may operate in two distinct modes; Sequential Username Guessing or Dictionary Attack.

Source: http://enumiax.sourceforge.net/
[enumIAX Homepage](http://enumiax.sourceforge.net/) | [Kali enumIAX Repo](https://gitlab.com/kalilinux/packages/enumiax.git;a=summary)

- Author: Dustin D. Trammell
- License: GPLv2

### Tools included in the enumiax package

##### enumiax – IAX protocol username enumerator

```
root@kali:~# enumiax -h
enumIAX 0.4a
Dustin D. Trammell <dtrammell@tippingpoint.com>

Usage: enumiax [options] target
 options:
  -d <dict>  Dictionary attack using <dict> file
  -i <count>  Interval for auto-save (# of operations, default 1000)
  -m #     Minimum username length (in characters)
  -M #     Maximum username length (in characters)
  -r #     Rate-limit calls (in microseconds)
  -s <file>  Read session state from state file
  -v      Increase verbosity (repeat for additional verbosity)
  -V      Print version information and exit
  -h      Print help/usage information and exit
```

### enumiax Usage Example

Run a dictionary attack ***(-d /usr/share/wordlists/metasploit/unix_users.txt)*** against the target host ***(192.168.1.1)***:
```
root@kali:~# enumiax -d /usr/share/wordlists/metasploit/unix_users.txt 192.168.1.1
```