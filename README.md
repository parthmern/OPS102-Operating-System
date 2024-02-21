# OPS102-Operating-System


## Why OS is needed ?
- If my system has not any OS then just think about the scenario like - when you launch the tiktok app that time it takes the permission of direct accessing the CPU, memory, GPU, disk.So it can hack your system if there is not any layer between the app and hardware parts to communicate.
- Also, tiktok is using 90% CPU,80% memory here so i am not able to play PUBG game because there is not running space for it.
-  The example of running TikTok on a device illustrates the basic hardware components required (CPU, memory, GPU, disk) and the need for resource management.
-  OS prevents one application (like TikTok) from monopolizing all resources by implementing resource management, allocating specific percentages of resources to different applications.
-  like **INTERFACE** - interface is like a bridge between two things that need to work together here app and hardware
<br/>

- **Application software** performs specific task for the user.like email,,game  
- **System software** operates and controls the computer system and provides a platform to run application software.like windows,ios

## OS - operates the system
- An operating system is a piece of software that manages all the resources of a computer system,both hardware and software, and provides an environment in which the user can execute his/her programs in a convenient and efficient manner by hiding underlying complexity of the hardware and acting as a resource manager.
- Collection of system softwares
- ![image](https://github.com/parthmern/OPS102-Operating-System/assets/125397720/b6225ab7-9fdb-42c5-90f7-a0395d5b412f)

### Types of OS 
- [Pdf](https://drive.google.com/file/d/1EHE-nnTHMQzQP7xGRQo2g7cPpEGlq7q1/view)

## what does OS do
### hardware abstraction
- hardware means os can access hardware + abstraction means hiding
- middleman between your computer's hardware and the software you use
- Hides the underlying complexity of the hardware. (Aka, Abstraction)
- OS hide the details of hardware like memory,gpu,cpu,usb,blutooth,screen,keyboard from the application software
- ex. here application software can get input from keyboard without knowing how it is connected so apps have no information about hardware
- ex. apps can send data through internet for api calling here apps have no idea that internet is conencted with ethernet, wifi, 5g-4g connection

### Resource Management - Arbitration
- (memory, device, file, security, process etc)
- Without an OS, developers would need to manage memory and resource allocation manually, leading to redundant code and bulkier applications.
- OS prevents one application (like TikTok) from monopolizing all resources by implementing resource management, allocating specific percentages of resources to different applications.
- The example of running TikTok on a device illustrates the basic hardware components required (CPU, memory, GPU, disk) and the need for resource management.
- OS have some number of resources like CPU, memory, GPU, disk, network bandwidth, peripheral devices include keyboards, mice, printers, scanners, external hard drives, webcams, and monitors ( input / output performing devices) so allocating this resources in such manner that there may be no conflict

- Let's consider a simple example of resource management in a multitasking operating system. Imagine a computer with a single CPU and two running programs: Program A and Program B. Both programs need to access a shared printer to print their respective documents.
  - Program A starts executing and requests access to the printer.
  - The operating system grants access to the printer to Program A, allowing it to print its document.
  - While Program A is printing, Program B starts executing and also requests access to the printer.
  - The operating system denies access to the printer for Program B because it's currently in use by Program A. Program B is placed in a waiting state until the printer becomes available.
  - **Resource Release / waiting process** Once Program A finishes printing, it releases the printer resource.
  - The operating system then grants access to the printer to Program B, allowing it to print its document.
  - using *alogorithms to do make resource management easy*

    - **Dead Lock / Contension** - when 2 or more porgramms runs after / needs same resources
    - Deadlock can occur in resource management when two or more processes are unable to proceed because each is waiting for a resource held by the other
    - In our example, deadlock could occur if Program A had requested access to both the printer and another resource (such as disk space) that Program B was holding, while Program B simultaneously requested access to the printer and the resource held by Program A.
    - ![deadlock](https://github.com/parthmern/OPS102-Operating-System/assets/125397720/4e532edd-c360-4593-af46-fdeef38a38f8)
    - Deadlock can lead to a situation where none of the processes can make progress, causing the system to become unresponsive. To prevent deadlock, operating systems often use techniques such as resource allocation strategies, deadlock detection, and deadlock recovery mechanisms.

<br/>

- ex. **Memory Management**- ensuring that each program has their own memory so they donot crash eachother (% of memory allocation like above tiktok example)
- preventing multiple programs like P1, P2, P3 to sending the constantly output on same device like R1.
<br/>

- avoidance of Thrashing/Excessive Paging and Swapping - research about it

### Security enforcement
- facilitates execution of application programs by providing isolation and protection.
- even both program is running at same time so provide isolation
- Security Checks: If Instagram tries to access your banking data, the operating system's security guard checks its credentials. Since Instagram doesn't have permission, it's denied access.


### Maintaining Programming Modal
- OS maintains the programming model by using hardware virtual memory to load multiple programs into different physical memory locations while still preserving the illusion that each program operates in the same memory region it expects.
- **VIRTUAL MEMEORY**
   - it creates illusion to the programmer that programs of larger size than primarymemory can be executed. It is not existed actually It is a part of the secondary storage that gives the user the illusion that it is a part of the main memory.
   - one feature in OS where large program can store themeselves in form of pages and while thier execution only required pages/portion are located into main memeory. - [hindi exp](https://youtu.be/sRUq_uaZ5f0?si=GMBUq_QolE5LZA1r)
   - it is implemented by demand paging and demand segmentation process.
   - *Demand Pageing with what is swapping*- [hindi expl](https://youtu.be/8HZGh7S1lJo?si=ys4iIvehKsG7xXfH)
   - ![maxresdefault](https://github.com/parthmern/OPS102-Operating-System/assets/125397720/83134776-4c73-465a-ae33-d02c2de084b9)
   - *Demand segementation*- 
  

## Components of OS

### Kernal
- heart of OS
- interects with hardware
- Very first part of OS to load on start-up.
- kernal is directed connected with hardware
- 
![what-is-kernel](https://github.com/parthmern/OPS102-Operating-System/assets/125397720/3760ff56-3847-4b0e-ba18-666ae25295b6)

- process management - process creation,termination, processes communication
- memory management - how to allocate and deallocate memory in RAM, free space management,
- file management - create file, delete, helps to maanage file in TREE strcuture
- I/O management - controlling all input and output devices

### User space / user interface
- Where application software runs, apps don’t have privileged access to the underlying hardware. It interacts with kernel.
- Enables user interaction with the system.
- no hardware access
- Text-based UI / command line (TUI/CLI): Allows command entry and text-based interaction.
- Graphical UI (GUI): Facilitates interaction through graphical elements.
- internally GUI executing the commads same to CLI to perform particular task
- 
- GUls are well-suited to graphical tasks, such as editing images and documents. However, they may require excessive repetitive actions in some situations.
- CLIs are well-suited to automation, such as mass-conversion of thousands of images. However, they're not well suited to occasional tasks.
- GUls require far more data than CLIs. A typical CLI display contains about 2 kilobytes of data; a typical HD GUI display contains about 6 megabytes (6000 kilobytes) of data. Therefore, CLIs are often used over remote connections.
- A text user interface (TUI) utilizes the same display technology as a CLI but presents a full-screen interface instead of scrolling command-and-response output.

### System Libraries
- its like function that performs similar task all time
- Common set of software tasks for operations like screen drawing, network access, playing sound
- helps to elemenate the duplication of code
- others libraries may be installed externally but the system libraries provided by the OS which reqired by every programs to work

### Services
- Programs running continuously in the background, providing various services.
- Example: WiFi authentication, print management, file sharing, blutooth
- Operate without full system privilege.

### utilities and applications
- Utilities = Tools provided by the operating system for setup, configuration, and maintenance tasks, Can be accessed through GUI or CLI, GUI Utilities:- Disk Management tool (Windows), System Preferences (MacOS), CLI Utilities:- ls (list files and directories), grep (search text), chmod (change file permissions).
- Applications = Basic starter programs provided by the operating system, Include text editors, clocks, games, and sometimes web browsers like notepad, internet explorer, firefox, clockapp

## Hsitory
- In the early days of computing, standardization was impossible due to unique, one-of-a-kind computers. Modern operating system concepts trace back to Multics, developed at MIT from 1965. Bell Labs, initially involved in Multics, withdrew early. Two Bell employees, Dennis Ritchie and Ken Thompson, later developed Unix, incorporating similar concepts from Multics.
- **UNIX** = Unix was first made for one type of computer, but later changed so it could work on many different types. It became popular with different computer companies because it meant they didn't have to make their own operating systems. Unix was also liked by schools because they could look at the code. Microsoft got a version of Unix called Xenix for small computers.
- **CP/M** =, originally the Control Program/Monitor, later renamed Control Program for Microcomputers, was another popular operating system. When IBM entered the microcomputer market in 1981, it hired Microsoft to provide an operating system. Microsoft licensed and later bought 86-DOS from another company, renaming it PC-DOS for IBM and MS-DOS for direct sale from Microsoft. These systems were heavily influenced by CP/M in design and structure. Unlike Unix, DOS was single-tasking and lacked a hierarchical filesystem for organizing files into nested folders or directories.
- **Operating systems started getting graphical user interfaces (GUIs)** = Unix systems got GUIs in 1984 with the introduction of the X Window System from MIT. DOS got multitasking and a GUI with the release of Windows 1.0 in 1985.Windows NT 3.1, released in 1993, was a new 32-bit operating system that combined features from DOS/Windows and a jointly-developed Microsoft-IBM operating system named OS/2. Even though it wasn't based on DOS, it could still run DOS programs and maintain compatibility with DOS commands. All modern versions of Windows are built on Windows NT.
- **Unix transformed from a proprietary product of Bell Labs/AT&T into a family of related operating systems customized by different vendors** = Initially proprietary, Unix later branched out into various versions sold under different names such as XENIX, AIX, Ultrix, HP/UX, among others.Standard bodies like IEEE, The Open Group, and ISO defined standards for "Unix-like" operating systems, specifying their components and operations.Unix evolved into a trademark rather than a single product. Operating systems conforming to Unix standards gained permission to use the Unix trademark.
- **The Post-Unix World** = In today's computing, while Unix's trademark has lost significance, numerous operating systems are Unix-like, yet few have undergone official conformance testing.

## ssh
- SSH stands for *Secure Shell*. It's a network protocol that allows you to securely connect to another computer over an unsecured network, such as the internet.
- Imagine you have two computers, a local one (your computer) and a remote one (a server, for example). SSH lets you *log into the remote computer and control it* as if you were sitting right in front of it.
- It *encrypts* the data being transmitted, so even if someone intercepts it, they can't understand what's being sent. This makes SSH a safe way to communicate and work on remote computers without worrying about unauthorized access or data interception.
- softwares that support ssh protocol - OpenSSH, PuTTY, WinSCP, FileZilla
  
<br/>

### **Linux terminal at start**

- ![image](https://github.com/parthmern/OPS102-Operating-System/assets/125397720/65818fc2-1a4d-46a4-bb1b-5b0c88dba67d)

  - username: This is the username of the user who is currently logged in.
   - servername: This is the local name or server name of the machine.
   - ~: This symbol represents the home directory (e.g., /home/username in Linux). Every user has a "home" directory created for them when they receive an account.
   - $: The dollar sign indicates that you are a normal user. If the prompt has a "#" symbol, it means the user is an administrator (root).

### **windows terminal at start**
- ![image](https://github.com/parthmern/OPS102-Operating-System/assets/125397720/2a222170-1e19-41bf-9cfd-2586c65c1527)
    - C:\Users\username: In Windows, this indicates the current directory, which is the user's home folder.

### basic commads

| Windows  | Linux  | Description                                  | Example                    |
|----------|--------|----------------------------------------------|----------------------------|
| `clear`  | `cls`  | Clears the terminal screen.                 | `clear`                    |
| `echo`   | `echo` | Print something on the screen.              | `echo Hello, world!`       |
|          | `cal`  | Display calendar.                           | `cal`                      |
| `date`   | `date` | Shows date and time. Equivalent to `date /t` and `time /t` in Windows. | `date`             |
| `whoami` | `whoami` | Prints Information about current logged-in user. | `whoami`               |
| `cls`    |        | Clears the terminal screen.                 | `cls`                      |
| `tree`   | `tree` | Shows the folder hierarchy in tree format.  | `tree`                     |

## File System
- A file system organizes and retrieves files efficiently from a storage medium such as a hard disk.
- Both Linux and Windows utilize hierarchical file systems.
- Files are organized in folders and subfolders.
- In command-line interfaces, folders are referred to as directories.
- In Windows, the file system hierarchy starts from drives like C, D, etc., whereas Linux has a root directory (/) from which all files and directories stem.

### Files and Folders:
- Virtually everything in modern computer systems is either a file or a folder.
- Folders act as containers that can hold files and other folders (sub-folders).
- Examples of common folders include Home, Desktop, and Root.
- Files store user data and can be of various types, such as Word documents, Excel sheets, and PowerPoint presentations.

### File Types and Extensions:
- File types are identified by their extensions, typically the 3 or 4 characters after a dot.
- Examples of file extensions include docx (Word documents), exe (executable programs), and txt (text files).
- Each file type requires a specific program or application to open it.
- Not having the required program for a file type can result in the inability to open the file properly.

### File Naming Conventions:
- File names should be meaningful and consistent.
- Unix/Linux file systems are case-sensitive, while Windows is not.
- Avoid non-alphanumeric characters in file names, as they may have special meanings to the system.
- Spaces in file names should be avoided; consider using periods, hyphens, or underscores instead.

### Linux Hierarchical File System:

![linux-filesystem-hierarchy](https://github.com/parthmern/OPS102-Operating-System/assets/125397720/97d35010-a5f0-4a28-ac6a-3843a926f170)

| Directory Path  | Purpose                                              |
|-----------------|------------------------------------------------------|
| /               | Root, top of file system hierarchy                   |
| /bin            | executable files, Common system binaries (commands)                    |
| /home           | Used to store users' home directories                |
| /usr            | This is called User, where user-related programs live|
| /usr/bin        | Common utilities (commands) for users                |
| /usr/sbin       | Common utilities for system administration           |
| /etc            | System configuration files (e.g., passwd)            |
| /var            | Dynamic files (log and mail files)                   |
| /tmp, /var/tmp  | Temporary files for programs                         |
| /dev            | Device driver files (terminals, printers, etc)       |
| /opt            | User-installed application programs                  |


### Paths
- A path specifies the location of a file or directory in the file system.
- It follows the directory tree hierarchy to point to a specific file system location.
- In Linux, directories are separated by forward slashes ` / `
- Windows, backslashes ` \ `

### path travelling
- [absolute and replative paths- imp video](https://youtu.be/ephId3mYu9o?si=4-TbFCThjPo43NHJ)

| Linux Command       | Description                                      | Windows Command                 | Description                                     |
|---------------------|--------------------------------------------------|---------------------------------|-------------------------------------------------|
| `cd /bin`           | Change directory to /bin.                        | `cd D:\Courses\OPS102`          | Change directory to D:\Courses\OPS102.         |
| `cd ~`              | Change directory to the user's home directory.  | `cd C:\Users`                   | Change directory to the C:\Users directory, equivalent to /home in Linux. |
| `cd ..`             | Change directory to the parent directory.        | `cd ..`                         | Change directory to the parent directory.       |
| `cd ./`             | Change directory to the current directory.      | `cd .\`                         | Change directory to the current directory.     |
| `cd /`              | Change directory to the root directory.         | `cd \`                          | Change directory to the root directory.        |

### listing content of dir
| Linux Command | Description                                  | Windows Command | Description                                    |
|---------------|----------------------------------------------|-----------------|------------------------------------------------|
| `ls`          | List the contents of the current directory. | `dir`           | List the contents of the current directory.   |
| `ls /bin`     | List the contents of the `/bin` directory.  | `dir D:\`       | List the contents of the `D` drive.           |

### `ls -l` or `ll` in linux where first charater
- ![image](https://github.com/parthmern/OPS102-Operating-System/assets/125397720/d0d4b86c-9f30-4a4a-9695-4847bff0ecf2)


| Character | Type           | Description                                        |
|-----------|----------------|----------------------------------------------------|
| -         | Regular File   | A regular file.                                    |
| b or c    | Device File    | A block or character device file.                  |
| d         | Directory      | A directory.                                       |
| l         | Symbolic Link  | A symbolic link.                                   |
| p         | Named Pipe     | A pipe for inter-process communication.           |
| s         | Socket         | A socket for network communication.                |


## commands

| Linux Command | Windows Command | Description                                 | Example                                      |
|---------------|-----------------|---------------------------------------------|----------------------------------------------|
| `mkdir`       | `mkdir`         | Create directories                         | `mkdir myfolder`                             |
| `mv`          | `move`          | Move/Rename files/directories              | `mv file.txt folder/`, `move file.txt folder/` |
| `cp`          | `copy`          | Create a copy of the file/directory        | `cp file.txt file_copy.txt`, `copy file.txt file_copy.txt` |
| `rm`          | `del`           | Remove the file/directory                  | `rm file.txt`, `del file.txt`                |
| `rmdir`       | `rd`         | Remove empty directory                     | `rmdir myfolder`                             |
| `touch`       | No equivalent   | Create an empty file/Change the timestamp of the file | `touch myfile.txt` |
| `ls`          | `dir`           | List directory contents                    | `ls`, `dir`                                  |

## working with text files

| Command | Usage | Example |
|---------|-------|---------|
| `cat`   | Display the contents of a file all at once on the screen. | `cat mytext.txt` |
| `more`, `less` | Display the contents of a file one screen at a time. | `more bigfile.txt`, `less bigfile.txt` |
| `head`, `tail` | Display the beginning or end of a file. | `head -n 5 numbers.txt`, `tail -n 3 numbers.txt` |
| `cut`   | Remove undesired columns from your data in a file. | `cut -d',' -f1,2 data.csv` |
| `sort`  | Sort the lines of a file. | `sort unsorted.txt` |
| `diff`  | Find the differences between two files. | `diff file1.txt file2.txt` |
| `file`  | Determine the type of a file. | `file myfile.jpg` |
| `uniq`  | Display identical consecutive lines only once. | `uniq repeated.txt` |
| `find`  | Find files matching specific criteria in the filesystem. | `find . -name "*.txt"` |
| `grep`  | Find specific lines in a file. | `grep "orange" mytext.txt` |
| `tr`    | Translate or replace the occurrences of characters. | `echo "hello" \| tr '[:lower:]' '[:upper:]'` |
| `wc` | represent number of lines,words, characters| `wc fileName.txt` |

![image](https://github.com/parthmern/OPS102-Operating-System/assets/125397720/38f48f45-b1d4-4d6b-b9f4-cd042f3a08bc)


<br/>

![image](https://github.com/parthmern/OPS102-Operating-System/assets/125397720/8f5a198e-ed9e-44e4-9c5c-dce93258de71)
![image](https://github.com/parthmern/OPS102-Operating-System/assets/125397720/62214794-c3f7-41c2-a392-e796341683d5)


<br/>

![image](https://github.com/parthmern/OPS102-Operating-System/assets/125397720/9e3c9820-e158-45c6-af59-bd9028cbb6ec)

<br/>

![image](https://github.com/parthmern/OPS102-Operating-System/assets/125397720/521e698f-a1f4-4327-aa17-220cdc3234de)

<br/>

![image](https://github.com/parthmern/OPS102-Operating-System/assets/125397720/631305d8-4107-4eb4-a26f-e33f7fe2fb18)

- Sort sample.txt for the sorting according to 1 to 9 and then a to z ⇒ it is risky bcz it changed the original file so be careful 
- To solve this we have to use REDIRECTION >
- Sort sample.txt > sample-sorted.txt
- It creates new file . It can also override if file name is same

- `>>` ⇒ used for append at the bottom
- Echo “test” > sample.txt   ⇒ it overrights the file with text of “test”


<br/>

![image](https://github.com/parthmern/OPS102-Operating-System/assets/125397720/8e206f7d-be83-4bdb-8540-3cbf3918e34c)

<br/>

![image](https://github.com/parthmern/OPS102-Operating-System/assets/125397720/ac375a25-d0a3-4bc3-8b4c-51019ed4a201)

<br/>

![image](https://github.com/parthmern/OPS102-Operating-System/assets/125397720/2b467f5a-0490-49d5-9a3b-7c248249fc13)

<br/>

![image](https://github.com/parthmern/OPS102-Operating-System/assets/125397720/f4d55331-0529-4f2d-bb76-b892e735d629)

<br/>

![image](https://github.com/parthmern/OPS102-Operating-System/assets/125397720/19587833-6039-4943-b827-62d1f289736a)

<br/>

![image](https://github.com/parthmern/OPS102-Operating-System/assets/125397720/d98549d4-566e-42ca-b008-0db7a62aa482)

<br/>

![image](https://github.com/parthmern/OPS102-Operating-System/assets/125397720/f933fae0-645c-4d2f-8e1b-cb9f1e0cd91a)

### Text Editors:
- Text editors are essential tools that allow users to create, modify, and save editing changes of text files.
- They are commonly used for various tasks such as editing system configuration files, writing scripts and programs, editing documentation, and developing web pages.
- Proficiency in using a text editor is crucial for installing, configuring, and running network services.
- there are many some for windows and some for linux here is ex. VIM, Nano, Gedit, Notepad, Notepad++, Sublime Text
- **NANO** = `nano fileName.txt`  
- Nano commands typically consist of the ^ symbol, representing the <ctrl> key, followed by another character (command).
- Basic Nano commands include:
  - ^G - Get help at any time
  - ^R - Open a file
  - ^O - Save a file
  - ^W - Find
  - ^\ - Replace
  - ^X - Exit

## File Globbing: Wild Cards
- Definition: File globbing is a feature provided by shells (like Bash) that allows users to use special characters called wildcards to represent multiple filenames with a single expression.
- Wildcards: Wildcards are symbols with special meanings and can be used to substitute for one or more characters in filenames.
  
| Wildcard          | Description                                         | Example                  |
|-------------------|-----------------------------------------------------|--------------------------|
| `*` (star)        | Represents zero or more characters.                 | `*.txt` matches all files with a `.txt` extension. |
| `?` (question mark) | Represents any single character.                    | `image?.jpg` matches `image1.jpg`, `image2.jpg`, etc. |
| `[]` (square brackets) | Represents one character from a list given in brackets. | `file[1-3].txt` matches `file1.txt`, `file2.txt`, or `file3.txt`. |

- These wildcards are used for pattern matching in Bash commands like ls, cp, mv, etc., allowing users to select specific files based on their names.

## File permissions
- In multi-user operating systems it is very important to be able to allow who has access to files and folders.
- This is achieved by setting permissions of files and folders. All modern operating systems provide ways to set such permissions.
- Linux provides elaborate command options for setting permissions. 
- file permissions are represented by a series of characters or bits, and they define the access rights for the owner of the file, the group associated with the file, and others. 
- `ls -l` or `ll` to see the file permission and other details

![image](https://github.com/parthmern/OPS102-Operating-System/assets/125397720/714c65e6-6c84-4c75-ac7d-9e45f90ba0c2)

- `RWX` - means read,write,xcecute permission - highest permission
- `R--`   - means read, no write permission , no execution permission
- `- - -`    - means no thing can do - lowest permission

| Permission | Symbol | Description                                                                                  |
|------------|--------|----------------------------------------------------------------------------------------------|
| Read       |   r    | Grants permission to access the file's contents, but not to edit it or execute it.            |
| Write      |   w    | Grants permission to edit the file's contents. Write permission is only effective with read permission. |
| Execute    |   x    | Allows the execution of the file as a program. Effective only if granted with read permission. |
| Special (setuid, setgid, sticky) |   s    | Special permissions in certain cases, such as setuid, setgid, or sticky bit. (Details explained below.) |

### Folder/directory permission
| Permission | Symbol | Description                                                                                                      |
|------------|--------|------------------------------------------------------------------------------------------------------------------|
| Read       |   r    | Grants permission to read the contents of the directory, allowing listing of all files and subdirectories.      |
| Write      |   w    | Grants permission to change/edit the contents of the directory, including creating, deleting, copying, and renaming subdirectories and files. |
| Execute    |   x    | Grants permission to set the directory as the current working directory (allows users to use `cd` command) and access metadata for entries. Also known as "pass through" permission. |

### how to change permissions?

![image](https://github.com/parthmern/OPS102-Operating-System/assets/125397720/9a455a60-b25c-412d-b220-a8187fc658fe)

=================
=================

![image](https://github.com/parthmern/OPS102-Operating-System/assets/125397720/b1c25add-51e4-4e98-8658-60871a2e3ead)
![image](https://github.com/parthmern/OPS102-Operating-System/assets/125397720/8c392784-7dd2-4ddf-8daf-3fa6c2e9f97e)

![image](https://github.com/parthmern/OPS102-Operating-System/assets/125397720/96815a4f-8fd9-4389-aa26-ff963655e223)

### change user or group using `chown`
- [impVideo](https://youtu.be/LnKoncbQBsM?si=M6eAg9k9926pgm85)
- Change user = ` sudo chown newuser example.txt `
- change group = ` sudo chown :new_group filename_or_directory `
- chnage user and group same command = ` sudo chown newuser:newgroup example.txt `

![image](https://github.com/parthmern/OPS102-Operating-System/assets/125397720/bf70dd08-9fc1-4f46-9aeb-a3d585b95ada)

[explaination video](https://youtu.be/-BDmmlgF1kM?si=_HW_DFGTHald-Js5)

### umask

![image](https://github.com/parthmern/OPS102-Operating-System/assets/125397720/317d3c81-1c51-47fe-904b-d70a70ae7a86)

