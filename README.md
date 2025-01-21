# Assembly Language Bug: Buffer Overflow and Invalid Memory Access

This repository demonstrates a common error in assembly language programming: buffer overflows and potential writes to invalid memory locations. The `bug.asm` file contains the erroneous code, while `bugSolution.asm` shows the corrected version.

## Bug Description
The `bug.asm` file includes code that is vulnerable to buffer overflow and can write to invalid memory addresses. If the value of `ecx` is too large, then `[ebx+ecx*4]` will point to a memory location outside of the allocated buffer, leading to unpredictable behavior (crash or data corruption). Similarly, if the calculated address `eax` is invalid, writing to it will likely result in a crash.

## Bug Solution
The `bugSolution.asm` file addresses the vulnerabilities by adding checks to ensure that `ecx` is within the bounds of the buffer and that the destination address `eax` is valid before any memory access occurs.  Appropriate error handling is also incorporated to gracefully handle invalid inputs.