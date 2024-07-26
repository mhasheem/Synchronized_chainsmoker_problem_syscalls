# Synchronized_chainsmoker_problem_syscalls
 System calls added through recompilation of Ubuntu to solve chainsmoker problem. 
Here's a concise README file for your GitHub repository that covers the essential aspects of your project:

---

# Synchronized Chainsmoker Problem

## Overview

This project implements a solution to the synchronized chainsmoker problem, a classic concurrency problem in operating systems. The problem involves multiple threads (smokers) and an agent, where the challenge lies in synchronizing their actions to avoid deadlocks and ensure correct operation. The solution integrates custom syscalls into the Ubuntu Linux kernel to facilitate communication between the agent and the smokers, using semaphores for synchronization.

## Features

- **Custom Syscalls**: Implemented two custom syscalls (`agent_syscall` and `smoker_syscall`) with specific syscall numbers (548 for agent and 549 for smoker).
- **Kernel Space Implementation**: Integrated synchronization mechanisms (semaphores and completions) in the Linux kernel to manage concurrency.
- **User Space Program**: A user-space application that interacts with the custom syscalls to simulate the chainsmoker problem.
- **Concurrency Control**: Utilized semaphores to manage the synchronization between the agent and the smokers to prevent deadlocks.

## Technologies Used

- **Programming Language**: C
- **Operating System**: Ubuntu 16.04 LTS
- **Kernel Version**: Linux 4.17.4
- **Virtual Machine**: Oracle VM VirtualBox 7.0.14

## Files

- **Kernel Level Code**: Includes syscall implementations for the agent and smokers.
- **User Space Program**: Simulates the interaction with syscalls and handles the agent and smokers' activities.
- **Makefile**: Build scripts for compiling the kernel and user-space programs.
- **Syscall Table Updates**: Changes made to the syscall table for integrating custom syscalls.

## Instructions

1. **Compile the Kernel**:
   - Apply patches to include custom syscalls.
   - Recompile the kernel and install it.
   
2. **Build the User Space Program**:
   - Use the provided Makefile to compile the user-space application.

3. **Run the Program**:
   - Execute the user-space program to simulate the chainsmoker problem.
   - Observe the output to verify the correct functioning of synchronization.

## Limitations

- The solution may encounter deadlocks under certain conditions due to the constraints of semaphore-based synchronization.
- The system may face increased complexity with more than three smokers or different configurations.

## Conclusion

This project demonstrates a robust approach to solving the synchronized chainsmoker problem using kernel-level syscalls and synchronization mechanisms. It effectively illustrates concurrency control and interprocess communication within the Linux operating system.
