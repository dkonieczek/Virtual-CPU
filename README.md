# Virtual-CPU
C program to perform registry level simulation of a CPU based on the ARM Cortex M0+ architecture
<br></br>

![architecture](https://github.com/dkonieczek/Virtual-CPU/blob/master/architecture.png?raw=true)

## Example:

The following examples can be executed by modifying the file.txt file. This would simulate an executable file being loaded into memory.
The file is loaded into memory using 'l' (load) function, and ran using 'g' (go), or optionally stepping through each instruction using the 't' (trace) function.

### ADD & SUB
File content: 
```
0150
0230
```
This example demonstrates the ADD and SUB instructions. The executed file will add the immediate value of 5 into register R0. Then the immediate value of 3 is subtracted from register R0.
```
0xxx = Data Processing
x1xx = ADD / x2xx = SUB 
xx5x = Immediate value of 5 
xxx0 = Register R0
```
### Unconditional Branch
File content:
```
C123
```
This example demonstrates the uncondition branch instruction. The executed file will branch unconditionally to the immediate memory address 123. 
```
Cxxx = Unconditional Branch
x123 = Immediate memory address 123
```
### Conditional Branch
File content:
```
8144
```
This example demonstrates the conditional branch instruction. Specifically testing if the zero flag is set. The executed file will branch to address 44 if the zero flage is set.
```
8xxx = Conditional Branch
x1xx = Check Zero Flag
xx44 = Immediate memory address 44
```
### Stop
File content:
```
e000
```
This example demonstrates the stop instruction. The program will stop execution and exit when this instruction is executed.
```
exxx = Stop
x000 = Not used
```
