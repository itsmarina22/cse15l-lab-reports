
1. Log into ieng6
  - `<up>` `<Enter>`
  - looked through command history to get `ssh mlhu@ieng6.ucsd.edu`
2. Clone your fork of the repository from your Github account (using the SSH URL)
  - rm -rf lab7 (to make sure it's deleted)
  - SSH URL from github: git@github.com:itsmarina22/lab7.git
  - (after copying ssh url from the forked repository) git clone `<Ctrl+V>` `<Enter>`
3. Run the tests, demonstrating that they fail
  - cd l`<Tab>` `<Enter>`
  - bash test`<Tab>` `<Enter>`

4. Edit the code file to fix the failing test
  - Accessing the ListExamples.java file: vim L`<Tab>`.java `<Enter>`
  - Finding 'index1' in the file: `<n>` `<n>` `<n>` `<n>` `<n>` `<n>` `<n>` `<n>` `<n>`
  - Actually editing and changing 'index1' to 'index2': `<e>` `<x>` `<h>` 2 `<Esc>`
  - Saving the edits: :wq `<Enter>`
  
5. Run the tests, demonstrating that they now succeed
  - `<up>` `<up>` `<Enter>`
  - looked through command history to get `bash test.sh`

6. Commit and push the resulting change to your Github account (you can pick any commit message!)
  - git add .
  - git commit -m "Changed index1 to index2 in ListExamples.java"
  - git branch
  - git push origin main
