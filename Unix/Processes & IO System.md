# Processes
Processes have ids, PIDs. Processes can spawn other decendents, who inherit the environment variables of their parent process.
- sub processes can change variables, but do not effect their parent

[source](http://blog.honeybadger.io/ruby-guide-environment-variables/)

- when program is executed, a special environment is created for it, containing everything it needs to run
- when a command is issued, a new process is started
- OS tracks rpocesses with five digit ID (pid)
- **Foreground Processes** take input from keyboard and output to screen (think commands)
- **Background Processes** run in background, you can run other commands while they're running
- each unix process has pid and *parent process id* (ppid), run `ps -f` for info
- when a child ps is killed, SIGCHLD is sent to the parent (for it to create a new ps or act)
- **Daemon Processes** are system-related background processes, have no controlling terminal

### Anonymous Pipe
An anonymous pipe is a one-way FIFO channel for communication between processes.
- typically a parent program opens anonymous pipes, spawns child processes that inherit other ends of the pipes
  - or creates several processes and arranges them in a pipeline

### File Descriptors
A **handle** is just an abstract reference to some resource outside the scope of your software (think like accessing memory in a database or from the OS). A **File Descriptor** is a type of handle 

#### inode
Data structure that describes a filesystem object (file/directory), with metadata attributes, disk block location as well as the object's data
- must include size in bytes, device ID (containing inode), user ID of owner, group ID, file permissions mode, timestamp for last modified & accessed, link count for number of hard links
