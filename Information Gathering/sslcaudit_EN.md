## sslcaudit Package Description

The goal of sslcaudit project is to develop a utility to automate testing SSL/TLS clients for resistance against MITM attacks. It might be useful for testing a thick client, a mobile application, an appliance, pretty much anything communicating over SSL/TLS over TCP.

Source: http://www.gremwell.com/sites/default/files/sslcaudit/doc/sslcaudit-user-guide-1.0.pdf
[sslcaudit Homepage](http://www.gremwell.com/sslcaudit_v1_0) | [Kali sslcaudit Repo](https://gitlab.com/kalilinux/packages/sslcaudit.git;a=summary)

- Author: Gremwell
- License: GPLv3

### Tools included in the sslcaudit package

##### sslcaudit – Tests SSL/TLS clients susceptibility to MITM attacks

```
root@kali:~# sslcaudit -h
Usage: sslcaudit [OPTIONS]

Options:
 --version       show program's version number and exit
 -h, --help       show this help message and exit
 -l LISTEN_ON      Specify IP address and TCP PORT to listen on, in
            format of HOST:PORT. Default is 0.0.0.0:8443
 -m MODULES       Launch specific modules. For now the only functional
            module is 'sslcert'. There is also 'dummy' module used
            for internal testing or as a template code for new
            modules. Default is sslcert
 -v VERBOSE       Increase verbosity level. Default is 0. Try 1.
 -d DEBUG_LEVEL     Set debug level. Default is 0, which disables
            debugging output. Try 1 to enable it.
 -c NCLIENTS      Number of clients to handle before quitting. By
            default sslcaudit will quit as soon as it gets one
            client fully processed.
 -N TEST_NAME      Set the name of the test. If specified will appear in
            the leftmost column in the output.
 -T SELF_TEST      Launch self-test. 0 - plain TCP client, 1 - CN
            verifying client, 2 - curl.
 --user-cn=USER_CN   Set user-specified CN.
 --server=SERVER    Where to fetch the server certificate from, in
            HOST:PORT format.
 --user-cert=USER_CERT_FILE
            Set path to file containing the user-supplied
            certificate.
 --user-key=USER_KEY_FILE
            Set path to file containing the user-supplied key.
 --user-ca-cert=USER_CA_CERT_FILE
            Set path to file containing certificate for user-
            supplied CA.
 --user-ca-key=USER_CA_KEY_FILE
            Set path to file containing key for user-supplied CA.
 --no-default-cn    Do not use default CN
 --no-self-signed    Don't try self-signed certificates
 --no-user-cert-signed
            Do not sign server certificates with user-supplied one
```

### sslcaudit Usage Example

Listen on port 443 ***(-l 0.0.0.0:443)*** in verbose mode ***(-v 1)***:

```
root@kali:~# sslcaudit -l 0.0.0.0:443 -v 1
\# filebag location: sslcaudit.1
127.0.0.1:38978  selfsigned(www.example.com)                  tlsv1 alert unknown ca
```