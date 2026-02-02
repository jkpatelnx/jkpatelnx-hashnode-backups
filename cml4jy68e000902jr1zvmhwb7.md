---
title: "Linux Commands Every DevOps Engineer Must Know"
seoTitle: "Essential Linux Commands for DevOps Engineers"
seoDescription: "Key Linux commands for DevOps: process, file, disk management, networking, troubleshooting. Enhance workflow with this reference guide"
datePublished: Mon Feb 02 2026 02:30:10 GMT+0000 (Coordinated Universal Time)
cuid: cml4jy68e000902jr1zvmhwb7
slug: linux-commands-every-devops-engineer-must-know
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1769983414321/76977b5c-7e5a-47b2-a5e1-4849e82e216f.png
tags: linux, linux-commands

---

Mastering Linux is a core skill for every DevOps engineer. From managing processes and disks to debugging networks and services, these Linux commands are used daily in real-world DevOps workflows. This guide is a quick revision-friendly reference covering the most essential Linux commands every DevOps engineer must know.

## 1\. Linux Process Management Commands (Revision Notes)

| No. | Command | Purpose | When to Use |
| --- | --- | --- | --- |
| 1 | `ps aux` | Show all running processes with user and resource usage | Quickly list all active processes |
| 2 | `top` | Real-time view of CPU, memory usage, and running processes | Monitor system performance live |
| 3 | `htop` | Enhanced and interactive process viewer (if installed) | Easier and more readable alternative to `top` |
| 4 | `pidof nginx` | Get the process ID (PID) of a running service | Find PID without searching manually |
| 5 | `kill <PID>` | Gracefully stop a process using its PID | Safely terminate a process |
| 6 | `kill -9 <PID>` | Force kill a process immediately | Use only when normal kill fails |
| 7 | `pkill node` | Kill processes by name instead of PID | Stop multiple processes at once |
| 8 | `uptime` | Show system running time and load average | Check system health and load |
| 9 | `watch -n 2 ps aux` | Run a command repeatedly at fixed intervals | Continuous monitoring of 

### Quick Notes
* Prefer `kill <PID>` over `kill -9` to avoid data corruption
* `htop` is recommended for clarity and ease of use
* `watch` is useful for real-time debugging and observation
    
## 2\. File System & Disk Commands (Revision Notes)

| No. | Command | Purpose | When to Use |
| --- | --- | --- | --- |
| 1 | `ls -lah` | List files with permissions, size, and hidden files | Inspect directory contents in detail |
| 2 | `pwd` | Show the current working directory | Confirm your current location |
| 3 | `cd /var/log` | Change directory | Navigate to system log files |
| 4 | `du -sh *` | Show disk usage of files and folders | Identify large files or directories |
| 5 | `df -h` | Display disk space usage in human-readable format | Check available disk space |
| 6 | `stat file.txt` | Show detailed metadata of a file | View timestamps, inode, and permissions |
| 7 | `find / -name nginx.conf` | Search for files by name | Locate configuration files |
| 8 | `chmod 644 file.txt` | Change file permissions | Set correct read/write access |
| 9 | `chown user:user file.txt` | Change file ownership | Fix ownership and access issues |

### Quick Notes
* `ls -lah` is ideal for auditing directories quickly
* Use `du -sh *` before expanding disk space    
* Avoid running `find /` on production systems during peak hours
    
## 3\. Networking & Troubleshooting Commands (Revision Notes)

| # | Command | Purpose | When to Use |
| --- | --- | --- | --- |
| 1 | `ip addr` | Show network interfaces and IP addresses | Verify IP configuration |
| 2 | `ping google.com` | Test network connectivity and latency | Check if a host is reachable |
| 3 | `ss -tuln` | Show listening ports and services | Identify open ports and running services |
| 4 | `curl -I https://example.com` | Fetch HTTP response headers | Validate website or API availability |
| 5 | `dig google.com` | DNS lookup and troubleshooting | Debug DNS resolution issues |
| 6 | `traceroute google.com` | Trace the network path to a host | Identify where network delays occur |

### Quick Notes
* Use `ss -tuln` instead of deprecated `netstat`   
* If `ping` fails but `curl` works, ICMP may be blocked  
* `traceroute` helps isolate network bottlenecks
    
---

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1769985517024/874fd4ed-af31-4371-babd-a636b780d1bf.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1769985532018/2aa7750b-c004-497a-96df-7c9523d95c0f.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1769985551174/eb60c876-c7d6-4d81-9a38-f1919875160e.png align="center")