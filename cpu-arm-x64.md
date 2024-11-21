# ARM 64

This guide provides an introduction to 64-bit ARM architecture, its instruction set, and practical assembly examples. ARM is widely used in modern mobile devices, embedded systems, and even servers due to its efficiency and performance.  

---

## Index  

- [Introduction to ARM64 Architecture](#introduction-to-arm64-architecture)  
- [Registers in ARM64](#registers-in-arm64)  
- [ARM64 Instructions](#arm64-instructions)  
  - [Data Movement](#data-movement)  
  - [Arithmetic and Logical Operations](#arithmetic-and-logical-operations)  
  - [Control Flow](#control-flow)  
- [Assembly Code Example](#assembly-code-example)  
- [Resources](#resources)  

---

## Introduction to ARM64 Architecture  

ARM64, also known as **AArch64**, is the 64-bit execution mode of the ARMv8 architecture. It offers enhancements over the 32-bit ARM architecture (AArch32), including:  

- A larger set of registers (31 general-purpose registers).  
- Support for 64-bit data and addressing.  
- Improved performance and energy efficiency.  

ARM64 is commonly found in devices like modern smartphones, tablets, and some laptops (e.g., Apple Silicon).  

---

## Registers in ARM64  

### General-Purpose Registers  

- **x0 - x30**: 64-bit general-purpose registers.  
  - **x0 - x7**: Used for passing arguments and returning values from functions.  
  - **x8**: Indirect result location register.  
  - **x9 - x15**: Temporary registers.  
  - **x16 - x18**: Intra-procedure-call temporary registers.  
  - **x19 - x28**: Callee-saved registers.  
  - **x29**: Frame pointer (optional).  
  - **x30**: Link register (holds return address).  

- **SP (Stack Pointer)**: Points to the top of the stack.  
- **PC (Program Counter)**: Holds the address of the current instruction.  

### Floating-Point and SIMD Registers  

- **v0 - v31**: Used for floating-point operations and SIMD (Single Instruction, Multiple Data).  

---

## ARM64 Instructions  

ARM64 assembly is designed to be simple and efficient. Here are some common instruction categories:  

### Data Movement  

- `MOV`: Move data between registers.  
- `LDR`: Load data from memory into a register.  
- `STR`: Store data from a register to memory.  

```asm
MOV x0, #5       // Move immediate value 5 into x0  
LDR x1, [x2]     // Load value from memory address in x2 to x1  
STR x0, [x2]     // Store value in x0 to memory address in x2  
```

### Arithmetic and Logical Operations  

- `ADD`: Add two registers.  
- `SUB`: Subtract one register from another.  
- `AND`: Bitwise AND operation.  
- `ORR`: Bitwise OR operation.  

```asm
ADD x0, x1, x2   // x0 = x1 + x2  
SUB x3, x4, x5   // x3 = x4 - x5  
AND x6, x7, x8   // x6 = x7 & x8  
ORR x9, x10, x11 // x9 = x10 | x11  
```

### Control Flow  

- `B`: Branch to a label.  
- `BL`: Branch with link (used for function calls).  
- `CBZ`: Compare and branch if zero.  
- `CBNZ`: Compare and branch if not zero.  

```asm
CBZ x0, label    // Branch to 'label' if x0 == 0  
BL function      // Call 'function'  
B loop           // Branch to 'loop'  
```

---

## Assembly Code Example  

Below is an example of a simple ARM64 assembly program that calculates the factorial of a number:  

### Code  

```asm
.section .data
number: .word 5         // Number to calculate factorial for
result: .word 0         // Store the result

.section .text
.global _start

_start:
    LDR x0, =number     // Load address of number into x0
    LDR w1, [x0]        // Load the number into w1 (32-bit register)
    MOV w2, #1          // Initialize result to 1

factorial_loop:
    MUL w2, w2, w1      // Multiply result (w2) by current number (w1)
    SUB w1, w1, #1      // Decrement the number (w1)
    CMP w1, #1          // Compare the number to 1
    BGT factorial_loop  // If number > 1, repeat the loop

    LDR x0, =result     // Load address of result
    STR w2, [x0]        // Store the factorial result

    // Exit program
    MOV x8, #93         // Exit syscall number
    MOV x0, #0          // Exit code 0
    SVC #0              // Make syscall
```

### Explanation  

1. **Input Data**: The `number` variable is the input to calculate the factorial.  
2. **Factorial Logic**: The loop repeatedly multiplies the result by the current number and decrements the number until it reaches 1.  
3. **Result Storage**: The result is stored in memory at the `result` label.  
4. **Exit**: The program exits using a syscall.  
