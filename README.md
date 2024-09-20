# Basic Computer Simulation
## Project Description

Implement a simulation of a basic computer memory system, arithmetic/logic unit (ALU), and a set of registers. These components will be interconnected through a common bus controlled by three select lines (S2, S1, S0).

![image](https://github.com/yehiarasheed/Basic-Computer-Simulation/assets/157399068/02807870-c8cf-40d4-b466-bbf6ef27c614)
1. **Memory (RAM)**
   - Size: 128 addresses (words).
   - Each word is 16 bits.
   - Users can read from and write to memory.
   - The Address Register (AR) output connects to the memory's address lines.
   - Memory's input and output lines are connected to the common bus.

2. **Registers**
   - Available registers: DR, TR, AR, AC (Accumulator Register), PC, IR.
   - Each register has a load enable flag to control data updates from the bus.
   - Registers do not have increment (INC) or clear (CLR) capabilities.

3. **ALU (Arithmetic/Logic Unit)**
   - Two inputs: A (from DR) and B (from AC).
   - Control lines (C2, C1, C0) determine the ALU operations:
     - `(001) Transfer input A`
     - `(010) Increment A`
     - `(011) Multiply A * B`
     - `(100) Subtract A - B`
     - `(101) Divide A / B`
     - `(110) Add A + B`
     - `(111) A XOR B`

4. **Bus Selection**
   - Control select lines determine which component is connected to the bus:
     - `(000) Memory`
     - `(001) AR`
     - `(010) PC`
     - `(011) AC`
     - `(100) DR`
     - `(101) TR`
     - `(111) IR`

Then we enhance the basic computer by adding a control unit, implementing the PC register as a counter and implementing a specific program.

5. **Control Unit**
   - Add decoders, sequence counters, and logic gates to implement the control unit.
   - Ensure all unused control signals are set to zero for stability.
   - Redesign timing diagrams for instructions as registers do not have clear or increment functionalities (or design registers to include these features).

6. **Program Assembly**
   - Implement the following program:
     ```c
     int A, B, C, i; // variables
     for (i = 0; i < 3; i++) {
         C += A / B;
         A += A * B;
     }
     ```
   - Example expected outputs after 3 iterations: A = 432, B = 2, C = 104.

7. **Instruction Set**
   - Implement the following instructions: LDA, MUL, ADD, STA, DIV, ISZ, BUN.
   - Use BSA opcode for MUL and AND opcode for DIV.
   - Ignore HLT and interrupt instructions; use normal instruction cycle.

## How to Install

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/yehiarasheed/Basic-Computer-Simulation.git
   cd Basic-Computer-Simulation
   ```
   This command downloads a copy of the repository to your local machine and navigates into the project directory.

2. **Install PSpice:**
   Download and install PSpice from the [official PSpice website](https://www.pspice.com/). PSpice is essential for running and modifying the simulation files.

3. **Open the Project in PSpice:**
   - Launch PSpice.
   - Navigate to the project files by selecting `File → Open` and choosing the appropriate `.circ` file from the cloned repository.

## Dependencies

This project relies on the following dependency:

- **PSpice**: The application required to run and simulate the basic computer architecture.

Make sure PSpice is installed and correctly configured on your machine to execute the simulation files in this project.

## Credits
- **Developers**: Jomana Mahmoud, Nada Yasser, Rawan Hossam, Amr Osama & Yehia Rasheed.

All media used in this project, including images and videos, are credited to their respective creators and used under fair use for educational and demonstration purposes. If you plan to use this project for commercial purposes, you must ensure you have obtained the necessary licenses or permissions for any copyrighted media.

---
