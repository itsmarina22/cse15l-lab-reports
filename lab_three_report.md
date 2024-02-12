# CSE 15L Lab 3 Report 
### by Marina Hu (W24 A02 Section)
#### due on Tuesday, February 13 by 10 PM

Part 1 - Bugs
--
Choose one of the bugs from week 4's lab: Testing `reverseInPlace(int[] arr)`

- A failure-inducing input for the buggy program, as a JUnit test and any associated code (write it as a code block in Markdown)
  ```
  @Test
  public void testReverseInPlace2() {
    int[] input1 = { 2,1 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 1,2 }, input1);   // Expected [2] but was [1]
  }
  ```
- An input that doesn't induce a failure, as a JUnit test and any associated code (write it as a code block in Markdown)
  ```
  @Test 
	public void testReverseInPlace() {
    int[] input1 = { 3 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 3 }, input1);
	}
  ```
- The symptom, as the output of running the tests (provide it as a screenshot of running JUnit with at least the two inputs above)
  > ![Image](lab_report_three_photos/nonfailure_inducing_test_no_terminal.JPG)
  > ![Image](lab_report_three_photos/failure_inducing_test_with_terminal.JPG)
- The bug, as the before-and-after code change required to fix it (as two code blocks in Markdown)
  > Before
  > > Original code
  ```
  static void reverseInPlace(int[] arr) {
    // old
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
  ```
  > After
  > > New Code:
  ```
  for(int i = 0; i < arr.length/2; i += 1) {
      int temp = arr[i];
      arr[i] = arr[arr.length - i - 1];
      arr[arr.length - i - 1] = temp;
  }
  ```
- Briefly describe why the fix addresses the issue
  - In the old or original method, there was an issue with the for loop, thus making it unable to handle any array that's longer than a length of 2. The for loop does iterate through the entire array, but the new assignment was incorrect as with each iteration, it overwrites the elements in the array with elements from the reversed position. So for example, with the failure-inducing input with the old code, the test, rather than seeing `{1,2}`, saw `{1, 1}`, hence why it's returning an error message that it was expecting [2] but saw [1] instead at index = 1. Because of this bud, the first test passed as it was only a length of 1, so the for loop coincidentally worked out for it, but once the length increased, a failure input was induced.


Part 2 - Researching Commands
--
Consider the commands less, find, and grep. Choose one of them. Online, find 4 interesting command-line options or alternate ways to use the command you chose. To find information about the commands, a simple Web search like “find command-line options” will probably give decent results. There is also a built-in command on many systems called man (short for “manual”) that displays information about commands; you can use man grep, for example, to see a long listing of information about how grep works. Also consider asking ChatGPT!

For example, we saw the -name option for find in class. For each of those options, give 2 examples of using it on files and directories from ./technical. Show each example as a code block that shows the command and its output, and write a sentence or two about what it’s doing and why it’s useful.

That makes 8 total examples, all focused on a single command. There should be two examples each for four different command-line options. Many commands like these have pretty sophisticated behavior possible – it can take years to be exposed to and learn all of the possible tricks and inner workings.

Along with each option/mode you show, cite your source for how you found out about it as a URL or a description of where you found it. See the syllabus on Academic Integrity and how to cite sources like ChatGPT for this class.

- Choose: find
1. Can find files of a specific type
   > General formatting of command: `find /path/to/directory -type f -name "*.txt"`
   >
   > With technical/, could use `find technical/ -type f -name "*.txt"` to find all the files that are txt files. It's looking through all the files (`-type f`) that are txt files (`-name "*.txt"`) in the technical/ directory. This can be particularly useful as this can be a separate way to find files that end with ".txt" rather than using grep to do so. The `| head -n 10` was added to the end to restrict the number of files listed, as there were a lot of files in technical/ that end with .txt, to just the first ten so that the image would be easier to capture.
   > ![Image](lab_report_three_photos/find_files_specific_type_1.JPG)
   >
   > With technical/, could use `find technical/ -type f -name "*.JPG"` to find all the files that are txt files. It's looking through all the files (-type f) that are JPG files (-name "*.JPG") in the technical/ directory. This can be particularly useful as this allows users to quickly determine the files that are pictures and can also be a separate way to find files that end with ".JPG" rather than using grep to do so.
   > ![Image](lab_report_three_photos/find_files_specific_type_2.JPG)
   > 
2. Can find files that are larger or smaller than a specific size
   > General formatting of command: `find /path/to/directory -type f -size (+/-)100M`
   >
   > With technical/, could use `find technical/ -type f -size +80k` to find all files (`-type f`) that are greater than 80 kilobytes (`-size +80k`). This can be particularly useful when one is building a potential software where the input is restricted by the file size given, so using this command line could be a quick way to find out which files are large or small enough to work for such software.  
   > ![Image](lab_report_three_photos/find_files_specific_size_1.JPG)
   >
   > With technical/, could use `find technical/ -type f -size -3k` to find all files (`-type f`) that are less than 3 kilobytes (`-size -3k`). This again can be particularly useful when one is building a potential software where the input is restricted by the file size given, so using this command line could be a quick way to find out which files are large or small enough to work for such software.  
   > ![Image](lab_report_three_photos/find_files_specific_size_2.JPG)
   > 
3. Can find files that were last modified in the last number of days or within a time period
   > General formatting of command: `find /path/to/directory -mtime -(number of days)` or `find /path/to/directory -type f -newermt "starting_date" ! -newermt "ending_date"`
   >
   > With technical/, could use `find technical/ -mtime -7 ` to find all the files that were modified in the last seven days (`-mtime -7`). This can be particularly useful if one wants to quickly access or know information about files that were most recently updated, resulting in potentially a change on their end with a code or some other software. The `| head -n 10` was added to the end to restrict the number of files listed, as there were a lot of files in technical/ that end with .txt, to just the first ten so that the image would be easier to capture.
   > ![Image](lab_report_three_photos/find_files_last_modified_1.JPG)
   >
   > With technical/, could use `find technical/ -type f -newermt "2024-01-10" ! -newermt "2024-02-10"` to find all the files (`-type f`) that were modified between 01/10/2024 and 02/10/2024 (`-newermt "2024-01-10" ! -newermt "2024-02-10"`). This can again be particularly useful if one wants to quickly access or know information about files that were updated during a specific period, resulting in potentially a change on their end with a code or some other software. The `| head -n 20` was added to the end to restrict the number of files listed, as there were a lot of files in technical/ that end with .txt, to just the first 20 so that the image would be easier to capture.
   > ![Image](lab_report_three_photos/find_files_last_modified_2.JPG)
   > 
4. Can find directories with a certain name
   > `find /path/to/directory -type d -name "dirname"`
   > ![Image](lab_report_three_photos/find_specific_directory_1.JPG)
   > ![Image](lab_report_three_photos/find_specific_directory_2.JPG)
