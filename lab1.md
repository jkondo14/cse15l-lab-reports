# Lab Report 1
---

## cd with no Argument
```
[user@sahara ~]$ cd /home/lecture1/messages
[user@sahara ~/lecture1/messages]$ pwd
/home/lecture1/messages
[user@sahara ~/lecture1/messages]$ cd
[user@sahara ~]$ pwd
/home
[user@sahara ~]$
```
In the example above, the working directory is *lecture1*, and when **cd** without argument was used, the working directory changed to */home*. Since **cd** means change directory, using the **cd** without the argument changes the working directory to the home directory as that is the default directory and no specific directory was given in the argument.
It was **not** an error since it did change the working directory to the home directory.


## cd with Directory Argument
```
[user@sahara ~]$ cd lecture1/
[user@sahara ~/lecture1]$ pwd
/home/lecture1
```
In the above example, the working directory is the *home* directory, and **cd** was given a directory argument, which was *lecture1*, and the working directory was changed to *lecture1*. Using the **cd** with a directory caused the working directory to change to the given directory in the argument, which was *lecture1* for this instance.
It was **not** an error as **cd** changed the directory.


## cd with File Argument
```
[user@sahara ~]$ cd lecture1/messages/en-us.txt 
bash: cd: lecture1/messages/en-us.txt: Not a directory
[user@sahara ~]$ cd lecture1/messages/
[user@sahara ~/lecture1/messages]$ cd en-us.txt 
bash: cd: en-us.txt: Not a directory
```
In the above example, the working directory was the *home* directory, and when using **cd** with a txt file, which was the *en-us.txt*, the terminal sent an error message. Even when changing to the direct parent directory of the *en-us.txt*, the terminal still gave us an error. Above we used **cd** with a file argument, which did not change the directory since a file is not a directory and outputted an error message.
It was an error as **cd** requires a directory instead of a file as an argument.


## ls with no Argument
```
[user@sahara ~/lecture1]$ ls
Hello.class  Hello.java  messages  README
```
In the code above the working directory is *lecture1* and when **ls** was used to show the direct files and directory in the working directory, which are *Hello.class*, *Hello.java*, *messages*, and *README*. **ls** is a command used to list files and folders of a directory, and here **ls** without an argument displays the direct files and folders in the working directory.
It was **not** an error and displayed all the direct directories and files.

## ls with Directory Argument
```
[user@sahara ~]$ ls lecture1/
Hello.class  Hello.java  messages  README
[user@sahara ~]$ ls lecture1/messages
en-us.txt  es-mx.txt  jp.txt  zh-cn.txt
```
In the example above, the working directory was *home*, and when using **ls** with a directory argument, which was *lecture1*, the terminal listed out the direct files and directory under lecture1. When **ls** is given a specific directory that the user wants to list out, the terminal lists the files within that directory like .txt files of the messages directory in lines 3 & 4.
It was **not** an error as **ls** shows the files within the current Directory.

## ls with File Argument
```
[user@sahara ~/lecture1]$ ls messages/en-us.txt
messages/en-us.txt
[user@sahara ~/lecture1]$ cd messages
[user@sahara ~/lecture1/messages]$ ls en-us.txt
en-us.txt
```
In the code above, the working directory is *lecture1*, and when a file path is given as an argument for **ls**, a file path is printed out in the terminal. Since **ls** is given a file as an argument, it just lists the file as the output since it is not a directory and cannot have any folders or files within the file, such as when we had the working directory in lecture1/messages and gave the terminal *en-us.txt* as the argument for **ls**.
It was **not** an error as **ls** displays the file used to enter as the argument.

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
In the code example above, **cat** was used without any arguments, where the working directory was *lecture1*, and proceeded to the next line, where the terminal printed out what the user printed in the line before. **cat** is used to print the contents of the file(s) given and since no file or path to a file was given, it did not print anything except for what the user printed in the terminal. Whenever the user printed "hi", the terminal printed "hi" on the next line, which occurred twice before **control+C** was used.
It was **not** an error as it just printed the input and did not throw an error message. This continued to occur until ***control+C*** was inserted, where the terminal ended the **cat** process.

## cat with Directory Argument
```
[user@sahara ~/lecture1]$ cat messages
cat: messages: Is a directory
[user@sahara ~/lecture1]$
```
In the code above, the working directory was *lecture1*, and *messages*, a directory, was given as the argument for **cat**, in which the terminal threw out an error message. Since **cat** was given a directory and not a file, the terminal gave an error message as the terminal did not know which file to print out within the given directory, which was *messages*.
It was an error as **cat** requires a file for the argument and not a directory.

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
In the example above, **cat** was given a file path, *messages/en-us.txt* and *Hello.java*, in the working directory of lecture1 and printed "Hello World!" and the Java code. **cat** was given a file argument, which led to the terminal printing out the contents of the files, which were the *en-us.txt* file and the Hello.java file from the *lecture1* working directory on the next line.
It was **not** an error as **cat** and **cat** printed out the txt file and code of the java file.
