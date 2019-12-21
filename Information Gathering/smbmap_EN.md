## smbmap Package Description

SMBMap allows users to enumerate samba share drives across an entire domain. List share drives, drive permissions, share contents, upload/download functionality, file name auto-download pattern matching, and even execute remote commands. This tool was designed with pen testing in mind, and is intended to simplify searching for potentially sensitive data across large networks.

Source: https://github.com/ShawnDEvans/smbmap
[SMBMap Homepage](https://github.com/ShawnDEvans/smbmap) | [Kali smbmap Repo](https://gitlab.com/kalilinux/packages/smbmap.git)

- Author: ShawnDEvans
- License: GPLv3

### Tools included in the smbmap package

##### [binary-name] – [short description from apt-cache search]

```
root@kali:~# smbmap -h
usage: smbmap.py [-h] (-H HOST | --host-file FILE) [-u USERNAME] [-p PASSWORD]
         [-s SHARE] [-d DOMAIN] [-P PORT] [-x COMMAND] [-L | -R [PATH]
         | -r [PATH]] [-A PATTERN] [-q] [-F PATTERN]
         [--search-path PATH] [--download PATH] [--upload SRC DST]
         [--delete PATH TO FILE] [--skip]

SMBMap - Samba Share Enumerator | Shawn Evans - ShawnDEvans@gmail.com

optional arguments:
 -h, --help       show this help message and exit

Main arguments:
 -H HOST        IP of host
 --host-file FILE    File containing a list of hosts
 -u USERNAME      Username, if omitted null session assumed
 -p PASSWORD      Password or NTLM hash
 -s SHARE        Specify a share (default C$), ex 'C$'
 -d DOMAIN       Domain name (default WORKGROUP)
 -P PORT        SMB port (default 445)

Command Execution:
 Options for executing commands on the specified host

 -x COMMAND       Execute a command ex. 'ipconfig /all'

Filesystem Search:
 Options for searching/enumerating the filesystem of the specified host

 -L           List all drives on the specified host
 -R [PATH]       Recursively list dirs, and files (no share\path lists
            ALL shares), ex. 'C$\Finance'
 -r [PATH]       List contents of directory, default is to list root of
            all shares, ex. -r 'C$\Documents and
            Settings\Administrator\Documents'
 -A PATTERN       Define a file name pattern (regex) that auto downloads
            a file on a match (requires -R or -r), not case
            sensitive, ex '(web|global).(asax|config)'
 -q           Disable verbose output. Only shows shares you have
            READ/WRITE on, and supresses file listing when
            performing a search (-A).

File Content Search:
 Options for searching the content of files

 -F PATTERN       File content search, -F '[Pp]assword' (requies admin
            access to execute commands, and powershell on victim
            host)
 --search-path PATH   Specify drive/path to search (used with -F, default
            C:\Users), ex 'D:\HR\'

Filesystem interaction:
 Options for interacting with the specified host's filesystem

 --download PATH    Download a file from the remote system,
            ex.'C$\temp\passwords.txt'
 --upload SRC DST    Upload a file to the remote system ex.
            '/tmp/payload.exe C$\temp\payload.exe'
 --delete PATH TO FILE
            Delete a remote file, ex. 'C$\temp\msf.exe'
 --skip         Skip delete file confirmation prompt

Examples:

$ smbmap -u jsmith -p password1 -d workgroup -H 192.168.0.1
$ smbmap -u jsmith -p 'aad3b435b51404eeaad3b435b51404ee:da76f2c4c96028b7a6111aef4a50a94d' -H 172.16.0.20
$ smbmap -u 'apadmin' -p 'asdf1234!' -d ACME -h 10.1.3.30 -x 'net group "Domain Admins" /domain'
```

### smbmap Usage Examples

Check for shares on the specified host with the username and password provided.

```
root@kali:~# smbmap -u victim -p s3cr3t -H 192.168.86.61
[+] Finding open SMB ports....
[+] User SMB session establishd on 192.168.86.61...
[+] IP: 192.168.86.61:445  Name: win7-x86.lan
  Disk                           Permissions
  ----                           -----------
  ADMIN$                        NO ACCESS
  C$                          NO ACCESS
  IPC$                         NO ACCESS
  Users                        READ ONLY
```