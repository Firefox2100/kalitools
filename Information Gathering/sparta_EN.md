## sparta Package Description

SPARTA is a python GUI application that simplifies network infrastructure penetration testing by aiding the penetration tester in the scanning and enumeration phase. It allows the tester to save time by having point-and-click access to their toolkit and by displaying all tool output in a convenient way. If less time is spent setting up commands and tools, more time can be spent focusing on analysing results.

Source: http://sparta.secforce.com/
[SPARTA Homepage](http://sparta.secforce.com/) | [Kali sparta Repo](https://gitlab.com/kalilinux/packages/sparta.git)

- Author: SECFORCE (Antonio Quina and Leonidas Stavliotis)
- License: GPLv3

### Tools included in the sparta package

##### sparta – Network Infrastructure Penetration Testing Tool

[![SPARTA main window](http://tools.kali.org/wp-content/uploads/2017/03/sparta-01-main.png)](http://tools.kali.org/wp-content/uploads/2017/03/sparta-01-main.png)

### SPARTA Usage Examples

When SPARTA is first launched, either via the Kali Applications menu or by running **sparta** at the command line, the main interface will open, presenting you with your workspace. Initially, the hosts pane will be empty so you can either import an [Nmap](https://tools.kali.org/information-gathering/nmap) scan results file or, as this example shows, click in the pane on the text “***Click here to add host(s) to scope***“.

[![img](http://tools.kali.org/wp-content/uploads/2017/03/sparta-02-scope.png)](http://tools.kali.org/wp-content/uploads/2017/03/sparta-02-scope.png)

After clicking “***Add to scope***“, the Nmap scan will begin and we are presented with a progress indicator in the ***Log*** pane.

[![img](http://tools.kali.org/wp-content/uploads/2017/03/sparta-03-nmap-progress.png)](http://tools.kali.org/wp-content/uploads/2017/03/sparta-03-nmap-progress.png)

The default Nmap scan is quite thorough and will take some time to complete. Once SPARTA has some hosts and ports to work with, it proceeds to run additional tools against the discovered services such as nikto, smbenum, snmpcheck, and more.

[![img](http://tools.kali.org/wp-content/uploads/2017/03/sparta-04-other-tools.png)](http://tools.kali.org/wp-content/uploads/2017/03/sparta-04-other-tools.png)

Selecting a host in the ***Hosts*** pane will display tabs for each of scans that was run against the host, including screenshots of any web servers that it encounters.

[![img](http://tools.kali.org/wp-content/uploads/2017/03/sparta-05-screenshot.png)](http://tools.kali.org/wp-content/uploads/2017/03/sparta-05-screenshot.png)

Services that require a login, such as telnet, SSH, HTTP, etc. can be sent to the brute force tool to try to crack the password. We can do this by right-clicking a service and selecting “”***Send to Brute***“”.

[![img](http://tools.kali.org/wp-content/uploads/2017/03/sparta-06-send-to-brute.png)](http://tools.kali.org/wp-content/uploads/2017/03/sparta-06-send-to-brute.png)

After we configure our settings, we let SPARTA begin attacking the root password over SSH with a pre-defined wordlist.

[![img](http://tools.kali.org/wp-content/uploads/2017/03/sparta-07-brute.png)](http://tools.kali.org/wp-content/uploads/2017/03/sparta-07-brute.png)

SPARTA has many more features available than we covered here and it is worth the time to get to know it better. It can save you a great deal of time in a penetration test by automating many tedious tasks.