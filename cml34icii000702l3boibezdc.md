---
title: "Linux Fundamentals: Kernel, Processes, and systemd Explained"
seoTitle: "Understanding Linux: Kernel, Processes, systemd"
seoDescription: "Learn Linux fundamentals including the kernel, processes, and systemd for efficient system management and faster debugging"
datePublished: Sun Feb 01 2026 02:30:12 GMT+0000 (Coordinated Universal Time)
cuid: cml34icii000702l3boibezdc
slug: linux-fundamentals-kernel-processes-and-systemd-explained
canonical: https://github.com/jkpatelnx/90DaysOfDevOps/blob/learning/2026/2026/day-02/linux-architecture-notes.md
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1769737001312/235db11b-c419-4f89-b462-3a61eeeeb88b.png
tags: linux, systemd, linux-kernel, linux-commands, linux-processes

---

Linux is built around a small set of powerful components. Understanding these core concepts helps you use Linux confidently and debug real systems faster.

## 1. Core Components of Linux  
The diagram below shows how Linux components are layered and interact with each other. 
    
<p align="center">
  <img src="https://cdn.hashnode.com/res/hashnode/image/upload/v1769730902597/7333555a-a62d-4381-8e1a-d2a5993f942f.png" width="600">
</p>

1. Kernel :
    - Core of Linux that manages hardware resources (CPU, memory, disk, network).  
    - Provides system calls and controls processes, memory, file systems, and networking.  
2. Shell :
    - Command-line interface that lets users interact with the kernel.
    - Interprets commands and runs programs in user space (e.g. `bash`, `zsh`). 
3. Utilities / User Programs :
    - Standard Linux commands and applications used for daily tasks.
    - Run in user space and rely on the kernel; failures don’t crash the system. 
4. init / systemd :
    - First user-space process (`PID 1`) started by the kernel at boot.
    - Starts and manages services, handles dependencies, and keeps the system running.

## 2. How Processes Are Created and Managed in Linux
    
#### What Is a Process?
A process is a running program.  
Example : When you run a command like `ls`, Linux creates a process.

#### How a Process Is Created (fork + exec)? 
- **Step 1**: `fork()` : A parent process creates a child process. Child is almost a copy of the parent and gets a new PID.  
- **Step 2**: `exec()` : The child loads and runs a new program. Old program is replaced in memory.

#### How Linux Manages Processes?
Process Scheduling : Kernel decides which process runs on the CPU. Scheduler shares CPU time so many processes run smoothly.

#### Process States
* `Running` – executing on CPU 
* `Sleeping` – waiting for input/resource
* `Stopped` – paused by user
* `Zombie` – finished, waiting for cleanup
 
#### Process Termination
Process ends when it finishes or is killed by a signal. Parent process collects the exit status.

## 3. What systemd Does and Why It Matters
    
#### What is systemd?
**systemd** is the first user-space process started by the Linux kernel. It always runs as `PID 1` and controls the system after boot.

#### What systemd Does?
* Starts the system during boot  
* Manages services (`ssh`, `nginx`, `docker`)
* Handles service dependencies
* Restarts failed services automatically
* Manages logs using `journald`
* Controls system states (`targets`)  

In short: systemd manages the entire system lifecycle.

#### Why systemd Matters?
* Faster boot with parallel service startup  
* More reliable services through auto-restart
* Centralized management of services, logs, and timers 
* Standard init system on modern Linux distributions
    
## 4. Here are some commonly used commands in Linux 
* `ls` – list files and directories   
* `cd` – navigate directories   
* `ps` – view running processes   
* `top` – monitor system resources   
* `df` – check disk usage
    

<p align="center">
  <img src="https://cdn.hashnode.com/res/hashnode/image/upload/v1769735364976/4944e687-cbfb-4590-bfa2-4c7b9de88418.png" width="600">
</p>

<p align="center">
  <img src="https://cdn.hashnode.com/res/hashnode/image/upload/v1769735493496/c9faece8-51e4-4b4c-8a23-bdef78506237.png" width="600">
</p>