# CSE 15L Lab 4 Report 
### by Marina Hu (W24 A02 Section)
#### due on Tuesday, February 27 by 10 PM

1. Log into ieng6
  a. Looked through command history to get `ssh mlhu@ieng6.ucsd.edu`:
    > `<up>` `<Enter>`
2. Clone your fork of the repository from your GitHub account (using the SSH URL)
  - For reference, the SSH URL from GitHub for my forked repo
    > git@github.com:itsmarina22/lab7.git
  - To make sure it's deleted:
    > rm -rf lab7
  - After copying ssh url from the forked repository, clone it into my ieng6:
    > git clone `<Ctrl+V>` `<Enter>`
3. Run the tests, demonstrating that they fail
  - Ensuring that I'm within the `lab7` directory:
    > cd l`<Tab>` `<Enter>`
  - Running the tests and noticing that they are failing:
    > bash test`<Tab>` `<Enter>`

4. Edit the code file to fix the failing test
  - Accessing the ListExamples.java file:
    > vim L`<Tab>`.java `<Enter>`
  - Finding 'index1' in the file:
    > `<n>` `<n>` `<n>` `<n>` `<n>` `<n>` `<n>` `<n>` `<n>`
  - Actually editing and changing 'index1' to 'index2' by first going to the end of the word(`<e>`), going one step to the left so that the cursor is over the '1' (`<h>`), then deleting the '1'(`<x>`), and changing it to '2' before exiting the editing mode (`<Esc>`):
    > `<e>` `<h>` `<x>` 2 `<Esc>`
  - Saving the edits:
    > :wq `<Enter>`
  
5. Run the tests, demonstrating that they now succeed
  - Looked through command history to get `bash test.sh`:
    > `<up>` `<up>` `<Enter>`

6. Commit and push the resulting change to your Github account (you can pick any commit message!)
  - Staging the changes I've made to the file:
    > git add .
  - Committing the staged changes with a custom commit message:
    > git commit -m "Changed index1 to index2 in ListExamples.java"
  - Double-checking what is the branch name that I'm working on:
    > git branch
  - Pushing the committed changes to my GitHub fork of the repo:
    > git push origin main
