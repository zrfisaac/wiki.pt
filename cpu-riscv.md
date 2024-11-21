# RISC-V Programming Guide  

This guide introduces **RISC-V**, a free, open-source RISC instruction set architecture (ISA), along with an example in RISC-V assembly language. RISC-V is designed to be highly flexible, making it ideal for research, development, and commercial use without licensing fees or royalties.  

---

## Index  

- [Introduction to RISC-V](#introduction-to-risc-v)  
- [Features of RISC-V](#features-of-risc-v)  
- [Registers in RISC-V](#registers-in-risc-v)  
- [Instruction Types](#instruction-types)  
- [RISC-V Assembly Code Example](#risc-v-assembly-code-example)  
- [Resources](#resources)  

---

## Introduction to RISC-V  

**RISC-V** is an open-source ISA based on the principles of Reduced Instruction Set Computing (RISC). Unlike proprietary ISAs like ARM or x86, RISC-V is freely available for use and modification. It supports a wide range of implementations, from low-power microcontrollers to high-performance processors.  

### Key Benefits  

- **Free and Open-Source**: No licensing fees or royalties.  
- **Scalable**: Designed for flexibility in various applications.  
- **Modular Design**: Allows custom extensions while maintaining compatibility.  
- **Simplicity**: Small, consistent instruction set for easy implementation and optimization.  

---

## Features of RISC-V  

1. **Base ISA**: Includes integer arithmetic instructions with optional extensions for floating-point, atomic operations, and more.  
2. **Open and Extensible**: Allows users to add custom instructions.  
3. **Endianness**: RISC-V is little-endian by default but supports big-endian configurations.  
4. **Community-Driven**: Backed by a strong, open community of developers and organizations.  

---

## Registers in RISC-V  

RISC-V features 32 general-purpose registers (GPRs), each 64 bits wide in the RV64I configuration.  

### Common Registers  

| Register | Name          | Description                      |  
|----------|---------------|----------------------------------|  
| x0       | Zero          | Always `0`.                     |  
| x1       | Return Address| Holds the return address for jumps. |  
| x2       | Stack Pointer | Points to the top of the stack. |  
| x3–x31   | General-Purpose| Used for data and computations. |  

---

## Instruction Types  

### RISC-V Instructions are divided into the following categories:  

1. **R-Type (Register Instructions)**: Operate on registers.  
   ```assembly  
   add x3, x1, x2   # x3 = x1 + x2  
   sub x3, x1, x2   # x3 = x1 - x2  
   ```  

2. **I-Type (Immediate Instructions)**: Operate with constants.  
   ```assembly  
   addi x3, x1, 10  # x3 = x1 + 10  
   lw x3, 0(x2)     # Load word from memory into x3  
   ```  

3. **S-Type (Store Instructions)**: Store data to memory.  
   ```assembly  
   sw x3, 0(x2)     # Store x3 into memory at x2  
   ```  

4. **B-Type (Branch Instructions)**: Conditional branches.  
   ```assembly  
   beq x1, x2, label # Branch to 'label' if x1 == x2  
   bne x1, x2, label # Branch to 'label' if x1 != x2  
   ```  

5. **J-Type (Jump Instructions)**: Control flow.  
   ```assembly  
   jal x1, label     # Jump to 'label' and save return address in x1  
   ```  

---

## RISC-V Assembly Code Example  

Below is a program that calculates the factorial of a number `n` using RISC-V assembly.  

### Code  

```assembly
.section .data
n:      .word 5        # Input: calculate factorial of 5
result: .word 0        # Output: store the result

.section .text
.global _start

_start:
    la x10, n          # Load address of n into x10
    lw x11, 0(x10)     # Load value of n into x11 (n)
    li x12, 1          # x12 = 1 (factorial result)

factorial_loop:
    beq x11, x0, done  # If n == 0, exit loop
    mul x12, x12, x11  # x12 = x12 * n
    addi x11, x11, -1  # n = n - 1
    j factorial_loop   # Repeat loop

done:
    la x10, result     # Load address of result
    sw x12, 0(x10)     # Store factorial in memory

    li a7, 93          # Exit syscall
    li a0, 0           # Exit code 0
    ecall
```

### Explanation  

1. **Input**: The program calculates the factorial of the value stored in `n`.  
2. **Loop**: Multiplies the current value of `n` by the factorial result and decrements `n` until it reaches `0`.  
3. **Output**: Stores the factorial in the memory location `result`.  
4. **Exit**: Ends the program cleanly using an `ecall`.  

