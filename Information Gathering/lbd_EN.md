# lbd

February 18, 2014

[Information Gathering](https://tools.kali.org/category/information-gathering)



<iframe src="https://asciinema.org/a/32257/embed?" id="asciicast-iframe-32257" name="asciicast-iframe-32257" scrolling="no" allowfullscreen="true" style="box-sizing: border-box; max-width: 100%; border: 0px; overflow: hidden; margin: 0px; display: inline-block; width: 622px; float: none; visibility: visible; height: 739px;"></iframe>


## lbd Package Description

lbd (load balancing detector) detects if a given domain uses DNS and/or HTTP Load-Balancing (via Server: and Date: header and diffs between server answers).

Source: http://ge.mine.nu/code/lbd
[lbd Homepage](http://ge.mine.nu/code/lbd) | [Kali lbd Repo](https://gitlab.com/kalilinux/packages/lbd.git;a=summary)

- Author: Stefan Behte
- License: GPLv2

### 

### Tools included in the lbd package

##### lbd – Load balancer detector

```
root@kali:~# lbd

lbd - load balancing detector 0.1 - Checks if a given domain uses load-balancing.
Written by Stefan Behte (http://ge.mine.nu)
Proof-of-concept! Might give false positives.
usage: /usr/bin/lbd [domain]
```

### lbd Usage Example

Test to see if the target domain ***(example.com)*** is using a load balancer:

```
root@kali:~# lbd example.com

lbd - load balancing detector 0.1 - Checks if a given domain uses load-balancing.
Written by Stefan Behte (http://ge.mine.nu)
Proof-of-concept! Might give false positives.

Checking for DNS-Loadbalancing: NOT FOUND
Checking for HTTP-Loadbalancing [Server]:
ECS (sea/55ED)
ECS (sea/1C15)
FOUND
```

[infogathering](https://tools.kali.org/tag/infogathering), [recon](https://tools.kali.org/tag/recon), [webapps](https://tools.kali.org/tag/webapps)

#### Related Posts

[DMitry](https://tools.kali.org/information-gathering/dmitry)

18 Feb 2014

[Sublist3r](https://tools.kali.org/information-gathering/sublist3r)

11 Oct 2017

[Gobuster](https://tools.kali.org/web-applications/gobuster)

6 Feb 2017