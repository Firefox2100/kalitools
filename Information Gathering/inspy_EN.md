## inspy Package Description

InSpy is a Python-based LinkedIn enumeration tool with two functionalities: TechSpy and EmpSpy. TechSpy crawls LinkedIn job listings for technologies used by the target company. InSpy attempts to identify technologies by matching job descriptions to keywords from a newline-delimited file.

EmpSpy crawls LinkedIn for employees working at the provided company. InSpy searches for employees by title and/or department from a newline-delimited file. InSpy may also create emails for the identified employees if the user specifies an email format.

Source: https://github.com/gojhonny/InSpy
[InSpy Homepage](https://github.com/gojhonny/InSpy) | [Kali inspy Repo](https://gitlab.com/kalilinux/packages/inspy.git)

- Author: Jonathan Broche
- License: MIT/X11

### Tools included in the inspy package

##### inspy – LinkedIn enumeration tool

```
root@kali:~# inspy -h
usage: inspy [-h] [-v] [--techspy [file]] [--limit int] [--empspy [file]]
       [--emailformat string] [--html file] [--csv file] [--json file]
       company

InSpy - A LinkedIn enumeration tool by Jonathan Broche (@g0jhonny)

positional arguments:
 company        Company name to use for tasks.

optional arguments:
 -h, --help       show this help message and exit
 -v, --version     show program's version number and exit

Technology Search:
 --techspy [file]    Crawl LinkedIn job listings for technologies used by
            the company. Technologies imported from a new line
            delimited file. [Default: tech-list-small.txt]
 --limit int      Limit the number of job listings to crawl. [Default:
            50]

Employee Harvesting:
 --empspy [file]    Discover employees by title and/or department. Titles
            and departments are imported from a new line delimited
            file. [Default: title-list-small.txt]
 --emailformat string  Create email addresses for discovered employees using
            a known format. [Accepted Formats: first.last@xyz.com,
            last.first@xyz.com, firstl@xyz.com, lfirst@xyz.com,
            flast@xyz.com, lastf@xyz.com, first@xyz.com,
            last@xyz.com]

Output Options:
 --html file      Print results in HTML file.
 --csv file       Print results in CSV format.
 --json file      Print results in JSON.
```

### inspy Usage Examples

Search LinkedIn for ***google*** employees (***–empspy***) with the provided wordlist of job titles (***/usr/share/inspy/wordlists/title-list-large.txt***).

```
root@kali:~# inspy --empspy /usr/share/inspy/wordlists/title-list-large.txt google
```

Search for technologies (***–techspy***) in use at the target company (***cisco***) using the provided list of terms (***/usr/share/inspy/wordlists/tech-list-small.txt***).

```
root@kali:~# inspy --techspy /usr/share/inspy/wordlists/tech-list-small.txt cisco
```