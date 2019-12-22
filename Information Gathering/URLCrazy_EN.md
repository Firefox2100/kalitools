<iframe src="https://asciinema.org/a/31882/embed?" id="asciicast-iframe-31882" name="asciicast-iframe-31882" scrolling="no" allowfullscreen="true" style="box-sizing: border-box; max-width: 100%; border: 0px; overflow: hidden; margin: 0px; display: inline-block; width: 686px; float: none; visibility: visible; height: 675px;"></iframe>


## urlcrazy Package Description

Generate and test domain typos and variations to detect and perform typo squatting, URL hijacking, phishing, and corporate espionage.

Features

- Generates 15 types of domain variants
- Knows over 8000 common misspellings
- Supports cosmic ray induced bit flipping
- Multiple keyboard layouts (qwerty, azerty, qwertz, dvorak)
- Checks if a domain variant is valid
- Test if domain variants are in use
- Estimate popularity of a domain variant

Source: http://www.morningstarsecurity.com/research/urlcrazy
[URLCrazy Homepage](http://www.morningstarsecurity.com/research/urlcrazy) | [Kali URLCrazy Repo](https://gitlab.com/kalilinux/packages/urlcrazy.git;a=summary)

- Author: Andrew Horton
- License: Non-commercial

### Tools included in the urlcrazy package

##### urlcrazy – Domain typo generator

```
root@kali:~# urlcrazy -h
URLCrazy version 0.5
by Andrew Horton (urbanadventurer)
http://www.morningstarsecurity.com/research/urlcrazy

Generate and test domain typos and variations to detect and perform typo squatting, URL hijacking,
phishing, and corporate espionage.

Supports the following domain variations:
Character omission, character repeat, adjacent character swap, adjacent character replacement, double
character replacement, adjacent character insertion, missing dot, strip dashes, singular or pluralise,
common misspellings, vowel swaps, homophones, bit flipping (cosmic rays), homoglyphs, wrong top level
domain, and wrong second level domain.

Usage: /usr/bin/urlcrazy [options] domain

Options
 -k, --keyboard=LAYOUT Options are: qwerty, azerty, qwertz, dvorak (default: qwerty)
 -p, --popularity  Check domain popularity with Google
 -r, --no-resolve  Do not resolve DNS
 -i, --show-invalid Show invalid domain names
 -f, --format=TYPE Human readable or CSV (default: human readable)
 -o, --output=FILE Output file
 -h, --help   This help
 -v, --version    Print version information. This version is 0.5
```

### urlcrazy Usage Example

Search for URLs using the dvorak layout ***(-k dvorak)*** and do no resolve hostnames ***(-r)*** for the given domain ***(example.com)***:

```
root@kali:~# urlcrazy -k dvorak -r example.com
URLCrazy Domain Report
Domain   : example.com
Keyboard  : dvorak
At     : 2014-05-13 17:04:01 -0600

# Please wait. 95 hostnames to process

Typo Type        Typo       CC-A  Extn
---------------------------------------------------
Character Omission   eample.com    ?   com
Character Omission   examle.com    ?   com
Character Omission   exampe.com    ?   com
Character Omission   exampl.com    ?   com
Character Omission   example.cm    ?   cm
Character Omission   exaple.com    ?   com
```