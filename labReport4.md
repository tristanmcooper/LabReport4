Tristan Cooper - A17085814
# Lab Report 4

*Hello, and welcome to the Markdown page for my fourth CSE 15L Lab Report!*
We're going to look back at Week 7's Lab Contest and how I thought to speed up tasks in the command line!

**I managed to complete all the tasks with two commands, which meant a total of just five keyboard presses!**

## Step 4: "Log into `ieng6`"
![step4sc](/Users/tristancooper/Desktop/cse15l/LabReport4Repo/LabReport4/step4sc.png)

As you can see above, this step isn't anything we're unfamiliar with in this class.
Because we were allowed to use our command line history for these tasks, this command only took 2 keyboard presses
KEYS PRESSED: `<up>` and `<enter>`
Unfortunately, I couldn't figure out how to both log into `ieng6` and run the following command in the same line.

## Steps 5 - 9: All in one command!
Here is the command I ran:
`git clone git@github.com:tristanmcooper/lab7.git ; cd lab7 ; javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar ListExamplesTests.java ; java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests ; sed -i.bak '43s/index1/index2/' ListExamples.java ; rm -rf ListExamples.java.bak ; javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar ListExamplesTests.java ; java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests ; git add ListExamples.java ; git commit -m "JUnit passed" ; git push`

By separating each command with a semicolon `;`, I was able to run them all in the same line as if they were one command.
Therefore, this step took just one more keyboard repetition than logging into `ieng6`, because it existed one command further back in the history. 
KEYS PRESSED: `<up><up><enter>`
*Here is a screenshot of my terminal after running the command:*
![step5-9](/Users/tristancooper/Desktop/cse15l/LabReport4Repo/LabReport4/4-5sc.png)

## Summary of Commands:
1. `git clone git@github.com:tristanmcooper/lab7.git` Clones the repository __**(Step 5)**__
2. `cd lab7` Changes directory to the newly-created one.
3. `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar ListExamplesTests.java` Compiles JUnit tester file
4. `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests` Runs JUnit tester file __**(Step 6)**__
5. `sed -i.bak '43s/index1/index2/' ListExamples.java` Edit the code file to fix the failing test __**(Step 7)**__
Our lab tutor was kind enough to introduce us to the `sed` command last week. Here's how it works:
    - `-i` allows the `sed` command to run and "change the file in place." This means that it creates a temporary file *without* the changes made with the command. This is done in the background.
    - `.bak` is an extension that I found on a StackOverflow discussion. From my understanding, it *saves* the temporary file that's normally in the background to an *actual* backup file in your directory. This was the only way I could get bash to run this command without an error.
    - `43s` indicates the specific line number to search for a string to replace.
    - `index1` is the string to be replaced (the error).
    - `index2` is what it's replaced with.
    - `ListExamples.java` specifies the file to run the `sed` command on.
6. `rm -rf ListExamples.java.bak` Deletes the backup file that was just created from the `sed -i.bak` command. We do this because we don't want to push a new file to the repository, and it no longer serves a purpose.
7. `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar ListExamplesTests.java` Recompile the JUnit tests
8. `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests` Re-run the JUnit tests, showing that they now succeed __**(Step 8)**__
9. `git add ListExamples.java` Adds the changes from the file we fixed to this local commit.
10. `git commit -m "JUnit passed"` Commits those changes. `-m` stands for "message" __**(Step 9)**__
11. `git push` Finally, push the changes to the GitHub Repository __**(Step 9)**__



### Thank you for reading my Lab Report!


