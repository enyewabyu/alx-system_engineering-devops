# 0x02. Shell, I/O Redirections and filters

## About Bash projects
Unless stated, all your projects will be auto-corrected with Ubuntu 20.04 LTS.

## Resources
### Read or watch:

* Shell, I/O Redirection
* Special Characters
### man or help:

* echo
* cat
* head
* tail
* find
* wc
* sort
* uniq
* grep
* tr
* rev
* cut
* passwd (5) (i.e. man 5 passwd)
## Learning Objectives
At the end of this project, you are expected to be able to explain to anyone, without the help of Google:

### Shell, I/O Redirection
* What do the commands head, tail, find, wc, sort, uniq, grep, tr do
* How to redirect standard output to a file
* How to get standard input from a file instead of the keyboard
* How to send the output from one program to the input of another program
* How to combine commands and filters with redirections
### Special Characters
* What are special characters
* Understand what do the white spaces, single quotes, double quotes, backslash, comment, pipe, command separator, tilde and how and when to use them
### Other Man Pages
* How to display a line of text
* How to concatenate files and print on the standard output
* How to reverse a string
* How to remove sections from each line of files
* What is the /etc/passwd file and what is its format
* What is the /etc/shadow file and what is its format
### Copyright - Plagiarism
* You are tasked to come up with solutions for the tasks below yourself to meet with the above learning objectives.
* You will not be able to meet the objectives of this or any following project by copying and pasting someone else’s work.
* You are not allowed to publish any content of this project.
* Any form of plagiarism is strictly forbidden and will result in removal from the program.
### Requirements
### General
* Allowed editors: vi, vim, emacs
* All your scripts will be tested on Ubuntu 20.04 LTS
* All your scripts should be exactly two lines long ($ wc -l file should print 2)
* All your files should end with a new line (why?)
* The first line of all your files should be exactly #!/bin/bash
* A README.md file, at the root of the folder of the project, describing what each script is doing
* You are not allowed to use backticks, &&, || or ;
* All your files must be executable
* You are not allowed to use sed or awk
### More Info
Read your /etc/passwd and /etc/shadow files.

Note: You do not have to learn about fmt, pr, du, gzip, tar, lpr, sed and awk yet.

  ## Quiz questions
``` Great! You've completed the quiz successfully! Keep going! (Show quiz) ```
## Question #0
Which symbol should I use to redirect the standard output to a file (overwrite the file)?

[] &

[x] >

[] 2>

[] >>

## Question #1
Which symbol should I use to redirect the error output to the standard output?


1>&2


2>


2>&1

## Question #2
Which symbol should I use to redirect the standard output to a file (appending to the file)?


&


>


2>


>>

## Question #3
Which command should I use to display the last 11 lines of a file?


tail 11 my_file


tail -n 11 my_file


head 11 my_file


head -n 11 my_file

## Question #4
Which command should I use to display the entire file content?


tail


head


cat


grep

## Question #5
Which symbol should I use to escape a special character?


#


$


!


\

## Question #6
Which symbol should I use to start a comment?


#


//


!


&
## Tasks

## 0. Hello World
 Write a script that prints “Hello, World”, followed by a new line to the standard output.
 
``` 
julien@ubuntu:/tmp/h$ ./0-hello_world 
Hello, World
julien@ubuntu:/tmp/h$ ./0-hello_world | cat -e
Hello, World$
julien@ubuntu:/tmp/h$ 
### Repo:

GitHub repository: alx-system_engineering-devops
Directory: 0x02-shell_redirections
File: 0-hello_world
```
   
## 1. Confused smiley

Write a script that displays a confused smiley "(Ôo)'. 

``` 
julien@ubuntu:/tmp/h$ ./1-confused_smiley 
"(Ôo)'
julien@ubuntu:/tmp/h$
```
### Repo:

* GitHub repository: alx-system_engineering-devops
* Directory: 0x02-shell_redirections
* File: 1-confused_smiley
   
## 2. Let's display a file
 Display the content of the /etc/passwd file.

```
Example:

$ ./2-hellofile
##
# User Database
#
# Note that this file is consulted directly only when the system is running
# in single-user mode. At other times this information is provided by
# Open Directory.
#
# See the opendirectoryd(8) man page for additional information about
# Open Directory.
##
nobody:*:-2:-2:Unprivileged User:/var/empty:/usr/bin/false
root:*:0:0:System Administrator:/var/root:/bin/sh
daemon:*:1:1:System Services:/var/root:/usr/bin/false
_uucp:*:4:4:Unix to Unix Copy Protocol:/var/spool/uucp:/usr/sbin/uucico
_taskgated:*:13:13:Task Gate Daemon:/var/empty:/usr/bin/false
_networkd:*:24:24:Network Services:/var/networkd:/usr/bin/false
_installassistant:*:25:25:Install Assistant:/var/empty:/usr/bin/false
_lp:*:26:26:Printing Services:/var/spool/cups:/usr/bin/false
_postfix:*:27:27:Postfix Mail Server:/var/spool/postfix:/usr/bin/false
_scsd:*:31:31:Service Configuration Service:/var/empty:/usr/bin/false
_ces:*:32:32:Certificate Enrollment Service:/var/empty:/usr/bin/false
_mcxalr:*:54:54:MCX AppLaunch:/var/empty:/usr/bin/false
_krbfast:*:246:-2:Kerberos FAST Account:/var/empty:/usr/bin/false
$
```
### Repo:

* GitHub repository: alx-system_engineering-devops
* Directory: 0x02-shell_redirections
* File: 2-hellofile
   
## 3. What about 2?
 Display the content of /etc/passwd and /etc/hosts 
````
Example:

$ ./3-twofiles
##
# User Database
#
# Note that this file is consulted directly only when the system is running
# in single-user mode. At other times this information is provided by
# Open Directory.
#
# See the opendirectoryd(8) man page for additional information about
# Open Directory.
##
nobody:*:-2:-2:Unprivileged User:/var/empty:/usr/bin/false
root:*:0:0:System Administrator:/var/root:/bin/sh
daemon:*:1:1:System Services:/var/root:/usr/bin/false
##
# Host Database
#
# localhost is used to configure the loopback interface
# when the system is booting. Do not change this entry.
##
127.0.0.1   localhost
255.255.255.255 broadcasthost
::1 localhost
$
````
### Repo:

* GitHub repository: alx-system_engineering-devops
* Directory: 0x02-shell_redirections
* File: 3-twofiles
   
## 4. Last lines of a file
Display the last 10 lines of /etc/passwd

```` Example:

$ ./4-lastlines
_assetcache:*:235:235:Asset Cache Service:/var/empty:/usr/bin/false
_coremediaiod:*:236:236:Core Media IO Daemon:/var/empty:/usr/bin/false
_launchservicesd:*:239:239:_launchservicesd:/var/empty:/usr/bin/false
_iconservices:*:240:240:IconServices:/var/empty:/usr/bin/false
_distnote:*:241:241:DistNote:/var/empty:/usr/bin/false
_nsurlsessiond:*:242:242:NSURLSession Daemon:/var/db/nsurlsessiond:/usr/bin/false
_nsurlstoraged:*:243:243:NSURLStorage Daemon:/var/empty:/usr/bin/false
_displaypolicyd:*:244:244:Display Policy Daemon:/var/empty:/usr/bin/false
_astris:*:245:245:Astris Services:/var/db/astris:/usr/bin/false
_krbfast:*:246:-2:Kerberos FAST Account:/var/empty:/usr/bin/false

Tips: “Thinks of it as a cat, what is at the end of it?”
````
### Repo:

* GitHub repository: alx-system_engineering-devops
* Directory: 0x02-shell_redirections
* File: 4-lastlines
   
## 5. I'd prefer the first ones actually

Display the first 10 lines of /etc/passwd
````
Example:

$ ./5-firstlines
##
# User Database
#
# Note that this file is consulted directly only when the system is running
# in single-user mode. At other times this information is provided by
# Open Directory.
#
# See the opendirectoryd(8) man page for additional information about
# Open Directory.
##
$
````
### Repo:

* GitHub repository: alx-system_engineering-devops
* Directory: 0x02-shell_redirections
* File: 5-firstlines
   
## 6. Line #2

Write a script that displays the third line of the file iacta.
````
The file iacta will be in the working directory

You’re not allowed to use sed
julien@ubuntu:/tmp/h$ cat iacta 
Alea iacta est

Alea iacta est ("The die is cast") is a Latin phrase attributed by Suetonius
(as iacta alea est) to Julius Caesar on January 10, 49 BC
as he led his army across the Rubicon river in Northern Italy. With this step,
he entered Italy at the head of his army in defiance of the Senate and began
his long civil war against Pompey and the Optimates. The phrase has been
adopted in Italian (Il dado è tratto), Romanian (Zarurile au fost aruncate),
Spanish (La suerte está echada), French (Les dés sont jetés), Portuguese (A
sorte está lançada), Dutch (De teerling is geworpen),
German (Der Würfel ist gefallen), Hungarian (A kocka el van vetve) and many other languages to
indicate that events have passed a point of no return.

Read more: https://en.wikipedia.org/wiki/Alea_iacta_est
julien@ubuntu:/tmp/h$ ./6-third_line 
Alea iacta est ("The die is cast") is a Latin phrase attributed by Suetonius
julien@ubuntu:/tmp/h$ 
Note: The output will differ, depending on the content of the file iacta.
````
### Repo:

* GitHub repository: alx-system_engineering-devops
* Directory: 0x02-shell_redirections
* File: 6-third_line
   
## 7. It is a good file that cuts iron without making a noise

Write a shell script that creates a file named exactly \*\\'"Best School"\'\\*$\?\*\*\*\*\*:) containing the text Best School ending by a new line.
````
julien@ubuntu:~/shell$ ls && ./7-file && ls -l && cat -e \\*
0-mac_and_cheese 7-file 7-file~ Makefile
total 20
-rwxrw-r-- 1 julien julien 79 Jan 20 06:24 0-mac_and_cheese
-rwxrw-r-- 1 julien julien 90 Jan 20 06:40 7-file
-rwxrw-r-- 1 julien julien 69 Jan 20 06:37 7-file~
-rw-rw-r-- 1 julien julien 14 Jan 20 06:38 Makefile
-rw-rw-r-- 1 julien julien 17 Jan 20 06:40 '\*\\'"Best School"\'\\*$\?\*\*\*\*\*:)'
Best School$
julien@ubuntu:~/shell$
````
### Repo:

* GitHub repository: alx-system_engineering-devops
* Directory: 0x02-shell_redirections
* File: 7-file
   
## 8. Save current state of directory

Write a script that writes into the file ls_cwd_content the result of the command ls -la. If the file ls_cwd_content already exists, it should be overwritten. If the file ls_cwd_content does not exist, create it.
````
julien@ubuntu:/tmp/h$ ls -la
total 20
drwxrwxr-x  2 julien julien 4096 Sep 20 18:18 .
drwxrwxrwt 13 root   root   4096 Sep 20 18:18 ..
-rwxrw-r--  1 julien julien   36 Sep 20 18:18 8-cwd_state
-rw-rw-r--  1 betty  julien   23 Sep 20 14:25 hello
-rw-rw-r--  1 julien julien  926 Sep 20 17:52 iacta
julien@ubuntu:/tmp/h$ ./8-cwd_state 
julien@ubuntu:/tmp/h$ ls -la
total 24
drwxrwxr-x  2 julien julien 4096 Sep 20 18:18 .
drwxrwxrwt 13 root   root   4096 Sep 20 18:18 ..
-rwxrw-r--  1 julien julien   36 Sep 20 18:18 8-cwd_state
-rw-rw-r--  1 betty  julien   23 Sep 20 14:25 hello
-rw-rw-r--  1 julien julien  926 Sep 20 17:52 iacta
-rw-rw-r--  1 julien julien  329 Sep 20 18:18 ls_cwd_content
julien@ubuntu:/tmp/h$ cat ls_cwd_content 
total 20
drwxrwxr-x  2 julien julien 4096 Sep 20 18:18 .
drwxrwxrwt 13 root   root   4096 Sep 20 18:18 ..
-rwxrw-r--  1 julien julien   36 Sep 20 18:18 8-cwd_state
-rw-rw-r--  1 betty  julien   23 Sep 20 14:25 hello
-rw-rw-r--  1 julien julien  926 Sep 20 17:52 iacta
-rw-rw-r--  1 julien julien    0 Sep 20 18:18 ls_cwd_content
julien@ubuntu:/tmp/h$ 
````
### Repo:

* GitHub repository: alx-system_engineering-devops
* Directory: 0x02-shell_redirections
* File: 8-cwd_state
   
## 9. Duplicate last line

Write a script that duplicates the last line of the file iacta
````
The file iacta will be in the working directory
julien@ubuntu:/tmp/h$ cat iacta 
Alea iacta est

Alea iacta est ("The die is cast") is a Latin phrase attributed by Suetonius
(as iacta alea est) to Julius Caesar on January 10, 49 BC
as he led his army across the Rubicon river in Northern Italy. With this step,
he entered Italy at the head of his army in defiance of the Senate and began
his long civil war against Pompey and the Optimates. The phrase has been
adopted in Italian (Il dado è tratto), Romanian (Zarurile au fost aruncate),
Spanish (La suerte está echada), French (Les dés sont jetés), Portuguese (A
sorte está lançada), Dutch (De teerling is geworpen),
German (Der Würfel ist gefallen), Hungarian (A kocka el van vetve) and many other languages to
indicate that events have passed a point of no return.

Read more: https://en.wikipedia.org/wiki/Alea_iacta_est
julien@ubuntu:/tmp/h$ ./9-duplicate_last_line 
julien@ubuntu:/tmp/h$ cat iacta 
Alea iacta est

Alea iacta est ("The die is cast") is a Latin phrase attributed by Suetonius
(as iacta alea est) to Julius Caesar on January 10, 49 BC
as he led his army across the Rubicon river in Northern Italy. With this step,
he entered Italy at the head of his army in defiance of the Senate and began
his long civil war against Pompey and the Optimates. The phrase has been
adopted in Italian (Il dado è tratto), Romanian (Zarurile au fost aruncate),
Spanish (La suerte está echada), French (Les dés sont jetés), Portuguese (A
sorte está lançada), Dutch (De teerling is geworpen),
German (Der Würfel ist gefallen), Hungarian (A kocka el van vetve) and many other languages to
indicate that events have passed a point of no return.

Read more: https://en.wikipedia.org/wiki/Alea_iacta_est
Read more: https://en.wikipedia.org/wiki/Alea_iacta_est
julien@ubuntu:/tmp/h$ 
````
### Repo:

* GitHub repository: alx-system_engineering-devops
* Directory: 0x02-shell_redirections
* File: 9-duplicate_last_line
   
## 10. No more javascript

Write a script that deletes all the regular files (not the directories) with a .js extension that are present in the current directory and all its subfolders.
````
julien@ubuntu:/tmp/h$ ls -lR
.:
total 24
-rwxrw-r-- 1 julien julien   49 Sep 20 18:29 10-no_more_js
drwxrwxr-x 2 julien julien 4096 Sep 20 18:23 dir1
drwxrwxr-x 2 julien julien 4096 Sep 20 18:24 dir.js
-rw-rw-r-- 1 betty  julien   23 Sep 20 14:25 hello
-rw-rw-r-- 1 julien julien  982 Sep 20 18:21 iacta
-rw-rw-r-- 1 julien julien  329 Sep 20 18:18 ls_cwd_content
-rw-rw-r-- 1 julien julien    0 Sep 20 18:23 main.js

./dir1:
total 0
-rw-rw-r-- 1 julien julien 0 Sep 20 18:23 code.js

./dir.js:
total 0
julien@ubuntu:/tmp/h$ ./10-no_more_js 
julien@ubuntu:/tmp/h$ ls -lR
.:
total 24
-rwxrw-r-- 1 julien julien   49 Sep 20 18:29 10-no_more_js
drwxrwxr-x 2 julien julien 4096 Sep 20 18:29 dir1
drwxrwxr-x 2 julien julien 4096 Sep 20 18:24 dir.js
-rw-rw-r-- 1 betty  julien   23 Sep 20 14:25 hello
-rw-rw-r-- 1 julien julien  982 Sep 20 18:21 iacta
-rw-rw-r-- 1 julien julien  329 Sep 20 18:18 ls_cwd_content

./dir1:
total 0

./dir.js:
total 0
julien@ubuntu:/tmp/h$ 
````
### Repo:

* GitHub repository: alx-system_engineering-devops
* Directory: 0x02-shell_redirections
* File: 10-no_more_js
   
## 11. Don't just count your directories, make your directories count

Write a script that counts the number of directories and sub-directories in the current directory.
````
The current and parent directories should not be taken into account
Hidden directories should be counted
julien@production-503e7013:~/shell/fun_with_the_shell$ ls -lRa
.:
total 32
drwxrwxr-x 3 julien julien 4096 Jan 20 03:53 .
drwxrwxr-x 3 julien julien 4096 Jan 20 02:58 ..
-rwxr--r-- 1 julien julien 43 Jan 20 02:59 0-commas
-rwxr--r-- 1 julien julien 47 Jan 20 02:50 1-empty_casks
-rwxrw-r-- 1 julien julien 68 Jan 20 03:35 2-gifs
-rwxrw-r-- 1 julien julien 47 Jan 20 03:53 3-directories
-rw-rw-r-- 1 julien julien 14 Jan 20 03:35 Makefile
drwxrwxr-x 4 julien julien 4096 Jan 20 03:42 test_dir

./test_dir:
total 16
drwxrwxr-x 4 julien julien 4096 Jan 20 03:42 .
drwxrwxr-x 3 julien julien 4096 Jan 20 03:53 ..
-rw-rw-r-- 1 julien julien 0 Jan 20 03:40 .horrible_selfie.gif
-rw-rw-r-- 1 julien julien 0 Jan 20 03:23 README.md
-rw-rw-r-- 1 julien julien 0 Jan 20 03:17 docker.gif
-rw-rw-r-- 1 julien julien 0 Jan 20 03:17 file.sh
drwxrwxr-x 2 julien julien 4096 Jan 20 03:23 photos
drwxrwxr-x 2 julien julien 4096 Jan 20 03:23 rep.gif

./test_dir/photos:
total 8
drwxrwxr-x 2 julien julien 4096 Jan 20 03:23 .
drwxrwxr-x 4 julien julien 4096 Jan 20 03:42 ..
-rw-rw-r-- 1 julien julien 0 Jan 20 03:23 cat.gif
-rw-rw-r-- 1 julien julien 0 Jan 20 03:22 index.html
-rw-rw-r-- 1 julien julien 0 Jan 20 03:23 main.gif
-rw-rw-r-- 1 julien julien 0 Jan 20 03:23 rudy_rigot.gif

./test_dir/rep.gif:
total 8
drwxrwxr-x 2 julien julien 4096 Jan 20 03:23 .
drwxrwxr-x 4 julien julien 4096 Jan 20 03:42 ..
julien@production-503e7013:~/shell/fun_with_the_shell$ ./11-directories
3
julien@production-503e7013:~/shell/fun_with_the_shell$
````
### Repo:

* GitHub repository: alx-system_engineering-devops
* Directory: 0x02-shell_redirections
* File: 11-directories
   
## 12. What’s new

Create a script that displays the 10 newest files in the current directory.

Requirements:

* One file per line
* Sorted from the newest to the oldest

````

alex@ubuntu:/tmp$ ls -l
total 7
-rwxr-xr-x 1 501 dialout  32 Sep 27 23:51 0-hello_world
-rwxr-xr-x 1 501 dialout  46 Sep 28 11:09 10-no_more_js
-rwxr-xr-x 1 501 dialout  43 Sep 28 11:19 11-directories
-rwxr-xr-x 1 501 dialout  30 Sep 29 13:43 12-newest_files
-rwxr-xr-x 1 501 dialout  28 Sep 27 23:54 1-confused_smiley
-rwxr-xr-x 1 501 dialout  28 Sep 27 23:58 2-hellofile
-rwxr-xr-x 1 501 dialout  39 Sep 27 23:58 3-twofiles
-rwxr-xr-x 1 501 dialout  33 Sep 27 23:59 4-lastlines
-rwxr-xr-x 1 501 dialout  33 Sep 28 00:00 5-firstlines
-rwxr-xr-x 1 501 dialout  28 Sep 28 00:25 6-third_line
-rwxr-xr-x 1 501 dialout 110 Sep 28 00:34 7-file
-rwxr-xr-x 1 501 dialout  36 Sep 28 00:34 8-cwd_state
-rwxr-xr-x 1 501 dialout  35 Sep 28 00:35 9-duplicate_last_line
-rw-r--r-- 1 501 dialout  19 Sep 27 23:51 README.md
alex@ubuntu:/tmp$ ./12-newest_files 
12-newest_files
11-directories
10-no_more_js
9-duplicate_last_line
7-file
8-cwd_state
6-third_line
5-firstlines
4-lastlines
3-twofiles
alex@ubuntu:/tmp$
````
### Repo:

* GitHub repository: alx-system_engineering-devops
* Directory: 0x02-shell_redirections
* File: 12-newest_files
   
## 13. Being unique is better than being perfect

Create a script that takes a list of words as input and prints only words that appear exactly once.

* Input format: One line, one word
* Output format: One line, one word
* Words should be sorted

````
julien@ubuntu:/tmp/0x02$ cat list 
C#
C
Javascript
Perl
PHP
PHP
ASP
R
Go
C#
C++
R
Perl
Javascript
Javascript
Python
Javascript
Javascript
Javascript
Java
Java
Python
Javascript
Javascript
Javascript
ASP
julien@ubuntu:/tmp/0x02$ cat list | ./13-unique 
C
C++
Go
julien@ubuntu:/tmp/0x02$ 
````
### Repo:

* GitHub repository: alx-system_engineering-devops
* Directory: 0x02-shell_redirections
* File: 13-unique
   
## 14. It must be in that file

Display lines containing the pattern “root” from the file /etc/passwd
````
$ ./14-findthatword
root:*:0:0:System Administrator:/var/root:/bin/sh
daemon:*:1:1:System Services:/var/root:/usr/bin/false
_cvmsroot:*:212:212:CVMS Root:/var/empty:/usr/bin/false
$

````
### Repo:

* GitHub repository: alx-system_engineering-devops
* Directory: 0x02-shell_redirections
* File: 14-findthatword
   
## 15. Count that word

Display the number of lines that contain the pattern “bin” in the file /etc/passwd
````
$ ./15-countthatword
81
$ 
````
### Repo:

* GitHub repository: alx-system_engineering-devops
* Directory: 0x02-shell_redirections
* File: 15-countthatword
   
## 16. What's next?

Display lines containing the pattern “root” and 3 lines after them in the file /etc/passwd.
````

$ ./16-whatsnext
root:*:0:0:System Administrator:/var/root:/bin/sh
daemon:*:1:1:System Services:/var/root:/usr/bin/false
_uucp:*:4:4:Unix to Unix Copy Protocol:/var/spool/uucp:/usr/sbin/uucico
_taskgated:*:13:13:Task Gate Daemon:/var/empty:/usr/bin/false
_networkd:*:24:24:Network Services:/var/networkd:/usr/bin/false
--
_cvmsroot:*:212:212:CVMS Root:/var/empty:/usr/bin/false
_usbmuxd:*:213:213:iPhone OS Device Helper:/var/db/lockdown:/usr/bin/false
_dovecot:*:214:6:Dovecot Administrator:/var/empty:/usr/bin/false
_dpaudio:*:215:215:DP Audio:/var/empty:/usr/bin/false
$
````
### Repo:

* GitHub repository: alx-system_engineering-devops
* Directory: 0x02-shell_redirections
* File: 16-whatsnext
   
## 17. I hate bins

Display all the lines in the file /etc/passwd that do not contain the pattern “bin”.
````
$ ./17-hidethisword
##
# User Database
#
# Note that this file is consulted directly only when the system is running
# in single-user mode. At other times this information is provided by
# Open Directory.
#
# See the opendirectoryd(8) man page for additional information about
# Open Directory.
##
$
````
### Repo:

* GitHub repository: alx-system_engineering-devops
* Directory: 0x02-shell_redirections
* File: 17-hidethisword
   
### 18. Letters only please

Display all lines of the file /etc/ssh/sshd_config starting with a letter.
````
include capital letters as well
$ ./18-letteronly
SyslogFacility AUTHPRIV
AuthorizedKeysFile  .ssh/authorized_keys
UsePrivilegeSeparation sandbox # Default for new installations.
AcceptEnv LANG LC_*
Subsystem   sftp    /usr/libexec/sftp-server
$
````
### Repo:

* GitHub repository: alx-system_engineering-devops
* Directory: 0x02-shell_redirections
* File: 18-letteronly
   
## 19. A to Z

Replace all characters A and c from input to Z and e respectively.
````
julien@ubuntu:/tmp/0x02$ echo 'Replace all characters `A` and `c` from input to `Z` and `e`.' | ./19-AZ 
Replaee all eharaeters `Z` and `e` from input to `Z` and `e`.
julien@ubuntu:/tmp/0x02$ 
````
### Repo:

* GitHub repository: alx-system_engineering-devops
* Directory: 0x02-shell_redirections
* File: 19-AZ
   
## 20. Without C, you would live in hiago

Create a script that removes all letters c and C from input.
````
julien@ubuntu:/tmp/0x02$ echo Chicago | ./20-hiago 
hiago
julien@ubuntu:/tmp/0x02$ 
````
### Repo:

* GitHub repository: alx-system_engineering-devops
* Directory: 0x02-shell_redirections
* File: 20-hiago
   
## 21. esreveR

Write a script that reverse its input.
````
julien@ubuntu:/tmp/0x02$ echo "Reverse" | ./21-reverse 
esreveR
julien@ubuntu:/tmp/0x02$ 
````
### Repo:

* GitHub repository: alx-system_engineering-devops
* Directory: 0x02-shell_redirections
* File: 21-reverse
   
## 22. DJ Cut Killer

Write a script that displays all users and their home directories, sorted by users.

* Based on the the /etc/passwd file
````
julien@ubuntu:/tmp/0x02$ cat /etc/passwd
root:x:0:0:root:/root:/bin/bash
daemon:x:1:1:daemon:/usr/sbin:/usr/sbin/nologin
bin:x:2:2:bin:/bin:/usr/sbin/nologin
sys:x:3:3:sys:/dev:/usr/sbin/nologin
sync:x:4:65534:sync:/bin:/bin/sync
games:x:5:60:games:/usr/games:/usr/sbin/nologin
man:x:6:12:man:/var/cache/man:/usr/sbin/nologin
lp:x:7:7:lp:/var/spool/lpd:/usr/sbin/nologin
mail:x:8:8:mail:/var/mail:/usr/sbin/nologin
news:x:9:9:news:/var/spool/news:/usr/sbin/nologin
uucp:x:10:10:uucp:/var/spool/uucp:/usr/sbin/nologin
proxy:x:13:13:proxy:/bin:/usr/sbin/nologin
www-data:x:33:33:www-data:/var/www:/usr/sbin/nologin
backup:x:34:34:backup:/var/backups:/usr/sbin/nologin
list:x:38:38:Mailing List Manager:/var/list:/usr/sbin/nologin
irc:x:39:39:ircd:/var/run/ircd:/usr/sbin/nologin
gnats:x:41:41:Gnats Bug-Reporting System (admin):/var/lib/gnats:/usr/sbin/nologin
nobody:x:65534:65534:nobody:/nonexistent:/usr/sbin/nologin
systemd-timesync:x:100:102:systemd Time Synchronization,,,:/run/systemd:/bin/false
systemd-network:x:101:103:systemd Network Management,,,:/run/systemd/netif:/bin/false
systemd-resolve:x:102:104:systemd Resolver,,,:/run/systemd/resolve:/bin/false
systemd-bus-proxy:x:103:105:systemd Bus Proxy,,,:/run/systemd:/bin/false
syslog:x:104:108::/home/syslog:/bin/false
_apt:x:105:65534::/nonexistent:/bin/false
messagebus:x:106:110::/var/run/dbus:/bin/false
uuidd:x:107:111::/run/uuidd:/bin/false
lightdm:x:108:114:Light Display Manager:/var/lib/lightdm:/bin/false
whoopsie:x:109:116::/nonexistent:/bin/false
avahi-autoipd:x:110:119:Avahi autoip daemon,,,:/var/lib/avahi-autoipd:/bin/false
avahi:x:111:120:Avahi mDNS daemon,,,:/var/run/avahi-daemon:/bin/false
dnsmasq:x:112:65534:dnsmasq,,,:/var/lib/misc:/bin/false
colord:x:113:123:colord colour management daemon,,,:/var/lib/colord:/bin/false
speech-dispatcher:x:114:29:Speech Dispatcher,,,:/var/run/speech-dispatcher:/bin/false
hplip:x:115:7:HPLIP system user,,,:/var/run/hplip:/bin/false
kernoops:x:116:65534:Kernel Oops Tracking Daemon,,,:/:/bin/false
pulse:x:117:124:PulseAudio daemon,,,:/var/run/pulse:/bin/false
rtkit:x:118:126:RealtimeKit,,,:/proc:/bin/false
saned:x:119:127::/var/lib/saned:/bin/false
usbmux:x:120:46:usbmux daemon,,,:/var/lib/usbmux:/bin/false
julien:x:1000:1000:Julien Barbier,,,:/home/julien:/bin/bash
guillaume:x:1001:1001:,,,:/home/guillaume:/bin/bash
betty:x:1002:1002::/home/betty:
julien@ubuntu:/tmp/0x02$
julien@ubuntu:/tmp/0x02$ ./22-users_and_homes 
_apt:/nonexistent
avahi-autoipd:/var/lib/avahi-autoipd
avahi:/var/run/avahi-daemon
backup:/var/backups
betty:/home/betty
bin:/bin
colord:/var/lib/colord
daemon:/usr/sbin
dnsmasq:/var/lib/misc
games:/usr/games
gnats:/var/lib/gnats
guillaume:/home/guillaume
hplip:/var/run/hplip
irc:/var/run/ircd
julien:/home/julien
kernoops:/
lightdm:/var/lib/lightdm
list:/var/list
lp:/var/spool/lpd
mail:/var/mail
man:/var/cache/man
messagebus:/var/run/dbus
news:/var/spool/news
nobody:/nonexistent
proxy:/bin
pulse:/var/run/pulse
root:/root
rtkit:/proc
saned:/var/lib/saned
speech-dispatcher:/var/run/speech-dispatcher
sync:/bin
sys:/dev
syslog:/home/syslog
systemd-bus-proxy:/run/systemd
systemd-network:/run/systemd/netif
systemd-resolve:/run/systemd/resolve
systemd-timesync:/run/systemd
usbmux:/var/lib/usbmux
uucp:/var/spool/uucp
uuidd:/run/uuidd
whoopsie:/nonexistent
www-data:/var/www
julien@ubuntu:/tmp/0x02$ 
````
### Repo:

* GitHub repository: alx-system_engineering-devops
* Directory: 0x02-shell_redirections
* File: 22-users_and_homes
   
## 23. Empty casks make the most noise

Write a command that finds all empty files and directories in the current directory and all sub-directories.

* Only the names of the files and directories should be displayed (not the entire path)
* Hidden files should be listed
* One file name per line
* The listing should end with a new line
* You are not allowed to use basename, grep, egrep, fgrep or rgrep
````
ubuntu@ip-172-31-63-244:~/0x02-shell_redirections$ ls -laR
.:
total 64
drwxrwxr-x 5 ubuntu ubuntu 4096 Oct  7 00:48 .
drwxrwxr-x 7 ubuntu ubuntu 4096 Sep 29 21:36 ..
-rwxrwxr-x 1 ubuntu ubuntu   56 Feb  8  2016 0-commas
drwxrwxr-x 2 ubuntu ubuntu 4096 Feb  8  2016 0-commas-checks
-rwxrwxr-x 1 ubuntu ubuntu   48 Feb  8  2016 1-empty_casks
-rwxrwxr-x 1 ubuntu ubuntu   68 Feb  8  2016 2-gifs
-rwxrwxr-x 1 ubuntu ubuntu   47 Feb  8  2016 3-directories
-rwxrwxr-x 1 ubuntu ubuntu   41 Feb  8  2016 4-zeros
-rwxrwxr-x 1 ubuntu ubuntu   43 Feb  8  2016 5-rot13
-rwxrwxr-x 1 ubuntu ubuntu   25 Feb  8  2016 6-odd
-rwxrwxr-x 1 ubuntu ubuntu   73 Feb  8  2016 7-sort_rot13
-rw-rw-r-- 1 ubuntu ubuntu    0 Oct  7 00:46 ........gif
-rw-rw-r-- 1 ubuntu ubuntu    0 Oct  7 00:47 ..hello.gif
drwxrwxr-x 2 ubuntu ubuntu 4096 Oct  7 00:41 javascript
-rw-rw-r-- 1 ubuntu ubuntu    0 Oct  7 00:48 Kris_is_awesome :)
-rw-rw-r-- 1 ubuntu ubuntu   14 Feb  8  2016 Makefile
-rw-rw-r-- 1 ubuntu ubuntu   69 Feb  8  2016 quote
-rw-rw-r-- 1 ubuntu ubuntu    0 Oct  7 00:24 Rona_napping.gif
-rw-rw-r-- 1 ubuntu ubuntu    0 Oct  6 23:59 root.gif
-rw-rw-r-- 1 ubuntu ubuntu    0 Mar 24  2016 ..something
drwxrwxr-x 3 ubuntu ubuntu 4096 Feb  8  2016 test_dir
-rwxrwxr-x 1 ubuntu ubuntu   54 Feb  8  2016 test.var

./0-commas-checks:
total 16
drwxrwxr-x 2 ubuntu ubuntu 4096 Feb  8  2016 .
drwxrwxr-x 5 ubuntu ubuntu 4096 Oct  7 00:48 ..
-rw-rw-r-- 1 ubuntu ubuntu 1361 Feb  8  2016 28-check.php
-rw-rw-r-- 1 ubuntu ubuntu  481 Feb  8  2016 28-check.php~

./javascript:
total 8
drwxrwxr-x 2 ubuntu ubuntu 4096 Oct  7 00:41 .
drwxrwxr-x 5 ubuntu ubuntu 4096 Oct  7 00:48 ..

./test_dir:
total 12
drwxrwxr-x 3 ubuntu ubuntu 4096 Feb  8  2016 .
drwxrwxr-x 5 ubuntu ubuntu 4096 Oct  7 00:48 ..
-rw-rw-r-- 1 ubuntu ubuntu    0 Feb  8  2016 docker.gif
-rw-rw-r-- 1 ubuntu ubuntu    0 Feb  8  2016 file.sh
-rw-rw-r-- 1 ubuntu ubuntu    0 Feb  8  2016 .horrible_selfie.gif
drwxrwxr-x 2 ubuntu ubuntu 4096 Feb  8  2016 photos
-rw-rw-r-- 1 ubuntu ubuntu    0 Feb  8  2016 README.md

./test_dir/photos:
total 8
drwxrwxr-x 2 ubuntu ubuntu 4096 Feb  8  2016 .
drwxrwxr-x 3 ubuntu ubuntu 4096 Feb  8  2016 ..
-rw-rw-r-- 1 ubuntu ubuntu    0 Feb  8  2016 cat.gif
-rw-rw-r-- 1 ubuntu ubuntu    0 Feb  8  2016 index.html
-rw-rw-r-- 1 ubuntu ubuntu    0 Feb  8  2016 main.gif
-rw-rw-r-- 1 ubuntu ubuntu    0 Feb  8  2016 rudy_rigot.gif
ubuntu@ip-172-31-63-244:~/0x02-shell_redirections$ ./100-empty_casks
Rona_napping.gif
javascript
root.gif
..something
Kris_is_awesome :)
..hello.gif
file.sh
docker.gif
README.md
index.html
main.gif
cat.gif
rudy_rigot.gif
.horrible_selfie.gif
........gif
ubuntu@ip-172-31-63-244:~/0x02-shell_redirections$
````
### Repo:

* GitHub repository: alx-system_engineering-devops
* Directory: 0x02-shell_redirections
* File: 100-empty_casks
   
## 24. A gif is worth ten thousand words

Write a script that lists all the files with a .gif extension in the current directory and all its sub-directories.

* Hidden files should be listed
* Only regular files (not directories) should be listed
* The names of the files should be displayed without their extensions
* The files should be sorted by byte values, but case-insensitive (file aaa should be listed before file bbb, file .b should be listed before file a, and file Rona should be listed after file jay)
* One file name per line
* The listing should end with a new line
* You are not allowed to use basename, grep, egrep, fgrep or rgrep
````
  julien@production-503e7013:~/shell/fun_with_the_shell$ ls -Rla
    .:
    total 28
    drwxrwxr-x 3 julien julien 4096 Jan 20 03:35 .
    drwxrwxr-x 3 julien julien 4096 Jan 20 02:58 ..
    -rwxr--r-- 1 julien julien 43 Jan 20 02:59 0-commas
    -rwxr--r-- 1 julien julien 47 Jan 20 02:50 1-empty_casks
    -rwxrw-r-- 1 julien julien 68 Jan 20 03:35 2-gifs
    -rw-rw-r-- 1 julien julien 14 Jan 20 03:35 Makefile
    drwxrwxr-x 4 julien julien 4096 Jan 20 03:42 test_dir

    ./test_dir:
    total 16
    drwxrwxr-x 4 julien julien 4096 Jan 20 03:42 .
    drwxrwxr-x 3 julien julien 4096 Jan 20 03:35 ..
    -rw-rw-r-- 1 julien julien 0 Jan 20 03:40 .horrible_selfie.gif
    -rw-rw-r-- 1 julien julien 0 Jan 20 03:23 README.md
    -rw-rw-r-- 1 julien julien 0 Jan 20 03:17 docker.gif
    -rw-rw-r-- 1 julien julien 0 Jan 20 03:17 file.sh
    drwxrwxr-x 2 julien julien 4096 Jan 20 03:23 photos
    drwxrwxr-x 2 julien julien 4096 Jan 20 03:23 rep.gif

    ./test_dir/photos:
    total 8
    drwxrwxr-x 2 julien julien 4096 Jan 20 03:23 .
    drwxrwxr-x 4 julien julien 4096 Jan 20 03:42 ..
    -rw-rw-r-- 1 julien julien 0 Jan 20 03:23 cat.gif
    -rw-rw-r-- 1 julien julien 0 Jan 20 03:22 index.html
    -rw-rw-r-- 1 julien julien 0 Jan 20 03:23 main.gif
    -rw-rw-r-- 1 julien julien 0 Jan 20 03:23 Electra_napping.gif

    ./test_dir/rep.gif:
    total 8
    drwxrwxr-x 2 julien julien 4096 Jan 20 03:23 .
    drwxrwxr-x 4 julien julien 4096 Jan 20 03:42 ..
    julien@production-503e7013:~/shell/fun_with_the_shell$ ./101-gifs
    .horrible_selfie
    cat
    docker
    Electra_napping
    main
    julien@production-503e7013:~/shell/fun_with_the_shell$
    
 ````
### Repo:

* GitHub repository: alx-system_engineering-devops
* Directory: 0x02-shell_redirections
* File: 101-gifs
   
## 25. Acrostic

An acrostic is a poem (or other form of writing) in which the first letter (or syllable, or word) of each line (or paragraph, or other recurring feature in the text) spells out a word, message or the alphabet. The word comes from the French acrostiche from post-classical Latin acrostichis). As a form of constrained writing, an acrostic can be used as a mnemonic device to aid memory retrieval. Read more.

Create a script that decodes acrostics that use the first letter of each line.

* The ‘decoded’ message has to end with a new line
*  You are not allowed to use grep, egrep, fgrep or rgrep

````
julien@ubuntu:/tmp/0x02$ cat An\ Acrostic 
Elizabeth it is in vain you say
Love not"—thou sayest it in so sweet a way:
In vain those words from thee or L.E.L.
Zantippe's talents had enforced so well:
Ah! if that language from thy heart arise,
Breath it less gently forth—and veil thine eyes.
Endymion, recollect, when Luna tried
To cure his love—was cured of all beside—
His follie—pride—and passion—for he died.
julien@ubuntu:/tmp/0x02$ ./102-acrostic < An\ Acrostic 
ELIZABETH
julien@ubuntu:/tmp/0x02$ 

````
### Repo:

* GitHub repository: alx-system_engineering-devops
* Directory: 0x02-shell_redirections
* File: 102-acrostic
   
## 26. The biggest fan

Write a script that parses web servers logs in TSV format as input and displays the 11 hosts or IP addresses which did the most requests.

* Order by number of requests, most active host or IP at the top
* You are not allowed to use grep, egrep, fgrep or rgrep
Format:

````
host    When possible, the hostname making the request. Uses the IP address if the hostname was unavailable.
logname Unused, always -
time    In seconds, since 1970
method  HTTP method: GET, HEAD, or POST
url Requested path
response    HTTP response code
bytes   Number of bytes in the reply

````
Here is an example with one day of logs of the NASA website (1995).

````
julien@ubuntu:/tmp/0x02$ wget https://s3.amazonaws.com/alx-intranet.hbtn.io/public/nasa_19950801.tsv
--2022-03-08 11:08:26--  https://s3.amazonaws.com/alx-intranet.hbtn.io/public/nasa_19950801.tsv
Resolving s3.amazonaws.com (s3.amazonaws.com)... 52.217.171.144
Connecting to s3.amazonaws.com (s3.amazonaws.com)|52.217.171.144|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 782913 (765K) [binary/octet-stream]
Saving to: ‘nasa_19950801.tsv’

nasa_19950801.tsv   100%[===================>] 764.56K  --.-KB/s    in 0.008s

2022-03-08 11:08:26 (98.4 MB/s) - ‘nasa_19950801.tsv’ saved [782913/782913]

julien@ubuntu:/tmp/0x02$ head nasa_19950801.tsv
host    logname time    method  url     response        bytes
in24.inetnebr.com       -       807249601       GET     /shuttle/missions/sts-68/news/sts-68-mcc-05.txt 200     1839
uplherc.upl.com -       807249607       GET     /       304     0
uplherc.upl.com -       807249608       GET     /images/ksclogo-medium.gif      304     0
uplherc.upl.com -       807249608       GET     /images/MOSAIC-logosmall.gif    304     0
uplherc.upl.com -       807249608       GET     /images/USA-logosmall.gif       304     0
ix-esc-ca2-07.ix.netcom.com     -       807249609       GET     /images/launch-logo.gif 200     1713
uplherc.upl.com -       807249610       GET     /images/WORLD-logosmall.gif     304     0
slppp6.intermind.net    -       807249610       GET     /history/skylab/skylab.html     200     1687
piweba4y.prodigy.com    -       807249610       GET     /images/launchmedium.gif        200     11853
julien@ubuntu:/tmp/0x02$ ./103-the_biggest_fan < nasa_19950801.tsv 
www-relay.pa-x.dec.com
piweba3y.prodigy.com
www.thyssen.com
130.110.74.81
ix-min1-02.ix.netcom.com
uplherc.upl.com
reggae.iinet.net.au
seigate.sumiden.co.jp
ircgate1.rcc-irc.si
s150.phxslip4.indirect.com
torben.dou.dk
julien@ubuntu:/tmp/0x02$ 

````
### Repo:

* GitHub repository: alx-system_engineering-devops
* Directory: 0x02-shell_redirections
* File: 103-the_biggest_fan
   
