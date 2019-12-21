## Metagoofil Package Description

Metagoofil is an information gathering tool designed for extracting metadata of public documents (pdf,doc,xls,ppt,docx,pptx,xlsx) belonging to a target company.

Metagoofil will perform a search in Google to identify and download the documents to local disk and then will extract the metadata with different libraries like Hachoir, PdfMiner? and others. With the results it will generate a report with usernames, software versions and servers or machine names that will help Penetration testers in the information gathering phase.

Source: http://www.edge-security.com/metagoofil.php
[Metagoofil Homepage](http://www.edge-security.com/metagoofil.php) | [Kali Metagoofil Repo](https://gitlab.com/kalilinux/packages/metagoofil.git;a=summary)

- Author: Christian Martorella
- License: GPLv2

### Tools included in the metagoofil package

##### metagoofil – Tool designed for extracting metadata of public documents

```
root@kali:~# metagoofil

******************************************************
\*   /\/\  ___| |_ __ _  __ _  ___  ___  / _(_) | *
\*   /   \ / _ \ __/ _` |/ _` |/ _ \ / _ \| |_| | | *
\*  / /\/\ \  __/ || (_| | (_| | (_) | (_) |  _| | | *
\*  \/   \/\___|\__\__,_|\__, |\___/ \___/|_| |_|_| *
\*             |___/            *
\* Metagoofil Ver 2.2                 *
\* Christian Martorella                *
\* Edge-Security.com                  *
\* cmartorella_at_edge-security.com          *
******************************************************

 Usage: metagoofil options

​     -d: domain to search
​     -t: filetype to download (pdf,doc,xls,ppt,odp,ods,docx,xlsx,pptx)
​     -l: limit of results to search (default 200)
​     -h: work with documents in directory (use "yes" for local analysis)
​     -n: limit of files to download
​     -o: working directory (location to save downloaded files)
​     -f: output file

 Examples:
 metagoofil.py -d apple.com -t doc,pdf -l 200 -n 50 -o applefiles -f results.html
 metagoofil.py -h yes -o applefiles -f results.html (local dir analysis)
```

### metagoofil Usage Example

Scan for documents from a domain ***(-d kali.org)*** that are PDF files ***(-t pdf)***, searching 100 results ***(-l 100)***, download 25 files ***(-n 25)***, saving the downloads to a directory ***(-o kalipdf)***, and saving the output to a file ***(-f kalipdf.html)***:

```
root@kali:~# metagoofil -d kali.org -t pdf -l 100 -n 25 -o kalipdf -f kalipdf.html

******************************************************
\*   /\/\  ___| |_ __ _  __ _  ___  ___  / _(_) | *
\*   /   \ / _ \ __/ _` |/ _` |/ _ \ / _ \| |_| | | *
\*  / /\/\ \  __/ || (_| | (_| | (_) | (_) |  _| | | *
\*  \/   \/\___|\__\__,_|\__, |\___/ \___/|_| |_|_| *
\*             |___/            *
\* Metagoofil Ver 2.2                 *
\* Christian Martorella                *
\* Edge-Security.com                  *
\* cmartorella_at_edge-security.com          *
******************************************************
['pdf']

[-] Starting online search...

[-] Searching for pdf files, with a limit of 100
    Searching 100 results...
Results: 21 files found
Starting to download 25 of them:
```