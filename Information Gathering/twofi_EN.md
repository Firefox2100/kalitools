## twofi Package Description

When attempting to crack passwords custom word lists are very useful additions to standard dictionaries. An interesting idea originally released on the “7 Habits of Highly Effective Hackers” blog was to use Twitter to help generate those lists based on searches for keywords related to the list that is being cracked. This idea has been expanded into twofi which will take multiple search terms and return a word list sorted by most common first.

Source: https://digi.ninja/projects/twofi.php
[twofi Homepage](https://digi.ninja/projects/twofi.php) | [Kali twofi Repo](https://gitlab.com/kalilinux/packages/twofi.git;a=summary)

- Author: Robin Wood
- License: Creative Commons Attribution-Share Alike 2.0



### Tools included in the twofi package

##### twofi – Twitter words of interest

```
root@kali:~# twofi -h
twoif 2.0-beta Robin Wood (robin@digininja.org) (www.digininja.org)
twoif - Twitter Words of Interest

Usage: twoif [OPTIONS]
  --help, -h: show help
  --config <file>: config file, default is twofi.yml
  --count, -c: include the count with the words
  --min_word_length, -m: minimum word length
  --term_file, -T <file>: a file containing a list of terms
  --terms, -t: comma separated search terms
    quote words containing spaces, no space after commas
  --user_file, -U <file>: a file containing a list of users
  --users, -u: comma separated usernames
    quote words containing spaces, no space after commas
  --verbose, -v: verbose
```

### Twofi Usage Example



<iframe src="https://asciinema.org/a/32180/embed?" id="asciicast-iframe-32180" name="asciicast-iframe-32180" scrolling="no" allowfullscreen="true" style="box-sizing: border-box; max-width: 100%; border: 0px; overflow: hidden; margin: 0px; display: inline-block; width: 686px; float: none; visibility: visible; height: 659px;"></iframe>