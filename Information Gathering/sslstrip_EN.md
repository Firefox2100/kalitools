## sslstrip Package Description

sslstrip is a tool that transparently hijacks HTTP traffic on a network, watch for HTTPS links and redirects, and then map those links into look-alike HTTP links or homograph-similar HTTPS links. It also supports modes for supplying a favicon which looks like a lock icon, selective logging, and session denial.

Source: https://github.com/moxie0/sslstrip
[sslstrip Homepage](https://moxie.org/software/sslstrip/) | [Kali sslstrip Repo](https://gitlab.com/kalilinux/packages/sslstrip.git;a=summary)

- Author: Moxie Marlinspike
- License: GPLv3

### Tools included in the sslstrip package

##### sslstrip – SSL/TLS man-in-the-middle attack tool

```
root@kali:~# sslstrip -h

sslstrip 0.9 by Moxie Marlinspike
Usage: sslstrip <options>

Options:
-w <filename>, --write=<filename> Specify file to log to (optional).
-p , --post            Log only SSL POSTs. (default)
-s , --ssl             Log all SSL traffic to and from server.
-a , --all             Log all SSL and HTTP traffic to and from server.
-l <port>, --listen=<port>     Port to listen on (default 10000).
-f , --favicon           Substitute a lock favicon on secure requests.
-k , --killsessions        Kill sessions in progress.
-h                 Print this help message.
```

### sslstrip Usage Example

Write the results to a file ***(-w sslstrip.log)***, listening on port 8080 ***(-l 8080)***:

```
root@kali:~# sslstrip -w sslstrip.log -l 8080

sslstrip 0.9 by Moxie Marlinspike running...
```