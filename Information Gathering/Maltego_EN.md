## Maltego Teeth Package Description

Maltego is a unique platform developed to deliver a clear threat picture to the environment that an organization owns and operates. Maltego’s unique advantage is to demonstrate the complexity and severity of single points of failure as well as trust relationships that exist currently within the scope of your infrastructure.

The unique perspective that Maltego offers to both network and resource based entities is the aggregation of information posted all over the internet – whether it’s the current configuration of a router poised on the edge of your network or the current whereabouts of your Vice President on his international visits, Maltego can locate, aggregate and visualize this information.

Maltego offers the user with unprecedented information. Information is leverage. Information is power. Information is Maltego.

What does Maltego do?

Maltego is a program that can be used to determine the relationships and real world links between:

- People
- Groups of people (social networks)
- Companies
- Organizations
- Web sites
- Internet infrastructure such as:
- Domains
- DNS names
- Netblocks
- IP addresses
- Phrases
- Affiliations
- Documents and files
- These entities are linked using open source intelligence.
- Maltego is easy and quick to install – it uses Java, so it runs on Windows, Mac and Linux.
- Maltego provides you with a graphical interface that makes seeing these relationships instant and accurate – making it possible to see hidden connections.
- Using the graphical user interface (GUI) you can see relationships easily – even if they are three or four degrees of separation away.
- Maltego is unique because it uses a powerful, flexible framework that makes customizing possible. As such, Maltego can be adapted to your own, unique requirements.

### What can Maltego do for me?

- Maltego can be used for the information gathering phase of all security related work. It will save you time and will allow you to work more accurately and smarter.
- Maltego aids you in your thinking process by visually demonstrating interconnected links between searched items.
- Maltego provide you with a much more powerful search, giving you smarter results.
- If access to “hidden” information determines your success, Maltego can help you discover it.

Source: http://paterva.com/web6/products/maltego.php
[Maltego Homepage](http://paterva.com/) | [Kali Maltego Teeth Repo](https://gitlab.com/kalilinux/packages/maltego-teeth.git;a=summary)

- Author: Paterva
- License: Commercial

### Maltego Teeth README

```
root@kali:~# cat /opt/Teeth/README.txt
NB NB: This runs on Kali Linux
=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-
\#Make directory /opt/Teeth/
\#Copy tgz to /opt/Teeth/
\#Untar

Load the config file called /opt/Teeth/etc/Maltego_config.mtz file into Maltego.
This is painless:
1) Open Maltego Tungsten (or Radium)
2) Click top left globe/sphere (Application button)
3) Import -> Import configuration, choose /opt/Teeth/etc/Maltego_config.mtz

Notes
\-----
Config file is in /opt/Teeth/etc/TeethConfig.txt
Everything can be set in the config file.

Log file is /var/log/Teeth.log, tail -f it while you running transforms for
real time logs of what's happening.

You can set DEBUG/INFO. DEBUG is useful for seeing progress - set in
/opt/Teeth/units/TeethLib.py line 26

Look in cache/ directory. Here you find caches of:
1) Nmap results
2) Mirrors
3) SQLMAP results

You need to remove cache files by hand if you no longer want them.
You can run housekeep/clear_cache.sh but it removes EVERYTHING.

The WP brute transform uses Metasploit.Start Metasploit server so:
  msfconsole -r /opt/Teeth/static/Teeth-MSF.rc
It takes a while to start, so be patient.

In /housekeep is killswitch.sh - it's the same as killall python.
```