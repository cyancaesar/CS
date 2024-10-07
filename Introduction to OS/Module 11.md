### Module 11: Process and Job Control

**Objectives**:
- Basic processes and job control
- How the kernel uses identification numbers to track and run processes
- How to run jobs in the foreground and backgroun
- Send a signal to a process

A process is a running program with the following information:
- **PID**: Process Identifier
- Scheduling Priority
- Memory Context
- Files Descriptor
- Security References

**Process Status**
- R : Running (process is runnning or ready to run)
- S : Sleeping (process is not running; rather, it is waiting for an event)
- T : Traced or Stopped (process has been instructed to stop)
- D : non-interruptible sleeping (process is waiting for I/O)
- Z : Zombie (child process that has terminated, but has not been cleaned up by its parent)

**Commands for Processes**
- **ps** : display info about process (stands for process status)
- **kill**, **pkill**, **killall** : send a signal to a process (for termination)
- **pgrep** : search for a specific process
- **jobs** : display processes running in the background and the foreground
- **top/htop** : display continuous info about all processes

Process Status : **ps**

To know all the processes and correspondingly their assigned pid, run
- ps -A

The options **A** and **e** provide summarized overview of running processes.

To print the detailed overview, use the options **f** (full format) and **F** (extra full format) with these options.

`ps aux` command options (ps aux)
- a : This option prints the running processes from all users
- u : This option shows user or owner column in output
- x : This option prints the processes those have not been executed from terminal

To give the Process ID (PID) of a process, run: `pidof mysqld`

**Displaying a List of All Processes**

`ps -ef` command to view a listing of all the processes currently scheduled to run on the system.

**Columns names**
- UID : Owner of the process
- PID : Process ID
- PPID : Parent Process ID
- C : The central processing unit (CPU) utilization for scheduling.
- STIME : The time the process started (hh:mm:ss)
- TTY : Short for Teletype and refer to the controlling terminal for the process
- TIME : The cumulative execution time for the process
- CMD : Is the name of the command that launched the process (command name, options and arguments)

**Searching for a Specific Process**

To search for a particular process, you can use one of these options:
- ps and grep command with pipe
- Using pgrep
- `pgrep -u root sshd`
- `ps -ef | grep sshd`

##### Unix Signals

**Signals** are communication tools between processes.
Each signal has a unique number.
Each signal has a specific meaning when receive by given process.

- 1 SIGHUP : End of session
- 2 SIGINT : Interruption (CTRL + C)
- 4 SIGILL : illegal instruction
- 6 SIGABRT : Instruction IOT or abort
- 8 SIGFPE : Floating Point Error
- 9 SIGKILL : Force Termination

**Sending Signals: Killing a Process**

To terminate a process (will not run anymore)
**kill PID**.

Important notes:
- A user can kill all his process
- A user can not kill another user's process
- A user can not kill processes System is using
- A root user can kill System-level-process and the process of any user

```bash
kill PID1 PID2
# or
kill -9 PID1 PID2
killall mysqld
```

`pkill` command is used after `pgrep` command.
Default signal is **SIGTERM** (15)
`pgrep -u root sshd ; pkill`

##### Type of Processes

**Foreground Processes**: They run on the screen
**Background Processes**: They run in the background

By default, all commands are executed in the foreground.

Sending foreground process to background using `&` at the end
```bash
find / -name core -exec rm -f {} \; &
```

##### Other Commands
- bg : To send a process to the background
- fg : To run a stopped process in the foreground
- Ctrl+Z : To suspend a job from the foreground
- jobs : display jobs from the background and those who are *suspended*

##### Process Scheduling and Priority

Priority of a process is called **niceness** in Linux
It has a value between -20 to 19
- The lower the higher priority
- Default is 0

**nice**
To start a process with a niceness value other than the default

```bash
nice -n 'nice value' process_name
```

**renice**
Used when a process is already running on the system.

```bash
renice 'nice value' -p 'PID'
```

```text
ps - Report a snapshot of current processes
top - Display tasks/processes
jobs - List active jobs
bg - Place a job in the background
fg - Place a job in the foreground
kill - Send a signal to a process
killall - Kill processes by name
```

