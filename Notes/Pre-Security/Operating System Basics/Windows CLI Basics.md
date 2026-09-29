[Windows CLI Basics.md](https://github.com/user-attachments/files/32807391/Windows.CLI.Basics.md)
## **A Quick Recap About the Terminal**

Before we begin exploring, let's take a moment to familiarize ourselves with the tool we're using.

The **terminal** is a text-based interface for interacting with the Windows OS. Instead of clicking windows and folders, you type commands that tell the computer exactly what to do. cyber security professionals use it because:

- It's faster than clicking around
- It gives more control
- Many security tools only run in the terminal

## **TASK-1: Windows CLI: Navigating Fies and Finding Your First File**

**Step 1: Where Am I?**

## **Overview**

Before you can explore anything on a Windows system, you need to know how to move around and look for files using the command line. In this task, you'll learn how to explore folders, move between directories, search for a file when you don't know where it is, and read the contents of a text file, all using **Command Prompt**.

These are the same kinds of skills you'll use later when troubleshooting systems.

### **Task: Find the mission_brief.txt file**

Your boss has left you another note, with a task to find the task_brief.txt file:

> _"I've left a file called **task_brief.txt** somewhere in your user folder.You'll need to find it using the command line and read what it says."_

You're only given the **name of the file**, not its location.

Let's explore how to navigate through the Windows filesystem using the command line and how to locate a file without knowing its actual location.

Step 1: Where Am I?

Before doing anything else, open the terminal on the Desktop, and check your current location by typing the command `cd`, as shown below:

![Shows output of cd command](https://tryhackme-images.s3.amazonaws.com/user-uploads/5e8dd9a4a45e18443162feab/room-content/5e8dd9a4a45e18443162feab-1767568026270.png)

This shows the full path of the directory you're currently in. On Windows, this is usually your **user folder**. Please note that the `cd` command is also used to change the directory, which we will use later in the task.

## **Step 2: What's Around Me?**

Now, list the contents of the current directory using the command: `dir`

This command will list down the files and the folders present in the current directory, as shown below:

![Shows output of dir command](https://tryhackme-images.s3.amazonaws.com/user-uploads/5e8dd9a4a45e18443162feab/room-content/5e8dd9a4a45e18443162feab-1767568027687.png)

You'll see files and folders that are visible by default. Take a moment to look around; not everything you need will always be obvious. From the output, we can see that the command has returned 16 directories.

## **Step 3: Are There Hidden Files?**

Some files and folders on Windows are marked as hidden, which means they don't appear in a normal listing. To show everything, including hidden items, run: `dir /a`

![Shows output of dir/a command](https://tryhackme-images.s3.amazonaws.com/user-uploads/5e8dd9a4a45e18443162feab/room-content/5e8dd9a4a45e18443162feab-1770670365538.png)

The output clearly indicates that more than 12 hidden folders were found. It is important to note that hidden doesn't mean secret; it just means Windows hides them by default.

### **Step 4: Moving Around the Filesystem**

Let's use the `cd` command to navigate through the folders. We can use the format `cd folder_name` to move to the specified folder. The command `cd Documents` will move us to the Documents folder, as shown below. To move back one level, we can use `the cd command`.

![Shows the output of cd command](https://tryhackme-images.s3.amazonaws.com/user-uploads/5e8dd9a4a45e18443162feab/room-content/5e8dd9a4a45e18443162feab-1767568026785.png)

To become familiar with the environment, use the `dir` or `dir /a` command to move to see what's inside each folder. You can explore a few folders to get comfortable, but the file you're looking for probably isn't in an obvious place.

### **Step 5: Finding the File on the Disk**

Instead of guessing where the file is, let Windows search for it. Use the following command: `dir /s task_brief.txt`. The `/s` flag tells Windows to search **all subfolders** starting from your current directory and show you the full path if the file exists.

![Shows the command to search for the files on the system](https://tryhackme-images.s3.amazonaws.com/user-uploads/5e8dd9a4a45e18443162feab/room-content/5e8dd9a4a45e18443162feab-1767876516240.png)

As we can see, the command above helped us locate the file and provided its full path. Take note of the path shown in the output.

### **Step 6: Navigate to the File**

Now that we know where the file is located, let's use the cd command to navigate to the folder using the command format `cd <path_to_the task_brief.txt>`. Use `dir` again to confirm that **task_brief.txt** is in the folder, as shown below:

![Shows output of the cd command](https://tryhackme-images.s3.amazonaws.com/user-uploads/5e8dd9a4a45e18443162feab/room-content/5e8dd9a4a45e18443162feab-1767876516174.png)

### **Step 7: Read the File**

Now read the contents of the file using: `type task_brief.txt`. This will print the contents of the file directly in the command prompt, as shown below:

![Shows the use of type command to read the file content](https://tryhackme-images.s3.amazonaws.com/user-uploads/5e8dd9a4a45e18443162feab/room-content/5e8dd9a4a45e18443162feab-1767568990065.png)

Perfect.

### **TASK-2: Gathering System Information on Windows**

**Overview**

Now that you know how to move around and find files using the Windows command line, it’s time to learn how to **ask the system questions about itself**. cyber security and IT professionals do this all the time. Before fixing a problem or investigating an incident, they first want to know:

- Who am I logged in as?
    
- What machine is this?
    
- What version of Windows is it running?
    
- How is it connected to the network?
    
    ![Image depicts a system under observation|78](https://tryhackme-images.s3.amazonaws.com/user-uploads/5e8dd9a4a45e18443162feab/room-content/5e8dd9a4a45e18443162feab-1770380933656.png)
    

In this task, you'll learn how to gather that information step by step.

## **Step 1: Who Am I Logged In As?**

When working on a system, one of the first things to check is **which user account you’re using**. This matters because different users can have different permissions.

Run the following command:`whoami`. This command prints the username of the account you’re currently logged into.

![Shows output of whoami](https://tryhackme-images.s3.amazonaws.com/user-uploads/5e8dd9a4a45e18443162feab/room-content/5e8dd9a4a45e18443162feab-1767570764040.png)

## **Step 2: What Is the Name of This Computer?**

Every Windows machine has a name. In workplaces, this helps identify network systems. To see the computer’s name, run: `hostname`.

![](https://tryhackme-images.s3.amazonaws.com/user-uploads/5e8dd9a4a45e18443162feab/room-content/5e8dd9a4a45e18443162feab-1767570764023.png)

You’ll see a short name printed in the terminal.

## **Step 3: What Version of Windows Is This?**

Next, let’s look at details about the operating system itself. Run:`systeminfo`

This command prints a lot of information. Don’t worry, you’re **not expected to understand everything** yet.

![](https://tryhackme-images.s3.amazonaws.com/user-uploads/5e8dd9a4a45e18443162feab/room-content/5e8dd9a4a45e18443162feab-1767570763969.png)

Focus on these parts:

- OS Name
- OS Version
- System Type

These details indicate the version of Windows the machine is running and whether it’s 32-bit or 64-bit.

## **Step 4: How Is This Machine Connected to the Network?**

Finally, let’s look at basic network information. Run: `ipconfig`

This shows the machine's network configuration.

Look for:

- An **IPv4 Address**
- A **Default Gateway**

![](https://tryhackme-images.s3.amazonaws.com/user-uploads/5e8dd9a4a45e18443162feab/room-content/5e8dd9a4a45e18443162feab-1767570763938.png)

This information helps analysts understand how a machine connects to the network.
