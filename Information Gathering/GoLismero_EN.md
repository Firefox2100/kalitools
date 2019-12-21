## GoLismero Package Description

GoLismero is an open source framework for security testing. It’s currently geared towards web security, but it can easily be expanded to other kinds of scans.

The most interesting features of the framework are:

- Real platform independence. Tested on Windows, Linux, *BSD and OS X.
- No native library dependencies. All of the framework has been written in pure Python.
- Good performance when compared with other frameworks written in Python and other scripting languages.
- Very easy to use.
- Plugin development is extremely simple.
- The framework also collects and unifies the results of well known tools: sqlmap, xsser, openvas, dnsrecon, theharvester
- Integration with standards: CWE, CVE and OWASP.
- Designed for cluster deployment in mind (not available yet).

Source: https://github.com/golismero/golismero
[GoLismero Homepage](https://github.com/golismero/golismero) | [Kali GoLismero Repo](https://gitlab.com/kalilinux/packages/golismero.git;a=summary)

- Author: Daniel Garcia
- License: GPLv2

### tools included in the golismero package

##### golismero – Web application mapper

```
root@kali:~# golismero -h

/-------------------------------------------\
| GoLismero 2.0.0b6, The Web Knife      |
| Copyright (C) 2011-2014 GoLismero Project |
|                      |
| Contact: contact@golismero-project.com   |
\-------------------------------------------/

usage: golismero.py COMMAND [TARGETS...] [--options]

 SCAN:
  Perform a vulnerability scan on the given targets. Optionally import
  results from other tools and write a report. The arguments that follow may
  be domain names, IP addresses or web pages.

 RESCAN:
  Same as SCAN, but previously run tests are repeated. If the database is
  new, this command is identical to SCAN.

 PROFILES:
  Show a list of available config profiles. This command takes no arguments.

 PLUGINS:
  Show a list of available plugins. This command takes no arguments.

 INFO:
  Show detailed information on a given plugin. The arguments that follow are
  the plugin IDs. You can use glob-style wildcards.

 REPORT:
  Write a report from an earlier scan. This command takes no arguments.
  To specify output files use the -o switch.

 IMPORT:
  Import results from other tools and optionally write a report, but don't
  scan the targets. This command takes no arguments. To specify input files
  use the -i switch.

 DUMP:
  Dump the database from an earlier scan in SQL format. This command takes no
  arguments. To specify output files use the -o switch.

 LOAD:
  Load a database dump from an earlier scan in SQL format. This command takes
  no arguments. To specify input files use the -i switch.

 UPDATE:
  Update GoLismero to the latest version. Requires Git to be installed and
  available in the PATH. This command takes no arguments.

examples:

 scan a website and show the results on screen:
  golismero.py scan http://www.example.com

 grab Nmap results, scan all hosts found and write an HTML report:
  golismero.py scan -i nmap_output.xml -o report.html

 grab results from OpenVAS and show them on screen, but don't scan anything:
  golismero.py import -i openvas_output.xml

 show a list of all available configuration profiles:
  golismero.py profiles

 show a list of all available plugins:
  golismero.py plugins

 show information on all bruteforcer plugins:
  golismero.py info brute_*

 dump the database from a previous scan:
  golismero.py dump -db example.db -o dump.sql
```

### golismero Usage Example

Run a vulnerability scan ***(scan)*** against the targets in the input file ***(-i /root/port80.xml)***, saving the output to a file ***(-o sub1-port80.html)***:

```
root@kali:~# golismero scan -i /root/port80.xml -o sub1-port80.html
```