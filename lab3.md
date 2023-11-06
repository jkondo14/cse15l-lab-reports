# Lab 3 Report - Jake Kondo
---
## Part 1 - Bugs
---
### Fail-Inducing Input
```
  @Test
  public void testReversed() {
    int[] input1 = {8,9};
    assertArrayEquals(new int[]{9,8}, ArrayExamples.reversed(input1));
  }
```
### Input that does not induce a failure
```
  @Test
  public void testReversed() {
    int[] input1 = {};
    assertArrayEquals(new int[]{}, ArrayExamples.reversed(input1));
  }
```
### Symptoms of Fail-Inducing Input
```
  @Test
  public void testReversed() {
    int[] input1 = {};
    assertArrayEquals(new int[]{}, ArrayExamples.reversed(input1));
  }

    @Test
  public void testReversed2() {
    int[] input1 = {8};
    assertArrayEquals(new int[]{8}, ArrayExamples.reversed(input1));
  }
```
<img width="979" alt="Screenshot 2023-11-05 at 8 50 39 PM" src="https://github.com/jkondo14/cse15l-lab-reports/assets/146896972/35a553f6-b3d4-4d9c-8ac1-cdb98be92b74">

### Bug Fix Before and After

**Before**
```
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
```
**After**
```
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length - i - 1];
    }
    return newArray;
  }
```
<img width="402" alt="Screenshot 2023-11-05 at 8 56 27 PM" src="https://github.com/jkondo14/cse15l-lab-reports/assets/146896972/c90a469e-dd92-47cd-b0f3-5bd0064c2b1d">
<br />
The original code changed each index of the original array with elements from newArray, which does not contain any element since it is a new Array, thus the code did not copy into the right array or copy it in reverse order into either array.
<br />
<br />
The new code copies the elements from the original array into newArray in reverse orders and returns newArray unlike the original code, where it returned the original array.

## Part 2 - Researching Commands
### Find Command
**find -empty**
```
tamonkondo@Tamons-MacBook-Air technical % find biomed -empty
biomed/s.txt
```
The find command with the empty primary finds an empty file within the directory and in the code above, I added an empty txt file to biomed. After that, I used the find biomed -empty command to see if the biomed directory had any empty files, which the command could find. The find -empty command is useful to ensure there are no empty files or which empty files are on hand to write in. 
```
tamonkondo@Tamons-MacBook-Air technical % find biomed -empty
biomed/s.txt
tamonkondo@Tamons-MacBook-Air technical %
```
The find command with the empty primary finds an empty file within the directory and in the code above, since the plos directory did not have any empty files, the terminal returned nothing. The find -empty command is useful to ensure there are no empty files or which empty files are on hand to write in. 
<br />
<br />
**find -delete**
```
tamonkondo@Tamons-MacBook-Air technical % find biomed/s.txt -delete
tamonkondo@Tamons-MacBook-Air technical %
```
The find -delete command takes a file path as an argument and deletes the file in the file path like how the command deleted s.txt from the biomed directory. This is useful when we need to get rid of a file when we know the name and do not want to look for it, especially in bigger files where there can be tens of thousands of files.
```
tamonkondo@Tamons-MacBook-Air technical % find biomed/a.txt -delete    
find: biomed/a.txt: No such file or directory
tamonkondo@Tamons-MacBook-Air technical % find biomed/rr196.txt -delete
tamonkondo@Tamons-MacBook-Air technical % 
```
The find -delete command takes a file path as an argument and deletes the file in the file path like how the command deleted rr196.txt from the biomed directory. However, this command does not work if the file does not exist within the directory such as a.txt. This is useful when we need to get rid of a file when we know the name and do not want to look for it, especially in bigger files where there can be tens of thousands of files.
<br />
<br />
**find -type**
```
tamonkondo@Tamons-MacBook-Air technical % find biomed/rr191.txt  -type f
biomed/rr191.txt
tamonkondo@Tamons-MacBook-Air technical % 
```
The find -type command finds a certain type of file depending on what the argument is after the type command. The code above shows that using -type with f shows the regular files within biomed/rr191.txt, which is the rr191.txt file within the biomed directory. The -type command for find is especially useful when looking for a certain type of file within a directory or a folder since there can be a lot of files and this command can be used to filter it.
```
tamonkondo@Tamons-MacBook-Air technical % find 911report -type f
911report/chapter-13.4.txt
911report/chapter-13.5.txt
911report/chapter-13.1.txt
911report/chapter-13.2.txt
911report/chapter-13.3.txt
911report/chapter-3.txt
911report/chapter-2.txt
911report/chapter-1.txt
911report/chapter-5.txt
911report/chapter-6.txt
911report/chapter-7.txt
911report/chapter-9.txt
911report/chapter-8.txt
911report/preface.txt
911report/chapter-12.txt
911report/chapter-10.txt
911report/chapter-11.txt
tamonkondo@Tamons-MacBook-Air technical %
```
The find -type command finds a certain type of file depending on what the argument is after the type command. The code above shows that using -type with f shows the regular files within the 911report directory, which is the handful of files within the 911report directory. The -type command for find is especially useful when looking for a certain type of file within a directory or a folder since there can be a lot of files and this command can be used to filter it.
