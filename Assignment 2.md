# Git/GitHub Assignment

* **INDIVIDUAL ASSIGNMENT**
* **Deadline:** Sept-08
* **How to submit**: For each empty grey box, please provide with an answer to the item in a document. Do the following to *submit* the **Part 1** of your assignment:
1. Use the repo you created for Assignmen1 (*INF502*); 
2. create a file called *"Assignment2.md"* and paste your answers there (tip: click on *"Raw"* at the right-top of this file to get the markdown source); 

For **Part 2** the pull request created will the submission (except for item 4, which you need to add to the end of the Assignemnt1.md).

* **Value**: Part of homework grade

## Description
This assignment is composed of two parts. 
- [Part 1](#Part-1-Dealing-with-git) consists of executing a sequence of commands and giving explanations about the commands you have to run. 
For each item in the assignment, please provide appropriate explanation and/or the details requested.
- [Part 2](#Part-2-Using-GitHub) consists of creating a Markdown file on a fork of this course and creating a pull request towards this repo.

### Part 1: Dealing with git

To conduct this, you will have to download [handson.zip](handson.zip) and unzip it.
handson folder is a git repository. Using the command line change the directory to "handson/"

The empty boxes
```
SLCpiggy@Efay MINGW64 ~
$ cd ./desktop/handson

```
represent the content you need to fill and post on your private repository


1. Describe what is the output of the following commands
    -  `git branch` 
    -  `git checkout BRANCH_NAME` (USE THE NAME OF AN EXISTING BRANCH)
    -  `git log --decorate`

```
SLCpiggy@Efay MINGW64 ~/desktop/handson (master)
$ git branch
* master
  math

SLCpiggy@Efay MINGW64 ~/desktop/handson (master)
$ git checkout math
Switched to branch 'math'

SLCpiggy@Efay MINGW64 ~/desktop/handson (math)
$ git log --decorate
commit e3c629dd524712aedea96d7dbaad1c50d12b5b5e (HEAD -> math)
Author: Igor Steinmacher <igorsteinmacher@gmail.com>
Date:   Wed Aug 14 23:13:48 2019 -0700

    Adding some more knowledge to the function

commit 654b490a181dedf82dd6deda5f9848d6cca05918
Author: Igor Steinmacher <igorsteinmacher@gmail.com>
Date:   Wed Aug 14 23:12:14 2019 -0700

    Added a draft of A.py

commit 2dfb02c3f9383d6c3b2695c99e175d8b85f594a1
Author: Igor Steinmacher <igorsteinmacher@gmail.com>
Date:   Wed Aug 14 23:08:47 2019 -0700

     Creating all files (all empty)

`git branch` tells all branches you have.
`git checkout BRANCH_NAME` Choose the branch you want.
`git log --decorate` gives the related infomation.

```

2. Try `git log --graph --all`. What do you see?
```
SLCpiggy@Efay MINGW64 ~/desktop/handson (math)
$ git log --graph --all
* commit 18931d12a8be7cac049b73c6bc8136e9482f3371 (master)
| Author: Igor Steinmacher <igorsteinmacher@gmail.com>
| Date:   Wed Aug 14 23:15:28 2019 -0700
|
|     Making a small change here
|
| * commit e3c629dd524712aedea96d7dbaad1c50d12b5b5e (HEAD -> math)
|/  Author: Igor Steinmacher <igorsteinmacher@gmail.com>
|   Date:   Wed Aug 14 23:13:48 2019 -0700
|
|       Adding some more knowledge to the function
|
* commit 654b490a181dedf82dd6deda5f9848d6cca05918
| Author: Igor Steinmacher <igorsteinmacher@gmail.com>
| Date:   Wed Aug 14 23:12:14 2019 -0700
|
|     Added a draft of A.py
|
* commit 2dfb02c3f9383d6c3b2695c99e175d8b85f594a1
  Author: Igor Steinmacher <igorsteinmacher@gmail.com>
  Date:   Wed Aug 14 23:08:47 2019 -0700

       Creating all files (all empty)


```

3. Use `git diff BRANCH_NAME` to view the differences from a branch and the current branch.
   Summarize the difference from master to the other branch.

```
SLCpiggy@Efay MINGW64 ~/desktop/handson (math)
$ git diff master
diff --git a/A.py b/A.py
index dc1e9bd..0afa98c 100644
--- a/A.py
+++ b/A.py
@@ -1,3 +1,11 @@
 #this is just an example, do not freak out
 def calculate_this(operator, num1, num2):
-   print 'my knowledge is limited'
+   if operator == 'sum':
+      print num1 + num2
+      print 'That was easy buddy'
+   else:
+      if operator == 'subtraction':
+         print num1 - num2
+         print 'I could handle that...'
+      else:
+         print 'my knowledge is limited'
diff --git a/B.py b/B.py
index c63f94c..e69de29 100644
--- a/B.py
+++ b/B.py
@@ -1 +0,0 @@
-# Another file that will receive a line of code... at least.

The results showed one is num1+num2, the other one is num1-num2.
```

4. Write a command sequence to merge the non-master branch into `master`

```
SLCpiggy@Efay MINGW64 ~/desktop/handson (master)
$ git merge math
Merge made by the 'recursive' strategy.
 A.py | 10 +++++++++-
 1 file changed, 9 insertions(+), 1 deletion(-)

```


5. Write a command (or sequence) to (i) create a new branch called `math` (from the `master`) 
and (ii) change to this branch (yes, `math` is already there, just report what you've done, the error and the reason you got the error. If you deleted and recreated the branch, you are fine too)

```
C:\Users\SLCpiggy\Desktop\handson>git branch math
fatal: A branch named 'math' already exists.

```
   
6. Edit B.py adding the following source code below the content you have there
```
print 'I know math, look:'
print 2+2
```

7. Write a command (or sequence) to commit your changes
```
C:\Users\SLCpiggy\Desktop\handson>git add B.py

C:\Users\SLCpiggy\Desktop\handson>git commit -m "There are two lines."
[math 56dc6fb] There are two lines.
 1 file changed, 2 deletions(-)

```

8. Change back to the `master` branch and change B.py adding the following source code (commit your change to `master`):
```
C:\Users\SLCpiggy\Desktop\handson>git checkout master
Switched to branch 'master'

C:\Users\SLCpiggy\Desktop\handson>git add B.py

C:\Users\SLCpiggy\Desktop\handson>git commit -m "There is one line."
[master ec74fd0] There is one line.
 1 file changed, 1 insertion(+), 4 deletions(-)
```
```
print 'hello world!'
```

9. Write a command sequence to merge the `math` branch into `master` and describe what happened
```
C:\Users\SLCpiggy\Desktop\handson>git merge math
Auto-merging B.py
CONFLICT (content): Merge conflict in B.py
Automatic merge failed; fix conflicts and then commit the result.

```
   
10. Write a set of commands to abort the merge
```
C:\Users\SLCpiggy\Desktop\handson>git merge --abort

```
   
11. Now repeat item 9, but proceed with the manual merge (Editing B.py). All implemented functions are needed. Explain your procedure
```
First, we should abort the merge.
C:\Users\SLCpiggy\Desktop\handson>git merge --abort

C:\Users\SLCpiggy\Desktop\handson>git reset --merge

Second, we need to delete one of the content of B.py.

Third, we commit it.
C:\Users\SLCpiggy\Desktop\handson>git add B.py

C:\Users\SLCpiggy\Desktop\handson>git commit -m "manually fixing B.py"
[master 5d09896] manually fixing B.py

Finally, we merge them.
C:\Users\SLCpiggy\Desktop\handson>git merge math
Already up to date.

```

12. Write a command (or set of commands) to proceed with the merge and make `master` branch up-to-date
```
C:\Users\SLCpiggy\Desktop\handson>git rebase master
Current branch master is up to date.
```

### Part 2: Using GitHub

Report your experience of making this submission, including the steps followed, commands used, and hurdles faced (within the file you created for the **Part 1**.
```
1. I downloaded handson, and extract them to desktop.
2. I relocated the directory using "cd ./desktop/handson".
3. I tried three commands 'git branch','git checkout' and'git log --decorate'.
4. I input the 'git log --graph --all' to see what happened.
5. I used 'git diff math' to compare the differences of "master" and "math".
6. I merged math into master, but it needed to set up user.email and user.name. 
7. I tried to created the new branch of math, but it had already exsited there, so I just checkout math.
8. I modified B.py and committed it (in math).
9. I went back to 'master', and also made the changes.
10. I merged math into master after committing the contents.
11. I needed to proceed with the manual merge. First, I used two commands to abort the merge: "git merge --abort" and "git reset --merge"; Second, I edited 'math' manually. Third, I commit the content. Finally, I merged them.
12. I used "git rebase master" to be up to date.

Problems: 1. I first use the MINGW64 to proceed step 1 to step 6, but when I was trying to use "vim B.py", it showed a window but nothing there. I do not know how to use, thus I changed to "Select Git CMD".  
          2. After modifying the lines in 'math' and 'master', I cannot merge 'math' into 'master', so I have to open B.py to modify it.
      
```




