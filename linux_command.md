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
	--------------------------------------------------------------
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
	
	[root@veena ~]# grep -E '^Listen' /etc/httpd/conf/httpd.conf
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



Cut command:
=============
```
	 The 'cut‘ command is a powerful tool to extract parts of each line from a file.
	 It is based on
	 Byte Position
	 Character Position
	 Fields based on delimiter (by default delimiter is the tab)
	 Cut command syntax:
	 cut [options] <positions(fields) /range of positions(fields)> <input_file>
	 cat file | cut [options] <positions(fields) /range of positions(fields)>
	 Options: -b -c and -f
  Rages:
	2 only second byte/character/filed
	2- second byte/character/filed to last
	-7 first to seven
	3,5 third and fifth

 Cut command for Byte/Character Position:
	 To cut out a section of a line by specifying a byte/character position use the -b/-c option.
	 Syntax:
		cut -b <position’s/range of position’s> file
		cut -c <position’s/range of position’s> file
		Position’s: 3,5,10
		Range of Position’s: 3-7, 6-10
	 Ex: mytext.txt
	 cut -b 2 mytext.txt
	 cut -b 3,7 mytext.txt
	 cut -b 5-9 mytext.txt
	 cut -b 5- mytext.txt
	 cut -b -7, 9 mytext.txt
	 Use --complement to complement the output
	
```

  Cut command for filed Position:
  -------------------------------
  ```
	 To cut out a section of a line by specifying a field position use the -f option.
	 Assume fields are like columns, by default cut command will separates columns based on
	tab(delimiter).
	 If we want to use different filed separator use -d (delimiter).
	 Syntax:
		 cut -f <position’s/range of position’s> file
		 cut -f <position’s/range of position’
		ss> [-d ‘
		:
		’] [--output-delimiter=‘**’] file
		 -d is a delimiter like @ , : / etc….
		 Position’s: 3,5,2
		 Range of Position’s: 3-7, 6-10
	 Ex: mytext.txt
	 cut -f 2 mytext.txt
	 cut -f 3,7 mytext.txt
	 cut -f 5-9 mytext.txt
	 cut -f 5- mytext.txt
	 cut -f -7, 9 --output-delimiter=“ “ mytext.txt
```
Practical
------------
```
 cut -c 4,9 /etc/passwd #display character 4th and 9th 
 cut -c 1 /etc/passwd
 cut -c 4-9  /etc/passwd #print 4-9 character
 cut -c 4-9,12  /etc/passwd
 cut -c -10  /etc/passwd #1 to 10
 cut -c 5-  /etc/passwd  #5th last
 
 filed should be separated with tab otherwise it will not work
 cut -f 1 out.txt #fetch first columns filed 
 cut -f 1,3  out.txt #1st and 3rd filed
 cut -f 1- out.txt #first to last
 cut -f -3 out.txt #first to 3rd 
 
 cut -d ':' -f 1 /etc/passwd  #gives all username 
 cut -d ':' -f 1,4  /etc/passwd  #give 1st and 4th filed
	root:0
	bin:1
	daemon:2
 cut -d ':' -f 1,4 /etc/passwd --output-delimiter=" " 
	root 0
    bin 1
 [root@veena ~]# crepo --show | cut -d ':' -f 1
  Cluster-Manager-1.7-rhel85-x86_64
  HPE-MPI-1.9.1-rhel85-x86_64
  
  [root@veena ~]# cat 1.txt
	abc     def     ghi
	jkl mnp xyz
	
 [root@veena ~]# cat 1.txt  | cut -sf 1
  abc
 
 [root@veena ~]# cat 1.txt  | cut -d ' ' -sf 1
 jkl
 
 [root@veena ~]# httpd -v
 Server version: Apache/2.4.37 (Red Hat Enterprise Linux)
 Server built:   Jul 12 2021 17:39:44
 
  [root@veena ~]# httpd -v | grep version | cut -d '/' -f 2 | cut -d ' ' -f 1
  2.4.37
  
  ```

AWK Command
============

```
awk command:
 The awk command is a powerful method for processing or analyzing text or data files ,
which are organized by lines (rows or records) and columns(fileds).
 we can use awk as a linux command and also as a scripting language like bash shell
scripting.
 Simple awk command syntax:
 awk [options] ‘[selection _criteria] {action }' input-file
 cat input-file | awk [options] ‘[selection _criteria] {action }' input-file
 Awk can take the following options:
-F fs To specify a field separator. (Default separator is tab and space)
-f file To specify a file that contains awk script.
-v var=value To declare a variable.
 Selection criteria: pattern/condition
 Action: It is a logic to perform action on each row/record

awk command:
 Simple awk command syntax:
 awk ' {action }' input-file
 Action: Action is a logic to perform action on each record.
 Example: print $1 print first filed from each line
 Some of the default variables for awk:
 $0  Entire file
 $1  First field from each line/record
 $2  Second field from each line/record
 NR  It will print line or record number
 NF  It will print number of filed from each line/record
```

Practical
----------

```
 [root@veena ~]# httpd -v | grep version |  awk -F '[ /]' '{print $4}'
	2.4.37

  # awk -F '[ /]'  means delimiter as  ' ' or / #similar to  grep -E [AB]
  
 [root@veena ~]# httpd -v |  awk -F '[ /]' ' NR=1 {print $4}'
  2.4.37

 [root@veena ~]# cat 1.txt
 abc     def     ghi
 jkl mnp xyz
	
 [root@veena ~]# awk '{print $1}' 1.txt
 abc
 jkl
 
  Default delimiter for awk is space . but for cut default delimiter/filed separator is tab
  
  to print entire conntent. '{print $0}' or '{print}' both are same.
  [root@veena ~]# awk '{print $0}' 1.txt
	abc     def     ghi
	jkl mnp xyz
	[root@veena ~]# awk '{print}' 1.txt
	abc     def     ghi
	jkl mnp xyz
	
 Print 1st and 2nd column 
 [root@veena ~]# awk '{print $1,$2}' 1.txt
 abc def
 jkl mnp
  
  Reverse the column
  [root@veena ~]# awk '{print $2,$1}' 1.txt
	def abc
	mnp jkl
 
 list the lines in the files
 [root@veena ~]# awk '{print NR }' 1.txt
	1
	2

 [root@veena ~]# awk '{print NR $0 }' 1.txt
	1abc    def     ghi
	2jkl mnp xyz

 [root@veena ~]# awk '{print NR $0 NF }' 1.txt
	1abc    def     ghi3
	2jkl mnp xyz3
 
 it will give last column info 
[root@veena ~]# awk '{print NR $NF }' 1.txt
	1ghi
	2xyz
	
	$NR means 1st record first field , 2nd record 2nd field
 [root@veena ~]# cat 1.txt
	abc     def     ghi
	jkl mnp xyz

 [root@veena ~]# awk '{print $NR }' 1.txt
	abc
	mnp
```

TEE Command
===========
```
 tee command is used to display the output and also to store that output into a file. (It does both the
tasks simultaneously).
 It is useful to create logs for shell scripting.
 Syntax:
 Command | tee outputFile.txt
 Command | tee –a outputFile.txt
```
```
[root@veena ~]# ls -ltrh | tee abc.txt
total 44K
-rw-r--r-- 1 root root 17K Oct 21 19:27 1
-rw-r--r-- 1 root root 17K Oct 21 19:27 veena6leaders.config
-rw-r--r-- 1 root root  21 Oct 22 10:05 1.txt

[root@veena ~]# pwd | tee -a abc.txt
/root

[root@veena ~]# cat abc.txt
total 44K
-rw-r--r-- 1 root root 17K Oct 21 19:27 1
-rw-r--r-- 1 root root 17K Oct 21 19:27 veena6leaders.config
-rw-r--r-- 1 root root  21 Oct 22 10:05 1.txt
/root
```
