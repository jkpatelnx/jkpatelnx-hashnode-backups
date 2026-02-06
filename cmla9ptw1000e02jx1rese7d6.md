---
title: "Linux File Read and Write Explained: cat, head, tail, tee, and Redirection"
seoTitle: "Linux File Commands: cat, head, tail, and more"
seoDescription: "Learn how to read and write to files in Linux using essential commands: cat, head, tail, tee, and redirection. Beginner-friendly guide"
datePublished: Fri Feb 06 2026 02:30:22 GMT+0000 (Coordinated Universal Time)
cuid: cmla9ptw1000e02jx1rese7d6
slug: linux-file-read-and-write-explained-cat-head-tail-tee-and-redirection
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1770339442634/dda542c5-5042-4b15-b48f-ffc51e917868.png
tags: linux, linux-for-beginners, linux-basics, linux-commands

---

If you are learning Linux, understanding how to read from and write to files using the terminal is a must-have skill. Configuration files, logs, scripts, and application data all depend on file operations. Before using editors like `vi` or `nano`, you should be comfortable with basic shell commands that handle files directly.

In this practice-based article, the focus is on basic file read and write operations, including single-line and multi-line text writing, using only fundamental Linux commands. This approach is beginner-friendly and highly useful for DevOps learners, cloud engineers, and Linux certification preparation.

Practice Objective
* Today’s goal is to create a simple text file and practice:  
* Creating a file
* Writing text to a file (single line)
* Writing multiple lines to a file
* Appending new content
* Reading the full file
* Reading partial content using head and tail
* Using tee to write and display output simultaneously We will use a file named notes.txt and keep the total number of lines between 8 and 12 for clarity.
    

---

### Step 1: Create the File
First, create an empty file using the touch command. 
`touch notes.txt` 
This creates the file without adding any content.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1770338161816/50b18ff3-34b9-4f0b-b8ea-8fd0f1e0b47d.png align="center")

### Step 2: Writing Text to a File (Single Line)
To write text into a file, Linux uses output redirection with the `>` operator. This writes content and overwrites anything already present in the file. 
`echo "This is line one written using redirection" > notes.txt` 
After this command, notes.txt contains one line.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1770338251737/577274b2-0155-43ae-8928-84c5ae4dbfce.png align="center")

### Step 3: Writing Multiple Lines to a File
You can also write multiple lines at once using a here-document (`<<`). This is useful when adding blocks of text without opening an editor. 
`cat << EOF >> notes.txt`
`This is line two`
`This is line three`
`This is line four`
` written as multiline input`
`EOF` 
All these lines are appended to the file in one operation.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1770338366261/9818d67d-ce4f-4813-b75b-5c330ecb0fdc.png align="center")

### Step 4: Appending a Single Line
To add another line without overwriting existing content, use the append operator `>>`. 
`echo "This line is appended using >> operator" >> notes.txt` 
Appending is commonly used in log files and automation scripts.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1770338469071/5eb9f78d-e0e7-4877-8613-5a831e7d4a11.png align="center")

### Step 5: Writing and Displaying Output Using tee
The `tee` command allows you to write to a file and display the output on the terminal at the same time.
`echo "This line is added using tee command" | tee -a notes.txt` 
The `-a` flag ensures the content is appended.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1770338557600/9b65cbcf-eeca-4272-8217-4706abe03475.png align="center")

### Step 6: Read the Entire File
To display the full content of the file, use the cat command. 
`cat notes.txt` 
This prints all lines in the file from top to bottom.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1770338664588/535d7c20-c8f0-4b9e-9936-3754eb8c0ea1.png align="center")

### Step 7: Read the First Few Lines
The head command is useful when you want to preview the beginning of a file. 
`head -n 2 notes.txt` 
This shows only the first two lines.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1770338952704/255da339-3083-4d3d-867b-3031b1dad053.png align="center")

### Step 8: Read the Last Few Lines
The `tail` command displays the last part of a file and is often used for checking recent logs. 
`tail -n 2 notes.txt` 
This prints the last two lines from notes.txt.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1770339033970/1b90f3a1-53ed-44e3-bb4f-7f54d0836930.png align="center")