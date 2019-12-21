## dnswalk Package Description

dnswalk is a DNS debugger. It performs zone transfers of specified domains, and checks the database in numerous ways for internal consistency, as well as accuracy.

Source: http://sourceforge.net/projects/dnswalk/
[dnswalk Homepage](http://sourceforge.net/projects/dnswalk/) | [Kali dnswalk Repo](https://tools.kali.org/information-gathering/dnswalk)

- Author: David Barr
- License: Artistic

### tools included in the dnswalk package

##### dnswalk – Checks DNS zone information using nameserver lookups

```
root@kali:~# dnswalk --help

Usage: dnswalk [-OPTIONS [-MORE_OPTIONS]] [--] [PROGRAM_ARG1 ...]

The following single-character options are accepted:
With arguments: -D
Boolean (without arguments): -r -f -i -a -d -m -F -l

Options may be merged together. -- stops processing of options.
Space is not required between options and their arguments.
[Now continuing due to backward compatibility and excessive paranoia.
See ``perldoc Getopt::Std'' about $Getopt::Std::STANDARD_HELP_VERSION.]
Usage: dnswalk domain
domain MUST end with a '.'
```

### dnswalk Options

```
-r   Recursively descend sub-domains of the specified domain.
-a   Turn on warning of duplicate A records.
-d   Print debugging and 'status' information to stderr. (Use only if redirecting stdout).
-m   Perform checks only if the zone has been modified since the previous run.
-F   Perform "fascist" checking. When checking an A record, compare the PTR name for each IP address with the forward name and report mismatches.
-i   Suppress check for invalid characters in a domain name.
-l   Perform "lame delegation" checking.  For every NS record, check to see that the listed host is indeed returning authoritative answers for this domain.
```

### dnswalk Usage Example

Attempt to get DNS zone information from the target domain ***(example.com.)***:

```
root@kali:~# dnswalk example.com.
Checking example.com.
```

```
root@kali:~# dnswalk -r -d example.com.
Checking example.com.
```