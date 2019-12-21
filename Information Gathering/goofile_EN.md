<iframe src="https://asciinema.org/a/31264/embed?" id="asciicast-iframe-31264" name="asciicast-iframe-31264" scrolling="no" allowfullscreen="true" style="box-sizing: border-box; max-width: 100%; border: 0px; overflow: hidden; margin: 0px; display: inline-block; width: 686px; float: none; visibility: visible; height: 483px;"></iframe>


## goofile Package Description

Use this tool to search for a specific file type in a given domain.

[goofile Homepage](http://code.google.com/p/goofile/) | [Kali goofile Repo](https://gitlab.com/kalilinux/packages/goofile.git;a=summary)

- Author: Thomas Richards
- License: MIT

### Tools included in the goofile package

##### goofile – Command line filetype search

```
root@kali:~# goofile

\-------------------------------------
|Goofile v1.5            |
|Coded by Thomas (G13) Richards   |
|www.g13net.com           |
|code.google.com/p/goofile      |
\-------------------------------------


Goofile 1.5

usage: goofile options

​    -d: domain to search

​    -f: filetype (ex. pdf)

example:./goofile.py -d test.com -f txt
```

### goofile Usage Example

Search for files from a domain ***(-d kali.org)*** of the PDF filetype ***(-f pdf)***:

```
root@kali:~# goofile -d kali.org -f pdf

\-------------------------------------
|Goofile v1.5            |
|Coded by Thomas (G13) Richards   |
|www.g13net.com           |
|code.google.com/p/goofile      |
\-------------------------------------


Searching in kali.org for pdf
========================================

Files found:
====================

docs.kali.org/pdf/kali-book-fr.pdf
docs.kali.org/pdf/kali-book-es.pdf
docs.kali.org/pdf/kali-book-id.pdf
docs.kali.org/pdf/kali-book-de.pdf
docs.kali.org/pdf/kali-book-it.pdf
docs.kali.org/pdf/kali-book-ar.pdf
docs.kali.org/pdf/kali-book-ja.pdf
docs.kali.org/pdf/kali-book-nl.pdf
docs.kali.org/pdf/kali-book-ru.pdf
docs.kali.org/pdf/kali-book-en.pdf
docs.kali.org/pdf/kali-book-pt-br.pdf
docs.kali.org/pdf/kali-book-zh-hans.pdf
docs.kali.org/pdf/kali-book-sw.pdf
docs.kali.org/pdf/articles/kali-linux-live-usb-install-en.pdf
====================
```