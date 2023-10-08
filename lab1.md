**cd with no Argument**
```
[user@sahara ~]$ cd
[user@sahara ~]$
```
Since cd means change directory, using the cd without the argument did not change the directory and remains in the same directory. 
It was not an error since it did not change the directory due to an empty argument.


**cd with Directory Argument**
```
[user@sahara ~]$ cd lecture1/
[user@sahara ~/lecture1]$
```
Since cd means change directory, using the cd with a directory will change the current directory to the given directory in the argument.
It was not an error as it changed the directory.


**cd with File Argument**
```
[user@sahara ~]$ cd lecture1/messages/en-us.txt
bash: cd: lecture1/messages/en-us.txt: Not a directory
```
Since cd means change directory, using a cd with a file argument will not change the directory since it is not a directory.
It was an error as cd requires a directory as opposed to a file as an argument.


**ls with no Argument**
```
[user@sahara ~/lecture1]$ ls
Hello.class  Hello.java  messages  README
```
ls is a command used to list files and folders of a directory, and here ls displayed the direct files and folders in the current directory, which is lecture1.
It was **not** an error and displayed all the direct directories and files.

**ls with Directory Argument**
```
[user@sahara ~]$ ls lecture1/
Hello.class  Hello.java  messages  README
[user@sahara ~]$ ls lecture1/messages
en-us.txt  es-mx.txt  jp.txt  zh-cn.txt
```
ls is a command used to list files and folders of a directory, and ls when given a specific directory lists the files within that directory like .txt files of messages.
It was **not** an error as ls shows the files within the current Directory.

**ls with File Argument**
```
[user@sahara ~/lecture1]$ ls messages/en-us.txt
messages/en-us.txt
[user@sahara ~/lecture1]$
```
ls is a command used to list files and folders of a directory, and since ls is given a file as an argument, it just lists the file as the output.
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
cat is used to print the contents of the file(s) given and since no file or path to a file was given, it did not print anything but what the user printed in the terminal.
It was an error as it just printed the input and continued to do so until ***control+C*** was inserted.

**cat with Directory Argument**
```
[user@sahara ~/lecture1]$ cat messages
cat: messages: Is a directory
[user@sahara ~/lecture1]$
```
cat is used to print the contents of the file(s) given and since a directory and not a file was given, the terminal gave an error message.
It was an error as cat requires a file for the argument and not a directory.

**cat with File Argument**
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
cat is used to print the contents of the file(s) given and since a file was given, the terminal printed out the contents of the files.
It was **not** an error as cat and cat printed out the txt file and code of the java file.
