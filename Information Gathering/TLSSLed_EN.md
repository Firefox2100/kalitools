## TLSSLed Package Description

TLSSLed is a Linux shell script whose purpose is to evaluate the security of a target SSL/TLS (HTTPS) web server implementation. It is based on sslscan, a thorough SSL/TLS scanner that is based on the openssl library, and on the “openssl s_client” command line tool. The current tests include checking if the target supports the SSLv2 protocol, the NULL cipher, weak ciphers based on their key length (40 or 56 bits), the availability of strong ciphers (like AES), if the digital certificate is MD5 signed, and the current SSL/TLS renegotiation capabilities.

Source: http://www.taddong.com/en/lab.html
[TLSSLed Homepage](http://www.taddong.com/en/lab.html) | [Kali TLSSLed Repo](https://gitlab.com/kalilinux/packages/tlssled.git;a=summary)

- Author: Raul Siles, Taddong SL
- License: GPLv3

### Tools included in the tlssled package

### tlssled – Evaluates the security of a target SSL/TLS (HTTPS) server

```
root@kali:~# tlssled
------------------------------------------------------
 TLSSLed - (1.3) based on sslscan and openssl
         by Raul Siles (www.taddong.com)
------------------------------------------------------
  openssl version: OpenSSL 1.0.1e 11 Feb 2013
  sslscan version 1.8.2
------------------------------------------------------
  Date: 20140520-110731
------------------------------------------------------

[!] Usage: /usr/bin/tlssled <hostname or IP_address> <port>
```

### TLSSLed Usage Example

Check SSL/TLS on the host ***(192.168.1.1)*** and port ***(443)***:

```
root@kali:~# tlssled 192.168.1.1 443
\------------------------------------------------------
 TLSSLed - (1.3) based on sslscan and openssl
         by Raul Siles (www.taddong.com)
\------------------------------------------------------
  openssl version: OpenSSL 1.0.1e 11 Feb 2013
  sslscan version 1.8.2
\------------------------------------------------------
  Date: 20140513-165131
\------------------------------------------------------

[*] Analyzing SSL/TLS on 192.168.1.1:443 ...
  [.] Output directory: TLSSLed_1.3_192.168.1.1_443_20140513-165131 ...

[*] Checking if the target service speaks SSL/TLS...
  [.] The target service 192.168.1.1:443 seems to speak SSL/TLS...

  [.] Using SSL/TLS protocol version:
    (empty means I'm using the default openssl protocol version(s))

[*] Running sslscan on 192.168.1.1:443 ...

  [-] Testing for SSLv2 ...

  [-] Testing for the NULL cipher ...
```