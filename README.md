Linux Kernel-Level Lottery Scheduler Implementation
Project Overview
This project involves the implementation of a ticket-based Lottery Scheduling policy within the Linux 2.4.20 kernel. The primary objective was to facilitate probabilistic and fair CPU resource distribution among processes and users.
+4

Key Features

Custom System Call: Integrated a new system call, cprocinf, to securely retrieve process descriptors (counter, nice, weight, pid, uid) from kernel-space to user-space.
+2


Lottery Policy: Replaced the default scheduler with a lottery mechanism where processes are granted "tickets," and the CPU is allocated via a random draw.
+2


Dynamic Ticket Management: Implemented logic to dynamically adjust ticket counts (min 1, max 7) based on CPU residency time to prevent starvation and ensure responsiveness.
+2


Secure Memory Transfer: Utilized copy_to_user and verify_area protocols to manage memory boundaries between user and kernel segments.
+3

Performance Analysis
The implementation was rigorously benchmarked against the standard Linux scheduler. Using custom instrumentation and CPU-intensive load generators, the performance was evaluated based on:


Throughput: Total work completed per time unit.


Average Waiting Time: Latency experienced by processes in the run queue.


CPU Utilization: Distribution of CPU time across different user processes.
+1

Technical Stack

Language: C 
+1


Environment: Linux Kernel v2.4.20 
+1


Tools: GCC, Git, Make, dmesg
