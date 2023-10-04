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
It was not an error and displayed all the directories

**ls with file Argument**
```
[user@sahara ~]$ ls lecture1/
Hello.class  Hello.java  messages  README
[user@sahara ~]$ ls lecture1/messages
en-us.txt  es-mx.txt  jp.txt  zh-cn.txt
```
