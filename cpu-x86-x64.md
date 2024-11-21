### x86_64

This guide provides an introduction to x86_64 assembly, including a list of common instructions, an overview of 64-bit CPU registers, and a practical example program.

---

## Overview of x86_64 Assembly Language

x86_64 is an extension of the x86 architecture, supporting 64-bit registers, larger memory addressing, and enhanced instruction sets. It is widely used in modern processors, including those from Intel and AMD.

---

## CPU Registers in x86_64

In x86_64, the number of general-purpose registers increases compared to x86, and their sizes expand to 64 bits.

### General-Purpose Registers
| Register | Purpose                             | Notes                                   |
|----------|-------------------------------------|-----------------------------------------|
| `RAX`    | Accumulator for operands           | Used in arithmetic and function returns. |
| `RBX`    | Base register                      | Used for addressing.                    |
| `RCX`    | Counter for loops                  | Iteration purposes.                     |
| `RDX`    | Data register                      | I/O and arithmetic.                     |
| `RSI`    | Source index for string operations | Source address in memory operations.    |
| `RDI`    | Destination index for string ops   | Destination address in memory operations. |
| `RSP`    | Stack pointer                      | Tracks the top of the stack.            |
| `RBP`    | Base pointer                       | Points to the base of the stack frame.  |
| `R8`-`R15` | Additional general-purpose regs  | Introduced in x86_64.                   |

### Segment Registers
| Register | Purpose                             |
|----------|-------------------------------------|
| `CS`     | Code Segment                       |
| `DS`     | Data Segment                       |
| `SS`     | Stack Segment                      |

---

## Common x86_64 Instructions

The instruction set of x86_64 largely builds upon x86, with additional enhancements for 64-bit operations. Below are some key instructions:

### Data Movement
- `MOV` - Move data
- `PUSH` - Push data onto the stack
- `POP` - Pop data off the stack
- `LEA` - Load effective address

### Arithmetic Operations
- `ADD` - Add
- `SUB` - Subtract
- `IMUL` - Multiply (signed)
- `IDIV` - Divide (signed)
- `INC` - Increment
- `DEC` - Decrement

### Logic and Bitwise Operations
- `AND` - Bitwise AND
- `OR` - Bitwise OR
- `XOR` - Bitwise XOR
- `SHL` - Shift left
- `SHR` - Shift right

### Control Flow
- `JMP` - Unconditional jump
- `JE` / `JZ` - Jump if equal/zero
- `JNE` / `JNZ` - Jump if not equal/not zero
- `CALL` - Call a procedure
- `RET` - Return from a procedure

---

## Simple Example Program in x86_64 Assembly

Below is a basic example that calculates the sum of numbers from 1 to 10 using x86_64 assembly.

### Example: Sum of Numbers from 1 to 10

```asm
section .data           ; Data section
    result dq 0         ; Allocate space for the result

section .text           ; Code section
    global _start       ; Entry point for the program

_start:
    mov rax, 0          ; Accumulator for the sum
    mov rcx, 10         ; Counter for the loop

loop_start:
    add rax, rcx        ; Add the value of RCX to RAX
    dec rcx             ; Decrement RCX
    jnz loop_start      ; Repeat until RCX = 0

    ; Store the result
    mov [result], rax   ; Move the final sum into memory

    ; Exit the program
    mov rax, 60         ; Syscall for exit
    xor rdi, rdi        ; Return code 0
    syscall             ; Exit
```

---

## Explanation of the Example

1. **Data Section**:
   - `result` is allocated to store the final sum.
2. **Initialization**:
   - `RAX` is cleared to prepare for the sum.
   - `RCX` is set to 10 (loop counter).
3. **Loop**:
   - The `ADD` instruction accumulates the value of `RCX` into `RAX`.
   - The `DEC` instruction decrements `RCX`.
   - `JNZ` repeats the loop while `RCX` is not zero.
4. **Store and Exit**:
   - The final result is stored in `result`.
   - The program exits using the Linux syscall mechanism.

---

## How to Assemble and Run

1. Save the code to a file (e.g., `sum64.asm`).
2. Assemble the code using **NASM**:
   ```bash
   nasm -f elf64 sum64.asm
   ```
3. Link the object file using **ld**:
   ```bash
   ld -o sum64 sum64.o
   ```
4. Run the program:
   ```bash
   ./sum64
   ```
