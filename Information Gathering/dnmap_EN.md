## dnmap Package Description

dnmap is a framework to distribute nmap scans among several clients. It reads an already created file with nmap commands and send those commands to each client connected to it.

The framework use a client/server architecture. The server knows what to do and the clients do it. All the logic and statistics are managed in the server. Nmap output is stored on both server and client.

Usually you would want this if you have to scan a large group of hosts and you have several different internet connections (or friends that want to help you).

Source: http://mateslab.weebly.com/dnmap-the-distributed-nmap.html
[dnmap Homepage](http://sourceforge.net/projects/dnmap/) | [Kali dnmap Repo](https://gitlab.com/kalilinux/packages/dnmap.git;a=summary)

- Author: www.mateslab.com.ar
- License: GPLv3

### Tools included in the dnmap package

##### dnmap_client – Distributed nmap framework (client)

```
root@kali:~# dnmap_client -h
+----------------------------------------------------------------------+
| dnmap Client Version 0.6                       |
| This program is free software; you can redistribute it and/or modify |
| it under the terms of the GNU General Public License as published by |
| the Free Software Foundation; either version 2 of the License, or   |
| (at your option) any later version.                  |
|                                    |
| Author: Garcia Sebastian, eldraco@gmail.com              |
| www.mateslab.com.ar                          |
+----------------------------------------------------------------------+

usage: /usr/bin/dnmap_client <options>
options:
 -s, --server-ip     IP address of dnmap server.
 -p, --server-port    Port of dnmap server. Dnmap port defaults to 46001
 -a, --alias    Your name alias so we can give credit to you for your help. Optional
 -d, --debug    Debuging.
 -m, --max-rate    Force nmaps commands to use at most this rate. Useful to slow nmap down. Adds the --max-rate parameter.
```

### dnmap_server – Distributed nmap framework (server)

```
root@kali:~# dnmap_server -h
+----------------------------------------------------------------------+
| dnmap_server Version 0.6                       |
| This program is free software; you can redistribute it and/or modify |
| it under the terms of the GNU General Public License as published by |
| the Free Software Foundation; either version 2 of the License, or   |
| (at your option) any later version.                  |
|                                    |
| Author: Garcia Sebastian, eldraco@gmail.com              |
| www.mateslab.com.ar                          |
+----------------------------------------------------------------------+

usage: /usr/bin/dnmap_server <options>
options:
 -f, --nmap-commands     Nmap commands file
 -p, --port     TCP port where we listen for connections.
 -L, --log-file     Log file. Defaults to /var/log/dnmap_server.conf.
 -l, --log-level    Log level. Defaults to info.
 -v, --verbose_level     Verbose level. Give a number between 1 and 5. Defaults to 1. Level 0 means be quiet.
 -t, --client-timeout     How many time should we wait before marking a client Offline. We still remember its values just in case it cames back.
 -s, --sort       Field to sort the statical value. You can choose from: Alias, #Commands, UpTime, RunCmdXMin, AvrCmdXMin, Status
 -P, --pem-file     pem file to use for TLS connection. By default we use the server.pem file provided with the server in the current directory.

dnmap_server uses a '<nmap-commands-file-name>.dnmaptrace' file to know where it must continue reading the nmap commands file. If you want to start over again,
just delete the '<nmap-commands-file-name>.dnmaptrace' file
```

### dnmap_server Usage Example

Create a text file containing the nmap commands that the clients will run. Pass the file ***dnmap.txt (-f)*** to start the server:

```
root@kali:~# echo "nmap -F 192.168.1.0/24 -v -n -oA sub1" >> dnmap.txt
root@kali:~# echo "nmap -F 192.168.0.0/24 -v -n -oA sub0" >> dnmap.txt
root@kali:~# dnmap_server -f dnmap.txt
+----------------------------------------------------------------------+
| dnmap_server Version 0.6                       |
| This program is free software; you can redistribute it and/or modify |
| it under the terms of the GNU General Public License as published by |
| the Free Software Foundation; either version 2 of the License, or   |
| (at your option) any later version.                  |
|                                    |
| Author: Garcia Sebastian, eldraco@gmail.com              |
| www.mateslab.com.ar                          |
+----------------------------------------------------------------------+

=| MET:0:00:00.000544 | Amount of Online clients: 0 |=

### dnmap_client Usage Example

Connect to the server at ***192.168.1.15 (-s)\*** using the alias ***dnmap-client1 (-a)\***:

root@kali:~# dnmap_client -s 192.168.1.15 -a dnmap-client1
+----------------------------------------------------------------------+
| dnmap Client Version 0.6                       |
| This program is free software; you can redistribute it and/or modify |
| it under the terms of the GNU General Public License as published by |
| the Free Software Foundation; either version 2 of the License, or   |
| (at your option) any later version.                  |
|                                    |
| Author: Garcia Sebastian, eldraco@gmail.com              |
| www.mateslab.com.ar                          |
+----------------------------------------------------------------------+

Client Started...
Nmap output files stored in 'nmap_output' directory...
Starting connection...
Client connected succesfully...
Waiting for more commands....
    Command Executed: nmap -F 192.168.1.0/24 -v -n -oA sub1
```