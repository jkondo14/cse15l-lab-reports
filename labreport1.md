**cd with no Argument**
```
[user@sahara ~]$ cd
[user@sahara ~]$
```
It was not an error, it did not change the directory due to an empty argument.


**cd with Directory Argument**
```
[user@sahara ~]$ cd lecture1/
[user@sahara ~/lecture1]$
It was not an error as it changed the directory.
```
It was not an error as it changed the directory.


**cd with File Argument**
```
[user@sahara ~]$ cd lecture1/messages/en-us.txt
bash: cd: lecture1/messages/en-us.txt: Not a directory
```
It was an error as cd requires a file as an argument.


**ls with no Argument**
```
[user@sahara ~/lecture1]$ ls
Hello.class  Hello.java  messages  README
```
It was **not** an error and displayed all the direct directories and files.

**ls with Directory Argument**
```
[user@sahara ~]$ ls lecture1/
Hello.class  Hello.java  messages  README
[user@sahara ~]$ ls lecture1/messages
en-us.txt  es-mx.txt  jp.txt  zh-cn.txt
```
It was **not** an error as ls shows the files within the current Directory.

**ls with File Argument**
```
[user@sahara ~/lecture1]$ ls messages/en-us.txt
messages/en-us.txt
[user@sahara ~/lecture1]$
```
It was **not** an error as ls displays the file used to enter as the argument.

**cat with no Argument**
```
[user@sahara ~/lecture1]$ cat
hi
hi
hi
hi
^C
[user@sahara ~/lecture1]$
```
It was an error as it just printed the input and continued to do so until ***control+C*** was inserted.

**cat with Directory Argument**
```
[user@sahara ~/lecture1]$ cat messages
cat: messages: Is a directory
[user@sahara ~/lecture1]$
```
It was an error as cat requires a file for the argument and not a directory.
