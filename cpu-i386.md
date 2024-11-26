### CPU x86

This guide provides an overview of x86 assembly language, including a comprehensive list of common instructions, an explanation of CPU registers, and a simple example program in assembly.

---

## Overview of x86 Assembly Language

The x86 architecture is a family of instruction set architectures based on the Intel 8086 CPU. It includes registers, a well-defined instruction set, and a variety of addressing modes.

---

## CPU Registers in x86

x86 has several registers that are categorized as **general-purpose**, **segment**, **index/pointer**, and **control** registers:

### General-Purpose Registers
| Register | Purpose                      | Notes                           |
|----------|------------------------------|---------------------------------|
| `EAX`    | Accumulator for operands     | Used in arithmetic operations. |
| `EBX`    | Base register                | Used in addressing memory.     |
| `ECX`    | Counter for loops            | Used for iteration.            |
| `EDX`    | Data register                | Used in I/O and arithmetic.    |

### Segment Registers
| Register | Purpose                      |
|----------|------------------------------|
| `CS`     | Code Segment                 |
| `DS`     | Data Segment                 |
| `ES`     | Extra Segment                |
| `SS`     | Stack Segment                |

### Index and Pointer Registers
| Register | Purpose                      |
|----------|------------------------------|
| `ESI`    | Source index for string ops  |
| `EDI`    | Destination index for string ops |
| `ESP`    | Stack Pointer                |
| `EBP`    | Base Pointer                 |

---

## Common x86 Instructions

Here is a categorized list of commonly used x86 instructions:

### Data Movement
- `MOV` - Move data
- `PUSH` - Push data onto the stack
- `POP` - Pop data off the stack
- `LEA` - Load effective address
- `XCHG` - Exchange data

### Arithmetic Operations
- `ADD` - Add
- `SUB` - Subtract
- `MUL` - Multiply (unsigned)
- `IMUL` - Multiply (signed)
- `DIV` - Divide (unsigned)
- `IDIV` - Divide (signed)
- `INC` - Increment
- `DEC` - Decrement

### Logic and Bitwise Operations
- `AND` - Bitwise AND
- `OR` - Bitwise OR
- `XOR` - Bitwise XOR
- `NOT` - Bitwise NOT
- `SHL` - Shift left
- `SHR` - Shift right
- `CMP` - Compare two operands

### Control Flow
- `JMP` - Unconditional jump
- `JE` / `JZ` - Jump if equal/zero
- `JNE` / `JNZ` - Jump if not equal/not zero
- `JG` / `JNLE` - Jump if greater
- `JL` / `JNGE` - Jump if less
- `CALL` - Call a procedure
- `RET` - Return from a procedure

---

## Simple Example Program in Assembly

Below is a basic program written in x86 assembly language that demonstrates moving data, arithmetic operations, and using loops.

### Example: Sum of Numbers from 1 to 10

```asm
section .data          ; Data segment
    result db 0        ; Store the result here

section .bss           ; Uninitialized data
    temp resb 1

section .text          ; Code segment
    global _start       ; Entry point for the program

_start:
    mov ecx, 10         ; Set up the loop counter (1 to 10)
    xor eax, eax        ; Clear the accumulator (EAX = 0)
    xor ebx, ebx        ; EBX will hold the sum

loop_start:
    add ebx, ecx        ; Add the current value of ECX to EBX
    loop loop_start     ; Decrement ECX and repeat until ECX = 0

    ; Store the result in memory
    mov [result], bl    ; Move the lower byte of EBX to the result

    ; Exit the program
    mov eax, 1          ; System call number for exit
    int 0x80            ; Call the kernel
```

---

## Explanation of the Example

1. **Data Section**: 
   - The `result` variable is declared to store the final sum.
2. **Initialization**:
   - `ECX` is set to 10 (the loop counter).
   - `EAX` and `EBX` are cleared to prepare for arithmetic.
3. **Loop**:
   - The `ADD` instruction adds the current value of `ECX` to `EBX`.
   - The `LOOP` instruction decrements `ECX` and jumps to the label if `ECX` is not zero.
4. **Exit**:
   - The program exits gracefully by invoking a system call (`int 0x80`).

---

## How to Assemble and Run

To assemble and run the above program:

1. Save the code to a file (e.g., `sum.asm`).
2. Use the **NASM** assembler to assemble the code:
   ```bash
   nasm -f elf32 sum.asm
   ```
3. Link the object file using the **ld** linker:
   ```bash
   ld -m elf_i386 -o sum sum.o
   ```
4. Run the program:
   ```bash
   ./sum
   ```
