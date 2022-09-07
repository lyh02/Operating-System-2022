---
layout: page
title: "homework2"
permalink: /homework/2/
---

# P37: Problems 1.3, 1.4, 1.7, 1.8, 1.9 (8th Edition)

**1.3** Consider a hypothetical 32-bit microprocessor having 32-bit instructions composed of  two fields. The first byte contains the opcode and the remainder an immediate operand or an operand address.

​	**a.** What is the maximum directly addressable memory capacity (in bytes)?

​	**b.** Discuss the impact on the system speed if the microprocessor bus has

​		**1.** a 32-bit local address bus and a 16-bit local data bus, or

​		**2.** a 16-bit local address bus and a 16-bit local data bus.

​	**c.** How many bits are needed for the program counter and the instruction register?

**1.4.** Consider a hypothetical microprocessor generating a 16-bit address (e.g., assume that  the program counter and the address registers are 16 bits wide) and having a 16-bit data bus.

​	**a.** What is the maximum memory address space that the processor can access directly if it is connected to a “16-bit memory”?

​	**b.** What is the maximum memory address space that the processor can access directly if it is connected to an “8-bit memory”?

​	**c.** What architectural features will allow this microprocessor to access a separate  “I/O space”?

​	**d.** If an input and an output instruction can specify an 8-bit I/O port number, how many 8-bit I/O ports can the microprocessor support? How many 16-bit I/O 

ports? Explain.

**1.7** In virtually all systems that include DMA modules, DMA access to main memory is given higher priority than processor access to main memory. Why?

**1.8** A DMA module is transferring characters to main memory from an external device  transmitting at 9600 bits per second (bps). The processor can fetch instructions at the rate of 1 million instructions per second. By how much will the processor be slowed down due to the DMA activity?

**1.9** A computer consists of a CPU and an I/O device *D* connected to main memory *M* via a shared bus with a data bus width of one word. The CPU can execute a maximum of 106 instructions per second. An average instruction requires five processor cycles, three of which use the memory bus. A memory read or write operation uses one processor cycle. Suppose that the CPU is continuously executing “background” programs that require 95% of its instruction execution rate but not any I/O instructions. Assume that one processor cycle equals one bus cycle. Now suppose that very large blocks of data are to be transferred between *M* and *D.*

​	**a.** If programmed I/O is used and each one-word I/O transfer requires the CPU to execute two instructions, estimate the maximum I/O data transfer rate, in words per second, possible through *D.*

​	**b.** Estimate the same rate if DMA transfer is used.