## SSLyze Package Description

SSLyze is a Python tool that can analyze the SSL configuration of a server by connecting to it. It is designed to be fast and comprehensive, and should help organizations and testers identify mis-configurations affecting their SSL servers.

Key features include:

- Multi-processed and multi-threaded scanning (it’s fast)
- SSL 2.0/3.0 and TLS 1.0/1.1/1.2 compatibility
- Performance testing: session resumption and TLS tickets support
- Security testing: weak cipher suites, insecure renegotiation, CRIME, Heartbleed and more
- Server certificate validation and revocation checking through OCSP stapling
- Support for StartTLS handshakes on SMTP, XMPP, LDAP, POP, IMAP, RDP and FTP
- Support for client certificates when scanning servers that perform mutual authentication
- XML output to further process the scan results

Source: https://github.com/iSECPartners/sslyze
[SSLyze Homepage](https://github.com/iSECPartners/sslyze) | [Kali SSLyze Repo](https://gitlab.com/kalilinux/packages/sslyze.git;a=summary)

- Author: iSECPartners
- License: GPLv2

### Tools included in the sslyze package

##### sslyze – Fast and full-featured SSL scanner

```
root@kali:~# sslyze -h



 REGISTERING AVAILABLE PLUGINS
 -----------------------------

 PluginSessionResumption
 PluginOpenSSLCipherSuites
 PluginCompression
 PluginCertInfo
 PluginSessionRenegotiation



Usage: sslyze [options] target1.com target2.com:443 etc...

Options:
 --version       show program's version number and exit
 -h, --help       show this help message and exit
 --xml_out=XML_FILE   Writes the scan results as an XML document to the file
            XML_FILE.
 --targets_in=TARGETS_IN
            Reads the list of targets to scan from the file
            TARGETS_IN. It should contain one host:port per line.
 --timeout=TIMEOUT   Sets the timeout value in seconds used for every
            socket connection made to the target server(s).
            Default is 5s.
 --https_tunnel=HTTPS_TUNNEL
            Sets an HTTP CONNECT proxy to tunnel SSL traffic to
            the target server(s). HTTP_TUNNEL should be
            'host:port'. Requires Python 2.7
 --starttls=STARTTLS  Identifies the target server(s) as a SMTP or an XMPP
            server(s) and scans the server(s) using STARTTLS.
            STARTTLS should be 'smtp' or 'xmpp'.
 --xmpp_to=XMPP_TO   Optional setting for STARTTLS XMPP.  XMPP_TO should be
            the hostname to be put in the 'to' attribute of the
            XMPP stream. Default is the server's hostname.
 --regular       Regular HTTPS scan; shortcut for --sslv2 --sslv3
            --tlsv1 --reneg --resum --certinfo --http_get
            --hide_rejected_ciphers --compression --tlsv1_1
            --tlsv1_2

 Client certificate support:
  --cert=CERT     Client certificate filename.
  --certform=CERTFORM
            Client certificate format. DER or PEM (default).
  --key=KEY      Client private key filename.
  --keyform=KEYFORM  Client private key format. DER or PEM (default).
  --pass=KEYPASS    Client private key passphrase.

 PluginSessionResumption:
  Analyzes the target server's SSL session resumption capabilities.

  --resum       Tests the server for session ressumption support,
            using session IDs and TLS session tickets (RFC 5077).
  --resum_rate     Performs 100 session resumptions with the target
            server, in order to estimate the session resumption
            rate.

 PluginOpenSSLCipherSuites:
  Scans the target server for supported OpenSSL cipher suites.

  --sslv2       Lists the SSL 2.0 OpenSSL cipher suites supported by
            the server.
  --sslv3       Lists the SSL 3.0 OpenSSL cipher suites supported by
            the server.
  --tlsv1       Lists the TLS 1.0 OpenSSL cipher suites supported by
            the server.
  --tlsv1_1      Lists the TLS 1.1 OpenSSL cipher suites supported by
            the server.
  --tlsv1_2      Lists the TLS 1.2 OpenSSL cipher suites supported by
            the server.
  --http_get      Option - For each cipher suite, sends an HTTP GET
            request after completing the SSL handshake and returns
            the HTTP status code.
  --hide_rejected_ciphers
            Option - Hides the (usually long) list of cipher
            suites that were rejected by the server.

 PluginCompression:
  --compression    Tests the server for Zlib compression support.

 PluginCertInfo:
  --certinfo=CERTINFO
            Verifies the target server's certificate validity
            against Mozilla's trusted root store, and prints
            relevant fields of the certificate. CERTINFO should be
            'basic' or 'full'.

 PluginSessionRenegotiation:
  --reneg       Tests the target server's support for client-initiated
            renegotiations and secure renegotiations.
```

### sslyze Usage Example

Launch a regular scan type ***(–regular)*** against the target host ***(www.example.com)***:

```
root@kali:~# sslyze --regular www.example.com

 REGISTERING AVAILABLE PLUGINS
 -----------------------------

 PluginCompression
 PluginCertInfo
 PluginSessionResumption
 PluginSessionRenegotiation
 PluginOpenSSLCipherSuites



 CHECKING HOST(S) AVAILABILITY
 -----------------------------

  www.example.com:443         => 93.184.216.119:443



 SCAN RESULTS FOR WWW.EXAMPLE.COM:443 - 93.184.216.119:443
 ---------------------------------------------------------

 * Compression :
    Compression Support:    Disabled

 * Certificate :
   Validation w/ Mozilla's CA Store:  Certificate is Trusted
```