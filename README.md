# Samsung RISC-V Talent Development Program
<br>
The RISC-V Talent Development Program, powered by Samsung Semiconductor India Research (SSIR) in collaboration with VLSI System Design (VSD), is an initiative that leverages open-source tools to teach VLSI chip design and RISC-V architecture. The program is led by esteemed instructor Kunal Ghosh.

##  Basic Details

**Name:** Manoj B
<br>
**College:** Atria Institutions of Technology  
**Email ID:** manoj2882003@gmail.com  
**GitHub Profile:** [manojDOX](https://github.com/manojDOX?tab=repositories)  
**LinkedIN Profile:** [Manoj B](https://www.linkedin.com/in/manoj-b-390821218/)

----------------------------------------------------------------------------------------------------------------

<details>
<summary><b>Task 1:</b> Task is to install all the essential tools required for this internship such as Ubuntu on VMBox, GNU Toolchain, GTKWave, Yosys and iVerilog simulator</summary>   
<br>

**1. Install Ubuntu 20.04 LTS on Oracle Virtual Machine Box**
> Setting up a virtual environment with Ubuntu 20.04 LTS to ensure a consistent development environment for all tasks. This includes configuring settings for optimal performance and usability.

![Ubuntu and VMBox Installation](https://github.com/manojDOX/samsung-riscv/blob/main/Task%201/virtual_machine.png)

**2. Install the RISC-V toolchain using the VDI**

### What is RISC-V GNU Toolchain?
> The RISC-V GNU Compiler Toolchain is a free and open source cross-compiler for C and C++. It supports two build modes: Generic ELF/Newlib and Linux-ELF/glibc. The toolchain can be used to create assembly instructions and sequences for execution in a simulator and target FPGA  

**3. compiling code in c**

### writing C code for printing sum up to n number

![compiling code in c](https://github.com/manojDOX/samsung-riscv/blob/main/Task%201/C_based_lab.png)

**4. generating RISC-V based O1 and Ofast**

### seen instruction reduction from O1 to Ofast
> Observing Optimization Levels: The optimization levels O1 and Ofast were applied to the compiled C code. Results revealed a significant reduction in the number of assembly instructions when moving from O1 to Ofast, showcasing the efficiency of RISC-V's optimization pipeline.



![RISC-V based result](https://github.com/manojDOX/samsung-riscv/blob/main/Task%201/RISC-V_Lab.png)

</details>

----------------------------------------------------------------------------------------------------------------

<details>
<summary><b>Task 2:</b> Implement a factorial program in C and analyze its RISC-V assembly output with spike simulation</summary>
<br>

**1. C Program Implementation**
> Writing a C program to calculate the factorial of a given number 'n'. The program demonstrates basic arithmetic operations and loop constructs.

![C Code Implementation](https://github.com/manojDOX/samsung-riscv/blob/main/Task%202/program_factorofn.png)

**2. RISC-V Compilation**
> Compiling the factorial program using RISC-V GCC compiler to generate assembly code. This step converts our high-level C code into RISC-V compatible assembly instructions.

![RISC-V GCC Compilation](https://github.com/manojDOX/samsung-riscv/blob/main/Task%202/factor_program_compilation.png)

**3. Optimization Level Analysis**
> Comparing assembly output between O1 and Ofast optimization levels. The analysis shows how different optimization flags affect the generated assembly code and overall instruction count.

![O1 Optimization](https://github.com/manojDOX/samsung-riscv/blob/main/Task%202/O1_instruction.png)
![Ofast Optimization](https://github.com/manojDOX/samsung-riscv/blob/main/Task%202/Ofast_instruction.png)
**4. Spike Simulation**
> Running the compiled program through the Spike RISC-V ISA Simulator to verify correct execution and analyze program behavior at the instruction level.

![Spike Simulation Results](https://github.com/manojDOX/samsung-riscv/blob/main/Task%202/simulation_of_O1_Ofast.png)

**Key Observations:**
- The factorial program demonstrates the use of loops and multiplication operations in RISC-V
- Different optimization levels (O1 vs Ofast) showed varying instruction counts and code organization
- Spike simulation confirmed correct program execution and output validation

</details>


----------------------------------------------------------------------------------------------------------------


<details>
<summary><b>Task 3:</b> Analysis of RISC-V Instruction Types and Assembly Code Documentation</summary>
<br>

![program](https://github.com/manojDOX/samsung-riscv/blob/main/Task%203/program.png)

![assembly_language_instruction](https://github.com/manojDOX/samsung-riscv/blob/main/Task%203/instruction_detail.png)

**1. Understanding RISC-V Instruction Formats**
> A comprehensive study of the six basic RISC-V instruction formats: R-type, I-type, S-type, B-type, U-type, and J-type instructions.

**2. Instruction Type Analysis with Detailed Encoding**

### I-Type Instructions (Immediate)
Example Instruction: `addi sp, sp, -128`
* **Opcode:** 0010011 (7 bits)
* **Immediate:** -128 (12 bits, two's complement)
* **Source Register (rs1):** sp (x2, 5 bits)
* **Destination Register (rd):** sp (x2, 5 bits)
* **Function (funct3):** 000 (3 bits)

Breakdown:
* **Immediate (-128):** `111111110000`
* **rs1 (sp = x2):** `00010`
* **funct3:** `000`
* **rd (sp = x2):** `00010`
* **Opcode:** `0010011`

Machine Code: `11111111000000010000000100010011`

Example Instruction: `ld ra, 8(sp)`
* **Opcode:** 0000011 (7 bits)
* **Immediate:** 8 (12 bits)
* **Source Register (rs1):** sp (x2, 5 bits)
* **Destination Register (rd):** ra (x1, 5 bits)
* **Function (funct3):** 011 (3 bits)

Breakdown:
* **Immediate (8):** `000000001000`
* **rs1 (sp = x2):** `00010`
* **funct3:** `011`
* **rd (ra = x1):** `00001`
* **Opcode:** `0000011`

### R-Type Instructions (Register)
Example Instruction: `add t0, t1, t2`
* **Opcode:** 0110011 (7 bits)
* **funct7:** 0000000 (7 bits)
* **Source Register 2 (rs2):** t2 (x7, 5 bits)
* **Source Register 1 (rs1):** t1 (x6, 5 bits)
* **Function (funct3):** 000 (3 bits)
* **Destination Register (rd):** t0 (x5, 5 bits)

Breakdown:
* **funct7:** `0000000`
* **rs2 (t2 = x7):** `00111`
* **rs1 (t1 = x6):** `00110`
* **funct3:** `000`
* **rd (t0 = x5):** `00101`
* **Opcode:** `0110011`

### S-Type Instructions (Store)
Example Instruction: `sd ra, 8(sp)`
* **Opcode:** 0100011 (7 bits)
* **Immediate[11:5]:** 0000000 (7 bits)
* **Source Register 2 (rs2):** ra (x1, 5 bits)
* **Source Register 1 (rs1):** sp (x2, 5 bits)
* **Function (funct3):** 011 (3 bits)
* **Immediate[4:0]:** 01000 (5 bits)

Breakdown:
* **Immediate[11:5]:** `0000000`
* **rs2 (ra = x1):** `00001`
* **rs1 (sp = x2):** `00010`
* **funct3:** `011`
* **Immediate[4:0]:** `01000`
* **Opcode:** `0100011`

### U-Type Instructions (Upper Immediate)
Example Instruction: `lui a0, 0x21`
* **Opcode:** 0110111 (7 bits)
* **Immediate[31:12]:** 20-bit immediate
* **Destination Register (rd):** a0 (x10, 5 bits)

Breakdown:
* **Immediate:** `00000000000000100001`
* **rd (a0 = x10):** `01010`
* **Opcode:** `0110111`

### J-Type Instructions (Jump)
Example Instruction: `jal ra, 104dc`
* **Opcode:** 1101111 (7 bits)
* **Immediate[20:1]:** 20-bit offset
* **Destination Register (rd):** ra (x1, 5 bits)

Breakdown:
* **Immediate:** `0000000100000011011100`
* **rd (ra = x1):** `00001`
* **Opcode:** `1101111`

**3. Common Patterns in Assembly Code**

Function Prologue:
```assembly
addi    sp,sp,-16        # Allocate stack frame
```
Encoding Breakdown:
* **Immediate (-16):** `111111110000`
* **rs1 (sp = x2):** `00010`
* **funct3:** `000`
* **rd (sp = x2):** `00010`
* **Opcode:** `0010011`

**4. Key Observations:**
- Each instruction type has a unique bit pattern for efficient decoding
- Immediate values are sign-extended appropriately
- Register encoding is consistent across instruction types
- Stack operations follow standard patterns
- Function calls maintain calling conventions through register usage

</details>

----------------------------------------------------------------------------------------------------------------

