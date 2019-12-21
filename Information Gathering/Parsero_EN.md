<iframe src="https://asciinema.org/a/31995/embed?" id="asciicast-iframe-31995" name="asciicast-iframe-31995" scrolling="no" allowfullscreen="true" style="box-sizing: border-box; max-width: 100%; border: 0px; overflow: hidden; margin: 0px; display: inline-block; width: 686px; float: none; visibility: visible; height: 627px;"></iframe>


## Parsero Package Description

Parsero is a free script written in Python which reads the Robots.txt file of a web server and looks at the Disallow entries. The Disallow entries tell the search engines what directories or files hosted on a web server mustn’t be indexed. For example, “Disallow: /portal/login” means that the content on www.example.com/portal/login it’s not allowed to be indexed by crawlers like Google, Bing, Yahoo… This is the way the administrator have to not share sensitive or private information with the search engines.

But sometimes these paths typed in the Disallows entries are directly accessible by the users without using a search engine, just visiting the URL and the Path, and sometimes they are not available to be visited by anybody… Because it is really common that the administrators write a lot of Disallows and some of them are available and some of them are not, you can use Parsero in order to check the HTTP status code of each Disallow entry in order to check automatically if these directories are available or not.

Also, the fact the administrator write a robots.txt, it doesn’t mean that the files or directories typed in the Dissallow entries will not be indexed by Bing, Google, Yahoo… For this reason, Parsero is capable of searching in Bing to locate content indexed without the web administrator authorization. Parsero will check the HTTP status code in the same way for each Bing result.

Source: https://github.com/behindthefirewalls/Parsero
[Parsero Homepage](https://github.com/behindthefirewalls/Parsero) | [Kali parsero Repo](https://gitlab.com/kalilinux/packages/parsero.git;a=tree)

- Author: Javier Nieto
- License: GPLv2

### Tools included in the parsero package

##### parsero – robots.txt audit tool

```
root@kali:~# parsero -h

____
| _ \ __ _ _ __ ___ ___ _ __ ___
| |_) / _` | '__/ __|/ _ \ '__/ _ \
| __/ (_| | | \__ \ __/ | | (_) |
|_| \__,_|_| |___/\___|_| \___/

usage: parsero [-h] [-u URL] [-o] [-sb]

optional arguments:
-h, --help show this help message and exit
-u URL Type the URL which will be analyzed
-o Show only the "HTTP 200" status code
-sb Search in Bing indexed Disallows
```

### parsero Usage Example

Search for results from a website ***(-u www.bing.com)*** using Bing indexed Disallows ***(-sb)***:

```
root@kali:~# parsero -u www.bing.com -sb

____
| _ \ __ _ _ __ ___ ___ _ __ ___
| |_) / _` | '__/ __|/ _ \ '__/ _ \
| __/ (_| | | \__ \ __/ | | (_) |
|_| \__,_|_| |___/\___|_| \___/

Starting Parsero v0.75 (https://github.com/behindthefirewalls/Parsero) at 06/09/14 12:48:25
Parsero scan report for www.bing.com
http://www.bing.com/travel/secure 301 Moved Permanently
http://www.bing.com/travel/flight/flightSearchAction 301 Moved Permanently
http://www.bing.com/travel/css 301 Moved Permanently
http://www.bing.com/results 404 Not Found
http://www.bing.com/spbasic 404 Not Found
http://www.bing.com/entities/search 302 Found
http://www.bing.com/translator/? 200 OK
http://www.bing.com/Proxy.ashx 404 Not Found
http://www.bing.com/images/search? 200 OK
http://www.bing.com/travel/hotel/hotelSearch 301 Moved Permanently
http://www.bing.com/static/ 404 Not Found
http://www.bing.com/offers/proxy/dealsserver/api/log 405 Method Not Allowed
http://www.bing.com/shenghuo 301 Moved Permanently
http://www.bing.com/widget/render 200 OK
```