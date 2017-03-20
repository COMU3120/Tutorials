# Tutorial 2 - Data Cleaning

1. Download OpenRefine and Sublime Text
2. Learn RegEx
3. Use Sublime
4. Use RegEx in Sublime
5. Use OpenRefine
6. Use RegEx in OpenRefine

## Downloads

Download these in the background while you are completing the next tasks

### OpenRefine

#### Windows

- Download OpenRefine for Windows [here](https://github.com/OpenRefine/OpenRefine/releases/download/2.7-rc.2/openrefine-win-2.7-rc.2.zip)
- unzip, and double-click on *openrefine.exe*. If you’re 
  having issues with the above, try double-clicking on *refine.bat* instead.

#### macOS

- Download OpenRefine for macOS [here](https://github.com/OpenRefine/OpenRefine/releases/download/2.7-rc.2/openrefine-mac-2.7-rc.2.dmg)
- Open, drag icon into the Applications folder and double click on it.

### Sublime Text

#### Windows

- Download Sublime for Windows [here](https://download.sublimetext.com/Sublime%20Text%20Build%203126%20Setup.exe)
- Run the installer

#### macOS

- Download Sublime for macOS [here](https://download.sublimetext.com/Sublime%20Text%20Build%203126.dmg)
- Drag Sublime into your applications

## Regular Expressions tutorial

Complete the RegEx tutorial here: https://regexone.com/

You can refer to http://www.regular-expressions.info/tutorial.html for more detailed information about regular expressions

You can practice your regular expressions here: https://regexr.com

## Download the project files

- Download the zip file [here](https://github.com/COMU3120/Tutorials/raw/master/files/tut2.zip)
- Extract it into a new folder on your Desktop
- Open the folder in Sublime


## Sublime RegEx tasks

After each task has been completed check that your solution is correct by comparing it with the answer file

1. In `file1.csv` remove all the instances of the character `.` 
2. In `file2.csv` replace all the instances of the character `.` with `-`
3. In `file3.csv` find all the upper-case text, and make it lower case
   1. Make sure your search is case-sensitive
   2. Try looking in the command palette
      1. **macOS** `⌘ + ⇧ + P`
      2. **Windows** `Ctrl + ⇧ + P`
4. In `file4.csv` replace all instances of the words `one`, `two`, and `three` with the numbers `1`, `2`, and `3` respectively
5. In `file5.csv` replace all the repeating instances of `a` with a single `a`

## OpenRefine

- Watch the introduction video here: http://www.youtube.com/watch?v=B70J_H_zAWM
- Download some data from Reaper. If you are having issues, download the sample file [here](files/reaper_sample.csv)
- Create a new project and import the file from Reaper
- Make some changes to the file
- Export the file as a csv

## OpenRefine tasks

1. In `file6.csv` trim the whitespace in the first column and capitalise the second

   1. Look in the `Common Transformations` menu

2. In `file7.csv` split the created date into `created_year` `created_month` `created_day` and `created_time`

   1. Look in the `Edit Column` menu

3. In `file8.csv` split all the urls into a new column using this code:

   1. ```python
      import re
      if value != None:
      	return ",".join(re.findall('http[s]?://(?:[a-zA-Z]|[0-9]|[$-_@.&+]|[!*\(\),]|(?:%[0-9a-fA-F][0-9a-fA-F]))+', value))
      ```

   2. Use `Add column based on this column`

   3. Change the language to `Python / Jython`

4. In `file9.csv` split all the hashtags into a new column using this code:

   1. ```python
      import re
      if value != None:
          return ",".join(re.findall(r"#(?:\[[^\]]+\]|\S+)", value))
      ```

   2. Use `Add column based on this column`

   3. Change the language to `Python / Jython`

5. In `file10.csv` fix the formatting issues in Sublime text, import it into OpenRefine



