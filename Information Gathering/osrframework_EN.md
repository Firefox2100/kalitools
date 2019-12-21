## osrframework Package Description

OSRFramework is a set of libraries to perform Open Source Intelligence tasks. They include references to a bunch of different applications related to username checking, DNS lookups, information leaks research, deep web search, regular expressions extraction, and many others. At the same time, by means of ad-hoc Maltego transforms, OSRFramework provides a way of making these queries graphically as well as several interfaces to interact with like OSRFConsole or a Web interface.

Source: https://github.com/i3visio/osrframework
[OSRFramework Homepage](https://github.com/i3visio/osrframework) | [Kali osrframework Repo](https://gitlab.com/kalilinux/packages/osrframework.git)

- Author: i3visio
- License: AGPLv3+

### Tools included in the osrframework package

##### usufy.py – checks for a user profile in up to 290 different platforms

```
root@kali:~# usufy.py -h
usage: usufy.py
        (--info <action> | --license | -b | -f <path_to_fuzzing_list> | -l <path_to_nick_list> | -n <nick> [<nick> ...] | --show_tags)
        [-p <platform> [<platform> ...]] [-t <tag> [<tag> ...]]
        [-x <platform> [<platform> ...]] [--avoid_download]
        [--avoid_processing] [--fuzz_config <path_to_fuzz_list>]
        [--nonvalid <not_valid_characters>]
        [-e <sum_ext> [<sum_ext> ...]] [-L <path_to_log_folder] [-m]
        [-o <path_to_output_folder>] [-w]
        [-F <alternative_header_file>] [-T <num_threads>] [-h]
        [-v <verbosity>] [--version]

usufy.py - Piece of software that checks the existence of a profile for a
given user in up to 290 different platforms.

Input options (one required):
 --info <action>    select the action to be performed amongst the
            following: list_platforms (list the details of the
            selected platforms), list_tags (list the tags of the
            selected platforms). Afterwards, it exists.
 --license       shows the AGPLv3+ license and exists.
 -b, --benchmark    perform the benchmarking tasks.
 -f <path_to_fuzzing_list>, --fuzz <path_to_fuzzing_list>
            this option will try to find usufy-like URLs. The list
            of fuzzing platforms in the file should be (one per
            line): <BASE_DOMAIN> <VALID_NICK>
 -l <path_to_nick_list>, --list <path_to_nick_list>
            path to the file where the list of nicks to verify is
            stored (one per line).
 -n <nick> [<nick> ...], --nicks <nick> [<nick> ...]
            the list of nicks to process (at least one is
            required).
 --show_tags      it will show the platforms grouped by tags.

Platform selection arguments:
 Criteria for selecting the platforms where performing the search.

 -p <platform> [<platform> ...], --platforms <platform> [<platform> ...]
            select the platforms where you want to perform the
            search amongst the following: ['all', '500px', 'abou',
            'about', 'affilorama', 'anarchy101', 'angel',
            'archive', 'arduino', 'ariva', 'armorgames', 'askfm',
            'audiob', 'audioboo', 'authorstream', 'autospies',
            'badoo', 'bandcamp', 'bebee', 'behance', 'bennugd',
            'betblog', 'bitbucket', 'bitcointa', 'bitcointalk',
            'bitly', 'bitrated', 'blackplanet', 'blip',
            'blogmarks', 'blogspot', 'bookofmatches', 'boonex',
            'bordom', 'boxedup', 'breakcom', 'bubok',
            'bucketlistly', 'buddypic', 'burbuja.info',
            'burdastyle', 'buzznet', 'cafemom', 'canva',
            'carbonmade', 'cardinghispano', 'cardingmx',
            'cardomain', 'care2', 'cartodb', 'cash', 'castroller',
            'causes', 'ccm', 'ccsinfo', 'chess', 'cockos',
            'codecademy', 'codementor', 'coderwall', 'coinbase',
            'colourlovers', 'connectingsingles', 'contently',
            'couchsurfing', 'crokes', 'crowdin', 'cryptofresh',
            'dailymotion', 'datpiff', 'deviantart', 'digitalspy',
            'disqus', 'doodle', 'douban', 'dreamstime',
            'dribbble', 'drugbuyersforum', 'drupal', 'dzone',
            'ebay', 'echatta', 'ehow', 'eightbitme', 'ello',
            'elmundo', 'emoneyspace', 'enfemenino', 'ethereum',
            'etsy', 'eyeem', 'f6s', 'facebook', 'fanpop', 'fark',
            'favstar', 'fiverr', 'flickr', 'flixster',
            'foodspotting', 'forobtc', 'forocoches', 'foroptc',
            'foros24h', 'forosperu', 'forospyware', 'fotolog',
            'foursquare', 'freelancer', 'freerepublic',
            'gamesheep', 'gametracker', 'gapyear', 'gather',
            'geeksphone', 'genspot', 'getlocalization',
            'getsatisfaction', 'github', 'goblinrefuge',
            'goodreads', 'googleplus', 'gravatar', 'gsmspain',
            'hi5', 'houzz', 'htcmania', 'hubpages', 'ibosocial',
            'identica', 'ifunny', 'imgur', 'inkonsky',
            'instagram', 'instructables', 'intfiction',
            'islamicawakening', 'issuu', 'ivoox', 'jamiiforums',
            'kali', 'kanogames', 'karmacracy', 'keybase',
            'kickstarter', 'kinja', 'kiwi', 'klout', 'kongregate',
            'kupika', 'lastfm', 'leakforums', 'linkedin',
            'livejournal', 'looki', 'losviajeros', 'marca',
            'matchdoctor', 'mcneel', 'mediavida', 'medium',
            'meneame', 'mercadolibre', 'metacafe', 'meteor',
            'mig', 'migente', 'miiverse', 'minecraft',
            'moneymaker', 'mozilla', 'musicasacra', 'myeloma',
            'myfitnesspal', 'myspace', 'nairaland', 'netlog',
            'netvibes', 'newgrounds', 'notabug', 'occupywallst',
            'odnoklassniki', 'okcupid', 'onename',
            'openbugbounty', 'openframeworks', 'openstreetmap',
            'papaly', 'pastebin', 'patreon', 'pearltrees',
            'peerbackers', 'periscope', 'phishtank',
            'photobucket', 'pixinsight', 'pixls', 'pjrc',
            'pokerred', 'pokerstrategy', 'pornhub', 'proboards',
            'pz', 'qq', 'quartermoonsaloon', 'rankia', 'rapid-i',
            'rapid7', 'ratemypoo', 'realcarders', 'rebelmouse',
            'reddit', 'redtube', 'researchgate', 'reverbnation',
            'ripenear', 'rojadirecta', 'ruby', 'sarahah',
            'scribd', 'seatwish', 'sencha', 'sidereel',
            'singletrackworld', 'skype', 'slashdot', 'slideshare',
            'smartcitizen', 'smugmug', 'soundcloud', 'soup',
            'sourceforge', 'spaniards', 'spoj', 'spotify',
            'spreaker', 'squidoo', 'steamcommunity', 'steemit',
            'steinberg', 'streakgaming', 'taringa',
            'teamtreehouse', 'techcrunch', 'technorati',
            'thehoodup', 'thesims', 'thestudentroom', 'theverge',
            'tipme', 'tradimo', 'trakt', 'translate_hola', 'trip',
            'tripadvisor', 'tripit', 'trulia', 'tumblr', 'tune',
            'tuporno', 'twicsy', 'twitch', 'twitter',
            'twoplustwo', 'typepad', 'unioncarder', 'ustream',
            'v7n', 'venmo', 'vexforum', 'viddler', 'videohelp',
            'vimeo', 'virustotal', 'vk', 'warriorforum', 'webtv',
            'wikia', 'wikipedia', 'winamp', 'wishlistr', 'witty',
            'wykop', 'xanga', 'xing', 'xtube', 'younow',
            'youtube', 'zabbix', 'zentyal', 'zotero']. More than
            one option can be selected.
 -t <tag> [<tag> ...], --tags <tag> [<tag> ...]
            select the list of tags that fit the platforms in
            which you want to perform the search. More than one
            option can be selected.
 -x <platform> [<platform> ...], --exclude <platform> [<platform> ...]
            select the platforms that you want to exclude from the
            processing.

Processing arguments:
 Configuring the way in which usufy will process the identified profiles.

 --avoid_download    argument to force usufy NOT to store the downloadable
            version of the profiles.
 --avoid_processing   argument to force usufy NOT to perform any processing
            task with the valid profiles.
 --fuzz_config <path_to_fuzz_list>
            path to the fuzzing config details. Wildcards such as
            the domains or the nicknames should come as: <DOMAIN>,
            <USERNAME>.
 --nonvalid <not_valid_characters>
            string containing the characters considered as not
            valid for nicknames.
 -e <sum_ext> [<sum_ext> ...], --extension <sum_ext> [<sum_ext> ...]
            output extension for the summary files. Default: xls.
 -L <path_to_log_folder, --logfolder <path_to_log_folder
            path to the log folder. If none was provided, ./logs
            is assumed.
 -m, --maltego     parameter specified to let usufy.py know that he has
            been launched by a Maltego Transform.
 -o <path_to_output_folder>, --output_folder <path_to_output_folder>
            output folder for the generated documents. While if
            the paths does not exist, usufy.py will try to create;
            if this argument is not provided, usufy will NOT write
            any down any data. Check permissions if something goes
            wrong.
 -w, --web_browser   opening the uris returned in the default web browser.
 -F <alternative_header_file>, --file_header <alternative_header_file>
            Header for the output filenames to be generated. If
            None was provided the following will be used:
            profiles.<extension>.
 -T <num_threads>, --threads <num_threads>
            write down the number of threads to be used (default
            32). If 0, the maximum number possible will be used,
            which may make the system feel unstable.

About arguments:
 Showing additional information about this program.

 -h, --help       shows this help and exists.
 -v <verbosity>, --verbose <verbosity>
            select the verbosity level: 0 - none; 1 - normal
            (default); 2 - debug.
 --version       shows the version of the program and exists.

Check the README.md file for further details on the usage of this program or
follow us on Twitter in <http://twitter.com/i3visio>.
```

##### mailfy.py – Check for the existence of a given mail

```
root@xulu:~# mailfy.py -h
usage: mailfy.py
         (--license | -m <emails> [<emails> ...] | -M <emails_file> | -n <nicks> [<nicks> ...] | -N <nicks_file> | --create_emails <nicks_file>)
         [-e <sum_ext> [<sum_ext> ...]]
         [-d <candidate_domains> [<candidate_domains> ...]]
         [-o <path_to_output_folder>] [-x <domain> [<domain> ...]]
         [-F <alternative_header_file>] [-T <num_threads>]
         [--is_leaked] [--quiet] [-h] [--version]

mailfy.py - Checking the existence of a given mail.

Input options (one required):
 --license       shows the GPLv3+ license and exists.
 -m <emails> [<emails> ...], --emails <emails> [<emails> ...]
            the list of emails to be checked.
 -M <emails_file>, --emails_file <emails_file>
            the file with the list of emails.
 -n <nicks> [<nicks> ...], --nicks <nicks> [<nicks> ...]
            the list of nicks to be checked in the domains
            selected.
 -N <nicks_file>, --nicks_file <nicks_file>
            the file with the list of nicks to be checked in the
            domains selected.
 --create_emails <nicks_file>
            the file with the list of nicks to be created in the
            domains selected.

Processing arguments:
 Configuring the way in which mailfy will process the identified profiles.

 -e <sum_ext> [<sum_ext> ...], --extension <sum_ext> [<sum_ext> ...]
            output extension for the summary files. Default: xls.
 -d <candidate_domains> [<candidate_domains> ...], --domains <candidate_domains> [<candidate_domains> ...]
            list of domains where the nick will be looked for.
 -o <path_to_output_folder>, --output_folder <path_to_output_folder>
            output folder for the generated documents. While if
            the paths does not exist, usufy.py will try to create;
            if this argument is not provided, usufy will NOT write
            any down any data. Check permissions if something goes
            wrong.
 -x <domain> [<domain> ...], --exclude <domain> [<domain> ...]
            select the domains to be excluded from the search.
 -F <alternative_header_file>, --file_header <alternative_header_file>
            Header for the output filenames to be generated. If
            None was provided the following will be used:
            profiles.<extension>.
 -T <num_threads>, --threads <num_threads>
            write down the number of threads to be used (default
            16). If 0, the maximum number possible will be used,
            which may make the system feel unstable.
 --is_leaked      Defines whether mailfy.py should search for leaked
            emails instead of verifying them.
 --quiet        tells the program not to show anything.

About arguments:
 Showing additional information about this program.

 -h, --help       shows this help and exists.
 --version       shows the version of the program and exists.

Check the README.md file for further details on the usage of this program or
follow us on Twitter in <http://twitter.com/i3visio>.
```

##### searchfy.py – Performs a query on the platforms in OSRFramework.

```
root@kali:~$ searchfy.py -h
Configuring OSRFramework working directory for Maltego...
Building the .mtz file.
Moving the .mtz file to the following folder: /home/dookie/osrframework-maltego-settings_v0.11.mtz
Moving the .mtz file to the backup folder:   /home/dookie/.config/OSRFramework/default/osrframework-maltego-settings_v0.11.mtz
usage: searchfy.py (--license | -q <searches> [<searches> ...])
          [-e <sum_ext> [<sum_ext> ...]]
          [-F <alternative_header_file>] [-m]
          [-o <path_to_output_folder>]
          [-p <platform> [<platform> ...]] [--process] [-w]
          [-x <platform> [<platform> ...]] [-h] [--version]

searchfy.py - Piece of software that performs a query on the platforms in
OSRFramework.

Input options (one required):
 --license       shows the GPLv3+ license and exists.
 -q <searches> [<searches> ...], --queries <searches> [<searches> ...]
            the list of queries to be performed).

Processing arguments:
 Configuring the way in which searchfy will process the identified
 profiles.

 -e <sum_ext> [<sum_ext> ...], --extension <sum_ext> [<sum_ext> ...]
            output extension for the summary files. Default: xls.
 -F <alternative_header_file>, --file_header <alternative_header_file>
            Header for the output filenames to be generated. If
            None was provided the following will be used:
            profiles.<extension>
 -m, --maltego     Parameter specified to let usufy.py know that he has
            been launched by a Maltego Transform.
 -o <path_to_output_folder>, --output_folder <path_to_output_folder>
            output folder for the generated documents. While if
            the paths does not exist, usufy.py will try to create;
            if this argument is not provided, usufy will NOT write
            any down any data. Check permissions if something goes
            wrong.
 -p <platform> [<platform> ...], --platforms <platform> [<platform> ...]
            select the platforms where you want to perform the
            search amongst the following: ['all', 'facebook',
            'github', 'pgpmit', 'skype', 'twitter', 'youtube'].
            More than one option can be selected.
 --process       whether to process the info in the profiles recovered.
            NOTE: this would be much slower.
 -w, --web_browser   opening the URIs returned in the default web browser.
 -x <platform> [<platform> ...], --exclude <platform> [<platform> ...]
            select the platforms that you want to exclude from the
            processing.

About arguments:
 Showing additional information about this program.

 -h, --help       shows this help and exists.
 --version       shows the version of the program and exists.

Check the README.md file for further details on the usage of this program or
follow us on Twitter in <http://twitter.com/i3visio>.
```

##### domainfy.py – Checks for the existence of domains

```
root@kali:~# domainfy.py -h
usage: domainfy.py (--license | -n <nicks> [<nicks> ...] | -N <nicks_file>)
          [-e <sum_ext> [<sum_ext> ...]] [-o <path_to_output_folder>]
          [-t <tld_type> [<tld_type> ...]]
          [-u <new_tld> [<new_tld> ...]] [-x <domain> [<domain> ...]]
          [-F <alternative_header_file>] [-T <num_threads>] [--quiet]
          [-h] [--version]

domainfy.py - Checking the existence of domains.

Input options (one required):
 --license       shows the GPLv3+ license and exists.
 -n <nicks> [<nicks> ...], --nicks <nicks> [<nicks> ...]
            the list of nicks to be checked in the domains
            selected.
 -N <nicks_file>, --nicks_file <nicks_file>
            the file with the list of nicks to be checked in the
            domains selected.

Processing arguments:
 Configuring the way in which mailfy will process the identified profiles.

 -e <sum_ext> [<sum_ext> ...], --extension <sum_ext> [<sum_ext> ...]
            output extension for the summary files. Default: xls.
 -o <path_to_output_folder>, --output_folder <path_to_output_folder>
            output folder for the generated documents. While if
            the paths does not exist, usufy.py will try to create;
            if this argument is not provided, usufy will NOT write
            any down any data. Check permissions if something goes
            wrong.
 -t <tld_type> [<tld_type> ...], --tlds <tld_type> [<tld_type> ...]
            List of tld types where the nick will be looked for.
 -u <new_tld> [<new_tld> ...], --user_defined <new_tld> [<new_tld> ...]
            Additional TLD that will be searched.
 -x <domain> [<domain> ...], --exclude <domain> [<domain> ...]
            select the domains to be avoided. The format should
            include the initial '.'.
 -F <alternative_header_file>, --file_header <alternative_header_file>
            Header for the output filenames to be generated. If
            None was provided the following will be used:
            profiles.<extension>.
 -T <num_threads>, --threads <num_threads>
            write down the number of threads to be used (default
            16). If 0, the maximum number possible will be used,
            which may make the system feel unstable.
 --quiet        tells the program not to show anything.

About arguments:
 Showing additional information about this program.

 -h, --help       shows this help and exists.
 --version       shows the version of the program and exists.

Check the README.md file for further details on the usage of this program or
follow us on Twitter in <http://twitter.com/i3visio>.
```

##### phonefy.py – Checks for the existence of a given series of phones

```
root@kali:~# phonefy.py -h
usage: phonefy.py (--license | -n <phones> [<phones> ...])
         [-e <sum_ext> [<sum_ext> ...]] [-o <path_to_output_folder>]
         [-p <platform> [<platform> ...]]
         [-F <alternative_header_file>] [--quiet] [-w]
         [-x <platform> [<platform> ...]] [-h] [--version]

phonefy.py - Piece of software that checks the existence of a given series of
phones in a bunch of phone number lists associated to malicious activities.

Input options (one required):
 --license       shows the GPLv3+ license and exists.
 -n <phones> [<phones> ...], --numbers <phones> [<phones> ...]
            the list of phones to process (at least one is
            required).

Processing arguments:
 Configuring the way in which usufy will process the identified profiles.

 -e <sum_ext> [<sum_ext> ...], --extension <sum_ext> [<sum_ext> ...]
            output extension for the summary files. Default: xls.
 -o <path_to_output_folder>, --output_folder <path_to_output_folder>
            output folder for the generated documents. While if
            the paths does not exist, usufy.py will try to create;
            if this argument is not provided, usufy will NOT write
            any down any data. Check permissions if something goes
            wrong.
 -p <platform> [<platform> ...], --platforms <platform> [<platform> ...]
            select the platforms where you want to perform the
            search amongst the following: ['all',
            'infotelefonica', 'kimatel', 'listaspam']. More than
            one option can be selected.
 -F <alternative_header_file>, --file_header <alternative_header_file>
            Header for the output filenames to be generated. If
            None was provided the following will be used:
            profiles.<extension>.
 --quiet        tells the program not to show anything.
 -w, --web_browser   opening the URIs returned in the default web browser.
 -x <platform> [<platform> ...], --exclude <platform> [<platform> ...]
            select the platforms that you want to exclude from the
            processing.

About arguments:
 Showing additional information about this program.

 -h, --help       shows this help and exists.
 --version       shows the version of the program and exists.

Check the README.md file for further details on the usage of this program or
follow us on Twitter in <http://twitter.com/i3visio>.
```

##### entify.py – Use regular expressions to extract entities

```
root@kali:~# entify.py -h
usage: entify.py (-r <name> [<name> ...] | -R <regular_expression>)
         (-i <path_to_input_folder> | -w <url>)
         [-e <sum_ext> [<sum_ext> ...]] [-o <path_to_output_folder>]
         [-v <verbosity>] [-F <alternative_header_file>] [-q]
         [-L <path_to_log_folder] [--recursive] [-h] [--version]

entify.py - entify.py is a program designed to extract using regular
expressions all the entities from the files on a given folder. This software
also provides an interface to look for these entities in any given text.

Input options (one required):
 -r <name> [<name> ...], --regexp <name> [<name> ...]
            select the regular expressions to be looked for
            amongst the following: ['all',
            'i3visio.bitcoin.address', 'i3visio.dni',
            'i3visio.dogecoin.address', 'i3visio.email',
            'i3visio.ipv4', 'i3visio.litecoin.address',
            'i3visio.md5', 'i3visio.namecoin.address',
            'i3visio.peercoin.address', 'i3visio.sha1',
            'i3visio.sha256', 'i3visio.uri']
 -R <regular_expression>, --new_regexp <regular_expression>
            add a new regular expression, for example, for testing
            purposes.
 -i <path_to_input_folder>, --input_folder <path_to_input_folder>
            path to the folder to analyse.
 -w <url>, --web <url>
            URI to be recovered and analysed.

Processing arguments:
 Configuring the processing parameters.

 -e <sum_ext> [<sum_ext> ...], --extension <sum_ext> [<sum_ext> ...]
            output extension for the summary files. Default: xls.
 -o <path_to_output_folder>, --output_folder <path_to_output_folder>
            output folder for the generated documents. While if
            the paths does not exist, usufy.py will try to create;
            if this argument is not provided, usufy will NOT write
            any down any data. Check permissions if something goes
            wrong.
 -v <verbosity>, --verbose <verbosity>
            select the verbosity level: 0 - none; 1 - normal
            (default); 2 - debug.
 -F <alternative_header_file>, --file_header <alternative_header_file>
            Header for the output filenames to be generated. If
            None was provided the following will be used:
            profiles.<extension>.
 -q, --quiet      Asking the program not to show any output.
 -L <path_to_log_folder, --logfolder <path_to_log_folder
            path to the log folder. If none was provided, ./logs
            is assumed.
 --recursive      Variable to tell the system to perform a recursive
            search on the folder tree.

About arguments:
 Showing additional information about this program.

 -h, --help       shows this help and exists.
 --version       shows the version of the program and exists.

Check the README.md file for further details on the usage of this program or
follow us on Twitter in <http://twitter.com/i3visio>.
```

##### osrfconsole.py – Open Sources Research Framework console interface

```
root@kali:~# osrfconsole.py

 ___  ____  ____  _____                       _
 / _ \/ ___||  _ \|  ___| __ __ _ _ __ ___  _____    _____  _ __| | __
| | | \___ \| |_) | |_ | '__/ _` | '_ ` _ \ / _ \ \ /\ / / _ \| '__| |/ /
| |_| |___) |  _ <|  _|| | | (_| | | | | | |  __/\ V  V / (_) | |  |  <
 \___/|____/|_| \_\_|  |_|  \__,_|_| |_| |_|\___| \_/\_/ \___/|_|  |_|\_

​        Version:    OSRFramework 0.17.2
​        Created by:  Felix Brezo and Yaiza Rubio, (i3visio)


    OSRFConsole v6.0 - Copyright (C) F. Brezo and Y. Rubio (i3visio) 2016-2017

This program comes with ABSOLUTELY NO WARRANTY.
This is free software, and you are welcome to redistribute it under certain conditions.  For additional info, visit to <http://www.gnu.org/licenses/gpl-3.0.txt>.
  General information
  ===================
  OSRFramework stands for Open Sources Research Framework. It includes a set of tools that help the analyst in the task of user profiling making use of different OSINT tools. To get additional information about the available commands type 'help'.

  Modules available:
  \------------------
    \- usufy --> the Jewel of the Chrown. A tool that verifies if a username exists in 291 platforms.
    \- mailfy --> a tool to check if a username has been registered in up to 22 email providers.
    \- searchfy --> a tool to look for profiles using full names and other info in 7 platforms.
    \- domainfy --> a tool to check the existence of a given domain in up to 1567 different TLD.
    \- phonefy --> a tool that checks if a phone number has been linked to spam practices in 4 platforms.
    \- entify --> a util to look for regular expressions using 13 patterns.

osrf >
```

##### osrframework_server.py – Open Sources Research Framework web interface

```
root@kali:~# osrframework_server.py -h
usage: ./osrframework-server.py [--host <IP>] [--port <PORT>] [--debug] [-h]
                [--version]

OSRFramework Server - The tool that will start a local server.

Configuration arguments:
 Configuring the processing parameters.

 --host <IP>   choose the host in which the server will be accesible. If
         "0.0.0.0" is choosen, the server will be accesible by any
         remote machine. Use this carefully. Default: localhost.
 --port <PORT>  choose the port in which the server will be accesible. Use
         this carefully.
 --debug     choose whether error messages will be deployed. Do NOT use
         this for production.

About arguments:
 Showing additional information about this program.

 -h, --help   shows this help and exists.
 --version    shows the version of the program and exists.

Check the README.md file for further details on the usage of this program or
follow us on Twitter in <http://twitter.com/i3visio>.
```

### osrframework Usage Examples

Check for the ***-n kalilinux*** username across all available services.

```
root@kali:~# usufy.py -n kalilinux

 ___  ____  ____  _____                       _
 / _ \/ ___||  _ \|  ___| __ __ _ _ __ ___  _____    _____  _ __| | __
| | | \___ \| |_) | |_ | '__/ _` | '_ ` _ \ / _ \ \ /\ / / _ \| '__| |/ /
| |_| |___) |  _ <|  _|| | | (_| | | | | | |  __/\ V  V / (_) | |  |  <
 \___/|____/|_| \_\_|  |_|  \__,_|_| |_| |_|\___| \_/\_/ \___/|_|  |_|\_

​        Version:    OSRFramework 0.17.2
​        Created by:  Felix Brezo and Yaiza Rubio, (i3visio)



usufy.py Copyright (C) F. Brezo and Y. Rubio (i3visio) 2014-2017

This program comes with ABSOLUTELY NO WARRANTY. This is free software, and you
are welcome to redistribute it under certain conditions. For additional info,
visit https://www.gnu.org/licenses/agpl-3.0.txt

2017-10-05 11:20:10.448178 Starting search in 297 platform(s)... Relax!

  Press <Ctrl + C> to stop...

[!] In skype.py, exception caught when checking information in Skype!

2017-10-05 11:20:30.854308 A summary of the results obtained are shown in the following table:

Sheet Name: Profiles recovered (2017-10-5_11h20m).
+-----------------------------------------------------------------+---------------+-------------------+
|              i3visio_uri              | i3visio_alias | i3visio_platform  |
+=================================================================+===============+===================+
| https://www.facebook.com/kalilinux                | kalilinux   | Facebook      |
+-----------------------------------------------------------------+---------------+-------------------+
| http://twitter.com/kalilinux                   | kalilinux   | Twitter      |
+-----------------------------------------------------------------+---------------+-------------------+
...
```

Search for a given email address.

```
root@kali:~# mailfy.py -n ltorvalds

 ___  ____  ____  _____                       _
 / _ \/ ___||  _ \|  ___| __ __ _ _ __ ___  _____    _____  _ __| | __
| | | \___ \| |_) | |_ | '__/ _` | '_ ` _ \ / _ \ \ /\ / / _ \| '__| |/ /
| |_| |___) |  _ <|  _|| | | (_| | | | | | |  __/\ V  V / (_) | |  |  <
 \___/|____/|_| \_\_|  |_|  \__,_|_| |_| |_|\___| \_/\_/ \___/|_|  |_|\_

​        Version:    OSRFramework 0.17.2
​        Created by:  Felix Brezo and Yaiza Rubio, (i3visio)


mailfy.py Copyright (C) F. Brezo and Y. Rubio (i3visio) 2016-2017

This program comes with ABSOLUTELY NO WARRANTY. This is free software, and you
are welcome to redistribute it under certain conditions. For additional info,
visit https://www.gnu.org/licenses/agpl-3.0.txt

2017-10-05 11:32:49.178753 Starting search in 22 different emails:
[
 "ltorvalds@000.com",
 "ltorvalds@111.com",
 "ltorvalds@000.cn",
...
```

Search for a given string across all OSRF services.

```
root@kali:~$ searchfy.py -q "dookie2000ca"

 ___  ____  ____  _____                       _
 / _ \/ ___||  _ \|  ___| __ __ _ _ __ ___  _____    _____  _ __| | __
| | | \___ \| |_) | |_ | '__/ _` | '_ ` _ \ / _ \ \ /\ / / _ \| '__| |/ /
| |_| |___) |  _ <|  _|| | | (_| | | | | | |  __/\ V  V / (_) | |  |  <
 \___/|____/|_| \_\_|  |_|  \__,_|_| |_| |_|\___| \_/\_/ \___/|_|  |_|\_

​        Version:    OSRFramework 0.17.2
​        Created by:  Felix Brezo and Yaiza Rubio, (i3visio)



searchfy.py Copyright (C) F. Brezo and Y. Rubio (i3visio) 2014-2017

This program comes with ABSOLUTELY NO WARRANTY. This is free software, and you
are welcome to redistribute it under certain conditions. For additional info,
visit https://www.gnu.org/licenses/agpl-3.0.txt

2017-10-05 11:38:33.545680 Starting search in different platform(s)... Relax!

  Press <Ctrl + C> to stop...

[!] In skype.py, exception caught when checking information in Skype!

2017-10-05 11:38:36.672623 A summary of the results obtained are listed in the following table:

Sheet Name: Profiles recovered (2017-10-5_11h38m).
+---------------------------------+---------------+------------------+
|      i3visio_uri      | i3visio_alias | i3visio_platform |
+=================================+===============+==================+
| http://github.com/dookie2000ca  | dookie2000ca  | Github      |
+---------------------------------+---------------+------------------+
| http://twitter.com/dookie2000ca | dookie2000ca  | Twitter      |
+---------------------------------+---------------+------------------+

2017-10-05 11:38:36.685354 You can find all the information collected in the following files:
  ./profiles.csv

2017-10-05 11:38:36.685581 Finishing execution...

Total time used:  0:00:03.139901
Average seconds/query: 3.139901 seconds

Did something go wrong? Is a platform reporting false positives? Do you need to
integrate a new one and you don't know how to start? Then, you can always place
an issue in the Github project:
  https://github.com/i3visio/osrframework/issues
Note that otherwise, we won't know about it!
```