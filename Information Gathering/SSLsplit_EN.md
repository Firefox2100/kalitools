## SSLsplit Package Description

SSLsplit is a tool for man-in-the-middle attacks against SSL/TLS encrypted network connections. Connections are transparently intercepted through a network address translation engine and redirected to SSLsplit. SSLsplit terminates SSL/TLS and initiates a new SSL/TLS connection to the original destination address, while logging all data transmitted. SSLsplit is intended to be useful for network forensics and penetration testing.

SSLsplit supports plain TCP, plain SSL, HTTP and HTTPS connections over both IPv4 and IPv6. For SSL and HTTPS connections, SSLsplit generates and signs forged X509v3 certificates on-the-fly, based on the original server certificate subject DN and subjectAltName extension. SSLsplit fully supports Server Name Indication (SNI) and is able to work with RSA, DSA and ECDSA keys and DHE and ECDHE cipher suites. SSLsplit can also use existing certificates of which the private key is available, instead of generating forged ones. SSLsplit supports NULL-prefix CN certificates and can deny OCSP requests in a generic way. SSLsplit removes HPKP response headers in order to prevent public key pinning.

Source: https://github.com/droe/sslsplit
[SSLsplit Homepage](https://www.roe.ch/SSLsplit) | [Kali SSLsplit Repo](https://gitlab.com/kalilinux/packages/sslsplit.git;a=summary)

- Author: Daniel Roethlisberger
- License: BSD

### Tools included in the sslsplit package

##### sslsplit – Transparent and scalable SSL/TLS interception

```
root@kali:~# sslsplit -h
Usage: sslsplit [options...] [proxyspecs...]
 -c pemfile  use CA cert (and key) from pemfile to sign forged certs
 -k pemfile  use CA key (and cert) from pemfile to sign forged certs
 -C pemfile  use CA chain from pemfile (intermediate and root CA certs)
 -K pemfile  use key from pemfile for leaf certs (default: generate)
 -q crlurl  use URL as CRL distribution point for all forged certs
 -t certdir  use cert+chain+key PEM files from certdir to target all sites
       matching the common names (non-matching: generate if CA)
 -w gendir  write leaf key and only generated certificates to gendir
 -W gendir  write leaf key and all certificates to gendir
 -O      deny all OCSP requests on all proxyspecs
 -P      passthrough SSL connections if they cannot be split because of
       client cert auth or no matching cert and no CA (default: drop)
 -a pemfile  use cert from pemfile when destination requests client certs
 -b pemfile  use key from pemfile when destination requests client certs
 -g pemfile  use DH group params from pemfile (default: keyfiles or auto)
 -G curve   use ECDH named curve (default: prime256v1)
 -Z      disable SSL/TLS compression on all connections
 -r proto   only support one of tls10 tls11 tls12 (default: all)
 -R proto   disable one of tls10 tls11 tls12 (default: none)
 -s ciphers  use the given OpenSSL cipher suite spec (default: ALL:-aNULL)
 -e engine  specify default NAT engine to use (default: netfilter)
 -E      list available NAT engines and exit
 -u user   drop privileges to user (default if run as root: nobody)
 -m group   when using -u, override group (default: primary group of user)
 -j jaildir  chroot() to jaildir (impacts sni proxyspecs, see manual page)
 -p pidfile  write pid to pidfile (default: no pid file)
 -l logfile  connect log: log one line summary per connection to logfile
 -L logfile  content log: full data to file or named pipe (excludes -S/-F)
 -S logdir  content log: full data to separate files in dir (excludes -L/-F)
 -F pathspec content log: full data to sep files with % subst (excl. -L/-S):
       %T - initial connection time as an ISO 8601 UTC timestamp
       %d - destination host and port
       %D - destination host
       %p - destination port
       %s - source host and port
       %S - source host
       %q - source port
       %% - literal '%'
   e.g.   "/var/log/sslsplit/%T-%s-%d.log"
 -M logfile  log master keys to logfile in SSLKEYLOGFILE format
 -d      daemon mode: run in background, log error messages to syslog
 -D      debug mode: run in foreground, log debug messages on stderr
 -V      print version information and exit
 -h      print usage information and exit
 proxyspec = type listenaddr+port [natengine|targetaddr+port|"sni"+port]
   e.g.   http 0.0.0.0 8080 www.roe.ch 80  # http/4; static hostname dst
       https ::1 8443 2001:db8::1 443  # https/6; static address dst
       https 127.0.0.1 9443 sni 443   # https/4; SNI DNS lookups
       tcp 127.0.0.1 10025        # tcp/4; default NAT engine
       ssl 2001:db8::2 9999 pf      # ssl/6; NAT engine 'pf'
       autossl ::1 10025         # autossl/6; STARTTLS et al
Example:
 sslsplit -k ca.key -c ca.pem -P  https 127.0.0.1 8443  https ::1 8443
```

### sslsplit Usage Example

Run in debug mode ***(-D)***, log the connections ***(-l connections.log)***, set the chroot jail ***(-j /tmp/sslsplit/)***, save files to disk ***(-S /tmp/)***, specify the key ***(-k ca.key)***, specify the cert ***(-c ca.crt)***, specify ssl ***(ssl)***, and configure the proxy ***(0.0.0.0 8443 tcp 0.0.0.0 8080)***:

```
root@kali:~# sslsplit -D -l connections.log -j /tmp/sslsplit/ -S /tmp/ -k ca.key -c ca.crt ssl 0.0.0.0 8443 tcp 0.0.0.0 8080
Generated RSA key for leaf certs.
SSLsplit 0.4.6 (built 2013-06-06)
Copyright (c) 2009-2013, Daniel Roethlisberger 
http://www.roe.ch/SSLsplit
Features: -DDISABLE_SSLV2_SESSION_CACHE -DHAVE_NETFILTER
NAT engines: netfilter\* tproxy
netfilter:  IP_TRANSPARENT SOL_IPV6 !IPV6_ORIGINAL_DST
compiled against OpenSSL 1.0.1e 11 Feb 2013 (1000105f)
rtlinked against OpenSSL 1.0.1e 11 Feb 2013 (1000105f)
TLS Server Name Indication (SNI) supported
OpenSSL is thread-safe with THREADID
```