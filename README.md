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
