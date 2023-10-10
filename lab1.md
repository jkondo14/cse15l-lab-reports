# Lab Report 1
---

## cd with no Argument
```
[user@sahara ~]$ cd
[user@sahara ~]$
```
Since **cd** means change directory, using the cd without the argument did not change the directory since it did not know what directory it should change to. The working directory remained in the same directory which is the home directory. 
It was not an error since it did not change the directory due to an empty argument.


## cd with Directory Argument
```
[user@sahara ~]$ cd lecture1/
[user@sahara ~/lecture1]$
```
Using the **cd** with a directory caused the working directory to change to the given directory in the argument which was lecture1 for this instance.
It was not an error as it changed the directory.


## cd with File Argument
```
[user@sahara ~]$ cd lecture1/messages/en-us.txt
bash: cd: lecture1/messages/en-us.txt: Not a directory
```
Above we used **cd** with a file argument, which did not change the directory since a file is not a directory and outputted an error message.
It was an error as cd requires a directory as opposed to a file as an argument.


## ls with no Argument
```
[user@sahara ~/lecture1]$ ls
Hello.class  Hello.java  messages  README
```
**ls** is a command used to list files and folders of a directory, and here ls displayed the direct files and folders in the current directory, which is lecture1.
It was **not** an error and displayed all the direct directories and files.

## ls with Directory Argument
```
[user@sahara ~]$ ls lecture1/
Hello.class  Hello.java  messages  README
[user@sahara ~]$ ls lecture1/messages
en-us.txt  es-mx.txt  jp.txt  zh-cn.txt
```
Above **ls** was given a specific directory that the user wanted a list of and the terminal lists the files within that directory like .txt files of  the messages directory..
It was **not** an error as ls shows the files within the current Directory.

## ls with File Argument
```
[user@sahara ~/lecture1]$ ls messages/en-us.txt
messages/en-us.txt
[user@sahara ~/lecture1]$
```
Since **ls** is given a file as an argument, it just lists the file as the output since it is not a directory and cannot have any folders or file within the file.
It was **not** an error as ls displays the file used to enter as the argument.

## cat with no Argument
```
[user@sahara ~/lecture1]$ cat
hi
hi
hi
hi
^C
[user@sahara ~/lecture1]$
```
**cat** is used to print the contents of the file(s) given and since no file or path to a file was given, it did not print anything except for what the user printed in the terminal. Whenever the user printed "hi", the terminal printed "hi" on the next line, which occurred twice before **control+C** was used.
It was an error as it just printed the input and continued to do so until ***control+C*** was inserted.

## cat with Directory Argument
```
[user@sahara ~/lecture1]$ cat messages
cat: messages: Is a directory
[user@sahara ~/lecture1]$
```
Since **cat** was given a directory and not a file was given, the terminal gave an error message as the terminal did not know which file to print out within the given directory.
It was an error as cat requires a file for the argument and not a directory.

## cat with File Argument
```
[user@sahara ~/lecture1]$ cat messages/en-us.txt
Hello World!
[user@sahara ~/lecture1]$ cat Hello.java
import java.io.IOException;
import java.nio.charset.StandardCharsets;
import java.nio.file.Files;
import java.nio.file.Path;

public class Hello {
  public static void main(String[] args) throws IOException {
    String content = Files.readString(Path.of(args[0]), StandardCharsets.UTF_8);    
    System.out.println(content);
  }
}[user@sahara ~/lecture1]$
```
**cat** was given a file argument, which led to the terminal printing out the contents of the files, which were the en-us.txt file and the Hello.java file on the next line.
It was **not** an error as cat and cat printed out the txt file and code of the java file.
