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

  
