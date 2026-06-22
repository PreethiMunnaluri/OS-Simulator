# OS Memory Management Simulator

A C++-based Operating System simulator that models core OS functionalities including process management, paging, virtual memory, interrupt handling, address translation, and execution of assembly-like instructions.

## Overview

This project simulates the internal working of an Operating System by implementing:

* Process Control Blocks (PCB)
* Paging and Virtual Memory
* Page Table Management
* Address Translation (Virtual → Physical)
* Interrupt Handling
* Page Fault Handling
* Memory Allocation
* Instruction Execution Cycle
* Input/Output Operations

The simulator executes jobs defined using control cards and a custom instruction set, demonstrating key Operating System and Computer Architecture concepts.

---

## Features

### Memory Management

* 300-word memory organized into 30 frames
* Dynamic frame allocation
* Page table creation and management
* Virtual-to-physical address mapping

### Process Management

* Process Control Block (PCB)
* Process ID (PID)
* Total Time Limit (TTL)
* Total Line Limit (TLL)
* Total Time Counter (TTC)
* Line Limit Counter (LLC)

### Interrupt Handling

* Service Interrupt (SI)
* Program Interrupt (PI)
* Timer Interrupt (TI)

### Error Handling

* Out Of Data
* Line Limit Exceeded
* Time Limit Exceeded
* Operation Code Error
* Operand Error
* Invalid Page Fault

### Instruction Execution

* Fetch–Decode–Execute cycle
* Register operations
* Conditional branching
* Program execution monitoring

---

## Instruction Set

| Instruction | Description                         |
| ----------- | ----------------------------------- |
| GD          | Read data from input file           |
| PD          | Write data to output file           |
| LR          | Load memory contents into register  |
| SR          | Store register contents into memory |
| CR          | Compare register with memory        |
| BT          | Branch if comparison is true        |
| H           | Halt execution                      |

---

## Architecture

### CPU Components

* Instruction Register (IR)
* General Purpose Register (R)
* Instruction Counter (IC)
* Toggle Flag (C)

### Operating System Components

* Monitor Operating System (MOS)
* Process Control Block (PCB)
* Page Table Register (PTR)
* Memory Manager

---

## Memory Organization

Physical Memory:

300 words
30 frames
10 words per frame

Each page contains 10 words and is mapped to a frame through the page table.

---

## Address Translation

The simulator performs virtual-to-physical address translation using page tables.

Virtual Address
↓
Page Number + Offset
↓
Page Table Lookup
↓
Frame Number
↓
Physical Address

---

## Page Fault Handling

### Valid Page Fault

Occurs when:

* GD
* SR

The Operating System allocates a new frame and updates the page table.

### Invalid Page Fault

Occurs when:

* PD

The program terminates with an error.

---

## Job Control Cards

### Start Job

$AMJ

Contains:

* Process ID
* Total Time Limit
* Total Line Limit

### Data Section

$DTA

Marks the beginning of input data.

### End Job

$END

Marks the end of the job.

---

## Sample Input

$AMJ100000300010

GD20

PD20

H

$DTA

HELLO WORLD

$END

---

## Sample Output

HELLO WORLD

---

## Concepts Demonstrated

* Operating System Fundamentals
* Paging
* Virtual Memory
* Process Management
* Interrupt Handling
* Address Translation
* Memory Allocation
* CPU Instruction Execution
* Error Detection and Recovery

---

## Technologies Used

* C++
* File Handling
* Data Structures
* Memory Management Concepts
* Operating System Design Principles

---

## Learning Outcomes

This project helped in understanding:

* How Operating Systems manage memory
* Page table organization and translation
* Interrupt-driven execution
* Process control structures
* Virtual memory implementation
* CPU instruction execution cycle
* Error and exception handling mechanisms

---

## Future Enhancements

* CPU Scheduling Algorithms (FCFS, SJF, Round Robin)
* Multi-programming Support
* Demand Paging
* Memory Deallocation
* Process Synchronization
* Resource Allocation Management
