# Lab Report 4
---
## Step 4

<img width="561" alt="Screenshot 2023-11-19 at 8 21 46 PM" src="https://github.com/jkondo14/cse15l-lab-reports/assets/146896972/7e313165-8464-4576-96a8-1322e7d73c23">

<br>
<br>

In order to log in to ssh, I typed into the terminal `ssh cs15lfa23nl@ieng6.ucsd.edu`
<br/>
**Keys pressed:** `ssh<space>cs15lfa23nl@ieng6.ucsd.edu<enter>`
<br/>
The **enter key** ran the command and logged me into my ssh account as I had set up to login without requiring me to enter the password for my ieng6 account. 

---

## Step 5

<img width="879" alt="Screenshot 2023-11-19 at 7 38 56 PM" src="https://github.com/jkondo14/cse15l-lab-reports/assets/146896972/985e8cb9-982b-4dba-8273-cc63ee30d7f5">

<br>
<br>

I typed `cd .ssh` in the terminal to change the working directory to the ssh directory.
<br/>
**Keys pressed:** `cd<space>.ssh<enter>`
<br/>
The **enter key** changed the working directory.
<br/>
<br/>
In the terminal, I typed `git clone git@github.com:jkondo14/lab7.git` to clone the repository we forked earlier.
<br/>
**Keys pressed:** `git<space>clone<space>git@github.com:jkondo14/lab7.git<enter>`
<br/>
The **enter key** cloned the repository into the ssh account. 

---

## Step 6
<img width="684" alt="Screenshot 2023-11-19 at 9 09 07 PM" src="https://github.com/jkondo14/cse15l-lab-reports/assets/146896972/1cd8948c-eb14-4e12-a569-51b4905c8062">

<br>
<br>

In the terminal, I typed `cd lab7` to change the working directory to the lab7 directory to access the files, including the bash script within the lab7 directory.
<br/>
**Keys pressed:** `cd<space>lab7<enter>`
<br/>
The **enter key** changed the working directory.
<br/>
<br/>
In the terminal, I typed `bash test.sh` to run the test script, where test.sh was the name of the bash script to be run. 
<br/>
**Keys pressed:**  `bash<space>test.sh<enter>`
The **enter key** ran the test script and showed the test results in the terminal.

---

## Step 7
<img width="738" alt="Screenshot 2023-11-19 at 7 48 00 PM" src="https://github.com/jkondo14/cse15l-lab-reports/assets/146896972/6c30be7b-64fd-4f09-88c0-1b2df9902ef9">

<br>
<br>

In the terminal, I typed **vim ListExamples.java** to edit the ListExamples.java.
<br/>
**Keys pressed:**  `<down><down><down><down><down><down><down>lllllllllllxi2<esc>:wq`
The down key was used to get to the line I wanted to edit, which was line 44 where the error was, and I used the l key to move to the right to the bug. The x key was used to delete 1, which was the bug,
the i key was to enter insert mode, the 2 was to edit the index to index2, the escape key was to escape editing, and the `:wq` command was used to save and exit the file.

---

## Step 8

<img width="387" alt="Screenshot 2023-11-19 at 9 45 14 PM" src="https://github.com/jkondo14/cse15l-lab-reports/assets/146896972/d0207ed1-b94f-4cbf-aaab-4d903f3b85d8">
<br>
<br>
In the terminal, I accessed the command history to use `bash test.sh` to run the test script. 
<br/>
**Keys pressed:**  `<up><up><enter>`
<br/>
The **up key** was used to access the previous command `bash test.sh` from the command history, and the **enter key** ran the test script and showed the test results in the terminal, which passed as we fixed the errors in ListExamples.java.

---

## Step 9

---
<img width="751" alt="Screenshot 2023-12-03 at 1 13 06 AM" src="https://github.com/jkondo14/cse15l-lab-reports/assets/146896972/e6ba4a4a-b2fd-49e4-b3b0-4fbeb9e25d6a">
<br>
<br>
As our final steps of the lab, I committed and pushed the changes to my GitHub Account.
**Keys pressed:** `git<space>add<space>ListExamples.java<enter>`
**Keys pressed:** `git<space>commit<space>-m<space>"fixed index2"<enter>`
**Keys pressed:** `git<space>push<enter>`
Using git add, git commit, and git push, I successfully pushed the repository changes to match the repository hosted on the remote, which is GitHub.

