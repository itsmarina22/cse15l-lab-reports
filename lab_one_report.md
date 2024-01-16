# 🍋 CSE 15L Lab 1 Report 
##### due on Tuesday, January 16 by 10pm ⚠️



## Workspace Commands
🏎️ `cd`
--
* Share an example of using the command with no arguments.
  * A screenshot or Markdown code block showing the command and its output
    > ![Image](lab_report_one_photos/cd_with_no_arguments.JPG)
  * What the working directory was when the command was run
    > `/home`
  * A sentence or two explaining why you got that output (e.g. what was in the filesystem, what it meant to have no arguments).
    > The output is observed because `cd` specifically is used to switch the current working directory to a given specified path. No path was provided to cd in the argument, so as a result, no output was generated or observed
  * Indicate whether the output is an error or not, and if it's an error, explain why it's an error.
    > This is not an error and is the expected output


* Share an example of using the command with a path to a directory as an argument.
  * A screenshot or Markdown code block showing the command and its output
    > ![Image](lab_report_one_photos/cd_with_path_to_directory.JPG)
  * What the working directory was when the command was run
    > `/home/lecture1`
  * A sentence or two explaining why you got that output (e.g. what was in the filesystem, what it meant to have no arguments).
    > `cd` specifically is used to switch the current working directory to a given specified path. A path to lecture1 has been specified, so now the working directory of the prompt is `/home/lecture1`
  * Indicate whether the output is an error or not, and if it's an error, explain why it's an error.
    > This is not an error and is the expected output


* Share an example of using the command with a path to a file as an argument.
  * A screenshot or Markdown code block showing the command and its output
      > ![Image](lab_report_one_photos/cd_with_path_to_a_file.JPG)
  * What the working directory was when the command was run
    > in the first time `cd Hello.java` was used, the working directory is `/home`
    > in the second time `cd Hello.java` was used, the working directory is `/home/lecture1`
  * A sentence or two explaining why you got that output (e.g. what was in the filesystem, what it meant to have no arguments).
    > for the first time `cd Hello.java`, the error was produced because `Hello.java` isn't a file or directory or path that is present within `/home`
    > 
    > for the second time `cd Hello.java`, now we have switched to the path that contains `Hello.java`, thus the file does exist; however, `Hello.java` is a file and not a directory or path. `cd` requires specifying a desired path or directory to go to
  * Indicate whether the output is an error or not, and if it's an error, explain why it's an error.
    > This is not an error and is the expected output



📰 `ls`
--
* Share an example of using the command with no arguments.
  * A screenshot or Markdown code block showing the command and its output
    >![Image](lab_report_one_photos/ls_with_no_arguments.JPG)
  * What the working directory was when the command was run
    > `/home`
  * A sentence or two explaining why you got that output (e.g. what was in the filesystem, what it meant to have no arguments).
    > The above outputs were observed because, within the `/home` working directory, the only file and/or folder to exist is the printed lecture1 folder, thus that is the only folder listed when the `ls` command is run without any additional arguments
  * Indicate whether the output is an error or not, and if it's an error, explain why it's an error.
    >These are all the expected output, and none of the above commands produced unexpected errors.

 
* Share an example of using the command with a path to a directory as an argument.
  * A screenshot or Markdown code block showing the command and its output
    >![Image](lab_report_one_photos/ls_with_path_to_directory.JPG)
  * What the working directory was when the command was run
    > for the `ls lecture1/` command, the working directory is `/home`
    >
    > for the `ls messages/` command, the working directory is `/home/lecture1`
  * A sentence or two explaining why you got that output (e.g. what was in the filesystem, what it meant to have no arguments).
    > for `ls lecture1/` command, the results were observed because within the lecture1 folder in the working directory of `/home`, three files (`Hello.class`, `Hello.java`, and `README`) and one folder (`messages`) are present
    >
    > for `ls messages/` command, the results were observed because within the messages folder in the working directory of `/home/lecture1`, four txt files (`en-us.txt`, `es-mx.txt`, `fr-ca.txt`, `zh-cn.txt`) are present.
  * Indicate whether the output is an error or not, and if it's an error, explain why it's an error.
    > These are all the expected output, and none of the above commands produced unexpected errors.

 
* Share an example of using the command with a path to a file as an argument.
  * A screenshot or Markdown code block showing the command and its output
    >![Image](lab_report_one_photos/ls_with_path_to_a_file.JPG)
  * What the working directory was when the command was run
    > Initially in the first `ls Hello.java`, the working directory is `/home`
    >
    > Then with the second `ls Hello.java` and the first `ls en-us.txt` and the first `ls en-us`, the working directory is `/home/lecture1`
    >
    > Finally with the second `ls en-us.txt` (no second `ls en-us` was included because this will produce an error stating that no such file or directory can be accessed, which is true because the file name is `en-us.txt` not just en-us), the working directory is `/home/lecture1/messages`
  * A sentence or two explaining why you got that output (e.g. what was in the filesystem, what it meant to have no arguments).
    > With the first `ls Hello.java`, the result was observed because similar to when we used `cd` with a file passed as an argument, `Hello.java` isn't a file or directory or path that is present within `/home`
    >
    > Then with the second `ls Hello.java`, because now we are in the working directory of `/home/lecture1`, "Hello.java" is printed as that file is indeed within the working directory now
    >
    > With the first `ls en-us.txt` and first `ls en-us`, the error was produced because we are not in the directory or path where those files reside in
    >
    > With the second `ls en-us.txt`, "en-us.txt" is printed because now we are in the working directory (`/home/lecture1/messages`) which that file is in
  * Indicate whether the output is an error or not, and if it's an error, explain why it's an error.
    > All the above outputs were expected, and none were unexpected errors. All errors produced were expected. 



➕ `cat`
--
* Share an example of using the command with no arguments.
  * A screenshot or Markdown code block showing the command and its output
    >![Image](lab_report_one_photos/cat_with_no_arguments.JPG)
  * What the working directory was when the command was run
    > `/home`
  * A sentence or two explaining why you got that output (e.g. what was in the filesystem, what it meant to have no arguments).
    > For this command with no arguments, whatever the user types in the terminal becomes printed as the output. This is because, within the current working directory, there is no file for the command to read and print out the content. There is only a folder called lecture1. According to the [documentation](https://man7.org/linux/man-pages/man1/cat.1.html), it states that when `cat` is used with no files (as is the case here), it'll copy the standard input to standard output. In other words, when one types more commands, one ends up typing them into the `cat` command, so it'll output what one has provided as an input.
  * Indicate whether the output is an error or not, and if it's an error, explain why it's an error.
    > This is not an error and instead, what is expected

 
* Share an example of using the command with a path to a directory as an argument.
  * A screenshot or Markdown code block showing the command and its output
    >![Image](lab_report_one_photos/cat_with_path_to_directory.JPG)
  * What the working directory was when the command was run
    > `/home`
  * A sentence or two explaining why you got that output (e.g. what was in the filesystem, what it meant to have no arguments).
    > The following output was produced because `cat` can only read files, not folders or directories. Because a folder/directory called lecture1 was provided, it outputs that, letting us know that lecture1 is a directory, and using cat will not read the contents of lecture1 as it is not a file. 
  * Indicate whether the output is an error or not, and if it's an error, explain why it's an error.
    > This is not an error and instead, what is expected

 
* Share an example of using the command with a path to a file as an argument.
  * A screenshot or Markdown code block showing the command and its output
    >![Image](lab_report_one_photos/cat_with_path_to_a_file.JPG)
  * What the working directory was when the command was run
    > for the `cat Hello.java command`, the working directory is `/home`
    >
    > ## ‼️: might want to check this
    > for the `cat /home/lecture1/Hello.java` command, the working directory is also `/home`
  * A sentence or two explaining why you got that output (e.g. what was in the filesystem, what it meant to have no arguments).
    > for the `cat Hello.java` command, the above error was observed because `Hello.java` isn't a file or directory or path that is present within `/home`
    >
    > for the `cat /home/lecture1/Hello.java` command, because we have now directly provided the path to be `/home/lecture1/Hello.java`, the prompt is able to navigate to the exact file `Hello.java`, and thus it'll print out all the content of `Hello.java`
  * Indicate whether the output is an error or not, and if it's an error, explain why it's an error.
    * ## ‼️: might want to check this, for all, is it okay to write that this is what is expected and there's no unexpected errors?
    > This is not an error and instead, what is expected



