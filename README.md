SHELL Scripting
----------------

	veena:~ # cat /etc/shells
	/bin/ash
	/bin/bash
	/bin/csh
	/bin/dash
	/bin/false
	/bin/ksh
	/bin/ksh93
	/bin/mksh
	/bin/pdksh
	/bin/sh
	/bin/tcsh
	/bin/true
	/bin/zsh
	/usr/bin/csh
	/usr/bin/dash
	/usr/bin/ksh
	/usr/bin/ksh93
	/usr/bin/mksh
	/usr/bin/passwd
	/usr/bin/pdksh
	/usr/bin/bash
	/usr/bin/tcsh
	/usr/bin/zsh
	/usr/bin/fish

	Change ownership of Directory 
	chown -R user:user /home/user

**to knoow shell**
-----------------

	/bin/bash

**to change shell**
-----------------
	veena:~ # chsh
	Changing the login shell for root
	Enter the new value, or press ENTER for the default
		Login Shell [/bin/bash]: /bin/bash


shibang line is which shell we are using in our shell script

Redirection operator , STDIN, STDOUT , STDERR
=============================================

	output redirection operator
	> create new file
	>> append the content 

	i/p redirection operator
	>
	cat < demo.txt

	Combining Redirection operator
	  | ->send standard o/p of one cmd to stand i/p of one command

	  veena:~ # ls -ltrh | awk '{print $1}'
	total
	drwx------
	drwxr-xr-x
	drwxr-xr-x
	drwx------

	file descriptor is integer to identify STDIN , STDOUT, STDERR
		0: STDIN
		1: STDOUT
		2: STDERR

	> filename (default to sucess o/p)
	1> filename (sucess o/p)
	1> filename 2>filename (both will store into same file)
	1>filename 2>&1 (sucess/error same file)
	&> filename  (sucess/error same file)

Read file content
==================
	 Read a file content by opening it
	 Using vi/vim/nano editors
	 Read a file content without opening it
	 Using cat, less, more
	 Read a file content with conditions
	 Using more, tail, grep, awk, se

	[root@veena ~]# ll / | awk 'NR>=1 && NR <=5 {print $1}'
	total
	lrwxrwxrwx
	dr-xr-xr-x
	drwxr-xr-x
	drwxr-xr-x

	ll / | sed -n '1,5p'

	head -5 xyz.txt
	tail
	less
	more


***Advanced grep command:***
======================
	 grep command syntax:
	 grep [options] “string/pattern” file/files
	 Basic options: -i -w -v -o -n -c -A -B -C -r -l -h
	 Advanced Options: -f -e and –E
	 -f Takes search string/pattern from a file, one per line
	 -e To search multiple strings/patterns
	 Pattern is a string and it represents more than one string.
	 -E To work with patterns
	 grep -E[options] “pattern” file/files
	Learn how to automate common tasks using bash shell scripting
	Rules to create patterns:
	 xy|pq Matches for xy or pq
	 ^xyz Matches for the lines which are starting with “xyz”
	 xyz$ Matches for the lines which are ending with “xyz”
	 ^$ Matches for the lines which are empty
	 \ To remove the special purpose of any symbol. Ex: \^ \$
	 . Matches any one character
	 \. Matches exactly with .
	 \b Match the empty string at the edge of word
	 ? The preceding character is optional and will be matched, at most, once.
	 * The preceding character will be matched zero or more times
	 + The preceding character will be matched one or more times
	 [xyz] Matches for the lines which are having x or y or z
	 [a-d] is equal to [abcd] Matched for the lines which are having a/b/b/d
	 [a-ds-z] is eqal to [abcdstuvwxyz]
	 ^[abc] Matches for the lines which are starting with a/b/c
	 [^abc] Matches for the lines which are not starting with a/b/c
	 {N} The preceding string matched exactly N times
	 {N,} The preceding string matched N or more times
	 {N,M} The preceding string matched at least N times but not more than M times

	[[:alnum:]] – Alphanumeric characters.
	[[:alpha:]] – Alphabetic characters
	[[:blank:]] – Blank characters: space and tab.
	[[:digit:]] – Digits: ‘0 1 2 3 4 5 6 7 8 9’.
	[[:lower:]] – Lower-case letters: ‘a b c d e f g h i j k l m n o p q r s t u v w x y z’.
	[[:space:]] – Space characters: tab, newline, vertical tab, form feed, carriage return, and space.
	[[:upper:]] – Upper-case letters: ‘A B C D E F G H I J K L M N O P Q R S T U

***examples***
---------------
	grep [options] string/paatern file/files
	grep -irn 'string' file.txt #-i means match both upper/lower case
	grep -w 'string' file.txt  #exact word match
	grep -o 'string' file.txt #exact word print in o/p
	grep -c 'string' file.txt #count how many line having match string
	grep -l 'kafka' /opt/* #print file name content kafka

	grep -E 'service0|service27' veena6leaders.config #multi string grep search
	grep -e service0 -e service27 veena6leaders.config #multi string grep search
	grep 'service0\|service27' veena6leaders.config #multi string grep search
	grep -E "^this" test.txt #print line starting with this
	[root@veena ~]# grep -Er '^Listen' /etc/httpd/conf/httpd.conf
	Listen 80

	grep -E 'this$' test.txt #print the line end with  this 
	grep -E '^$' test.txt #print the empty line
	grep -E '\^' test.txt #print line special symbol
	grep -E '.' test.txt #print  all character
	grep -E 't..s' test.txt #print start t any two char ens s 
	grep -E '\.' test.txt #print line having .
	grep -E 'yf?' test.txt #f may 0 time or one time 
	grep -E 'yf*' test.txt #f may 0 time or more  time 
	grep -E 'yf+' test.txt #f may at least 1 or many time
	grep -E '[tTfy]' test.txt #any of the character match  same as  grep -E 't|T|f|y' test.txt
	grep -E '[a-f]' test.txt or  grep -E 'a|b|c|d|e|f' test.txt
	grep -E '[a-dp-r]' test.txt   grep -E 'a|b|c|d|p|q|r' test.txt  or  grep -E '[abcdpqr]' test.txt
	grep -E '^[xy]' test.txt #print line start with x or yf
	grep -E '[^xy]' test.txt #it will print other than x and y
	grep -E 'xf{4}' test.txt # same as grep -E 'xffff' test.txt 
	grep -E 'xf{3,4}' test.txt #f may be 3 time or 4 time
	grep -E 'xf{3,4}\b' test.txt #f may be 3 time or 4 time and space should be end
	grep -E 'xf{3,}' test.txt #f may be 3 time max any time 
	grep -E '[[:digit:]]' file.txt #display digit 

	***practical***


	ls -ltrh | grep -E '^d' #list of directory
	ls -ltrh | grep -E '^-' #list of file
	grep -E '\b[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\b'  ip.txt




