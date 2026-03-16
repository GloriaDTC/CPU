# 8-Bit CPU Design & Simulation (ALU Focus)

This project features the design and implementation of a functional **8-bit CPU** and **Arithmetic Logic Unit (ALU)** using **Logisim Evolution 3.9.0**. The architecture follows a **RISC-style** model with a two-operand system, focusing on modularity and clear data path execution.

## Core Features

### 1. 8-Bit ALU with 14 Operations
The ALU is the heart of this system, supporting a diverse set of instructions wired through a **14-input, 8-bit Multiplexer (MUX)**.
* **Arithmetic:** ADD, SUB, INC, DEC
* **Logical:** AND, OR, XOR, NOT
* **Shifting:** SHL (Logical Left), SHR (Logical Right)
* **Data Utility:** PASS A, ZERO (0x00), ONE (0xFF), and a TEST AND gate for register diagnostics

### 2. Independent Comparison Logic (CMP)
The **CMP block** operates outside the MUX to generate three distinct 1-bit flags independently of the ALU result bus:
* **EQ** (Equal: A == B)
* **LT** (Less than: A < B)
* **GT** (Greater than: A > B)  
These flags allow the control unit to handle conditional branching and logic

### 3. Architecture & Data Path
* **Registers:** Two 8-bit general-purpose registers (Reg_A and Reg_B) serve as operand sources and result destinations
* **Control Simulation:** Emulates a functional data path using manual Load and Clock signals to mimic real-world CPU instruction cycles
* **Modular Design:** Built with high cohesion, allowing the ALU to be easily embedded into larger circuits

## Assembly Program Examples
To verify the hardware logic, the project includes simulated assembly programs:
* **Program 1 (Looping Addition):** Continually adds operands until a zero-condition is met via the EQ flag
* **Program 2 (Bit-Shifting):** Right-shifts a value until the Least Significant Bit (LSB) becomes 0, utilizing the SHR and CMP instructions

## Technical Challenges
* **Lazy Evaluation Mitigation:** Addressed Logisim’s lazy evaluation model by implementing additional buffers and manual simulation tick triggering to ensure consistent output

## Project Structure
* `/circ`: Contains the `.circ` file for Logisim Evolution.
* `/pdf`: Contains the full **CPU Design Project Report** in PDF format.

---
*Developed as part of Computer Science 306 course at Study.com.*
