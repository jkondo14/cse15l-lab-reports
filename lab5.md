 # Lab Report 5
---
## Part 1 - Debugging Scenario

### Annonymous

**18 minutes ago**

<br/>

<img width="498" alt="Screenshot 2023-12-03 at 3 21 29 AM" src="https://github.com/jkondo14/cse15l-lab-reports/assets/146896972/22cc7035-7da1-4736-9926-60169a55b9a6">

<img width="669" alt="Screenshot 2023-12-03 at 3 21 44 AM" src="https://github.com/jkondo14/cse15l-lab-reports/assets/146896972/c012ee80-03e3-4ead-a047-97a62370b082">

<img width="791" alt="Screenshot 2023-12-03 at 3 20 57 AM" src="https://github.com/jkondo14/cse15l-lab-reports/assets/146896972/afe92f3c-4abd-4aa8-b383-f4ce7830cbbf">


Hi, when testing the Java File ArrayExamples.java with the bash script, test.sh, I continuously run into failures and never get the answer correctly. I believe my test input and expectations are correct as they are in reverse order. I am wondering what about ArrayExamples.java, in particular the reversed function, which may be incorrect as I am not sure what the problem may be.

---

### Joe Politz
**Just Now**

Hello there. Read the instructions clearly as it states to return a new array and when traversing the for loop, what would happen if the array is pulling the values for its indices from the same array? 

---
### Student's work after receiving assistance
<img width="415" alt="Screenshot 2023-12-03 at 3 37 31 AM" src="https://github.com/jkondo14/cse15l-lab-reports/assets/146896972/cb538c39-9ece-4ff5-a5fb-09c1259bf78d">

<img width="434" alt="Screenshot 2023-12-03 at 3 39 15 AM" src="https://github.com/jkondo14/cse15l-lab-reports/assets/146896972/413102a2-52fd-4d20-aba7-971f35b5ccad">

---

**File/Directory Structure:** Need the lab3 files and be in the lab3 directory to access the files and the bash script

<br/>

**Contents of each file before fixing:**

<br/> 

ArrayExamples.java
```
public class ArrayExamples {

  // Changes the input array to be in reversed order
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }

  // Returns a *new* array with all the elements of the input array in reversed
  // order
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }

  // Averages the numbers in the array (takes the mean), but leaves out the
  // lowest number when calculating. Returns 0 if there are no elements or just
  // 1 element in the array
  static double averageWithoutLowest(double[] arr) {
    if(arr.length < 2) { return 0.0; }
    double lowest = arr[0];
    for(double num: arr) {
      if(num < lowest) { lowest = num; }
    }
    double sum = 0;
    for(double num: arr) {
      if(num != lowest) { sum += num; }
    }
    return sum / (arr.length - 1);
  }


}
```
ArrayTests.java
```
import static org.junit.Assert.*;
import org.junit.*;

public class ArrayTests {



  @Test
  public void testReversed() {
    int[] input1 = {1,2,3};
    assertArrayEquals(new int[]{3,2,1}, ArrayExamples.reversed(input1));
  }

    @Test
  public void testReversed2() {
    int[] input1 = {8,9};
    assertArrayEquals(new int[]{9,8}, ArrayExamples.reversed(input1));
  }
  
}

```

**Command Line:** `bash test.sh`

**How to fix:** Firstly you need to change the return statement to newArray as the function needs to return a new Array stated by the comments. Then you will change arr[i] to newArray[i] as we would like to add to the newArray in order to return it with some content and change the newArray[arr.length - i - 1] to arr[arr.length - i - 1] as newArray is initially empty so we cannot grab any content to copy onto the array.

---
## Part 2 - Reflection
In CSE 15L, I learned a lot about bash scripts and the usefulness of the terminal as I hardly used the terminal for coding before, except for downloading Python 3 using pip3. I learned the
various commands such as cd, ls, and cat, and enjoyed creating bash scripts to allow for the recycling of code and the functionality of bash scripts. This class taught me how to create a GitHub
Page and Markdown, things many classes will never teach, and the functions of GitHub, like committing and forking and pushing changes as I always have wondered how GitHub changes were made.
I would like to take this time and thank Professor Joe for his constant support and empathy towards his students and congratulate him on his second child as it is a very important and beautiful
moment of life. I would like to also thank the TAs and tutors for their continuous patience and guidance to us, students, as we were lost on various parts of this class during labs and they truly
showed a helping hand with a smile! 
