# 8-Bit CPU Design & Simulation (ALU Focus)

This project features the design and implementation of a functional **8-bit CPU** and **Arithmetic Logic Unit (ALU)** using **Logisim Evolution 3.9.0**. [span_0](start_span)[span_1](start_span)[span_2](start_span)The architecture follows a **RISC-style** model with a two-operand system, focusing on modularity and clear data path execution[span_0](end_span)[span_1](end_span)[span_2](end_span).

## Core Features

### 1. 8-Bit ALU with 14 Operations
[span_3](start_span)[span_4](start_span)The ALU is the heart of this system, supporting a diverse set of instructions wired through a **14-input, 8-bit Multiplexer (MUX)**[span_3](end_span)[span_4](end_span).
* **[span_5](start_span)[span_6](start_span)[span_7](start_span)Arithmetic:** ADD, SUB, INC, DEC[span_5](end_span)[span_6](end_span)[span_7](end_span).
* **[span_8](start_span)[span_9](start_span)Logical:** AND, OR, XOR, NOT[span_8](end_span)[span_9](end_span).
* **[span_10](start_span)[span_11](start_span)Shifting:** SHL (Logical Left), SHR (Logical Right)[span_10](end_span)[span_11](end_span).
* **[span_12](start_span)[span_13](start_span)Data Utility:** PASS A, ZERO (0x00), ONE (0xFF), and a TEST AND gate for register diagnostics[span_12](end_span)[span_13](end_span).

### 2. Independent Comparison Logic (CMP)
[span_14](start_span)[span_15](start_span)The **CMP block** operates outside the MUX to generate three distinct 1-bit flags independently of the ALU result bus[span_14](end_span)[span_15](end_span):
* **[span_16](start_span)EQ** (Equal: A == B)[span_16](end_span).
* **[span_17](start_span)LT** (Less than: A < B)[span_17](end_span).
* **[span_18](start_span)GT** (Greater than: A > B)[span_18](end_span).
* [span_19](start_span)[span_20](start_span)These flags allow the control unit to handle conditional branching and logic[span_19](end_span)[span_20](end_span).

### 3. Architecture & Data Path
* **[span_21](start_span)[span_22](start_span)Registers:** Two 8-bit general-purpose registers (Reg_A and Reg_B) serve as operand sources and result destinations[span_21](end_span)[span_22](end_span).
* **[span_23](start_span)[span_24](start_span)Control Simulation:** Emulates a functional data path using manual Load and Clock signals to mimic real-world CPU instruction cycles[span_23](end_span)[span_24](end_span).
* **[span_25](start_span)Modular Design:** Built with high cohesion, allowing the ALU to be easily embedded into larger circuits[span_25](end_span).

## Assembly Program Examples
[span_26](start_span)To verify the hardware logic, the project includes simulated assembly programs[span_26](end_span):
* **[span_27](start_span)[span_28](start_span)Program 1 (Looping Addition):** Continually adds operands until a zero-condition is met via the EQ flag[span_27](end_span)[span_28](end_span).
* **[span_29](start_span)[span_30](start_span)[span_31](start_span)Program 2 (Bit-Shifting):** Right-shifts a value until the Least Significant Bit (LSB) becomes 0, utilizing the SHR and CMP instructions[span_29](end_span)[span_30](end_span)[span_31](end_span).

## Technical Challenges
* **[span_32](start_span)Lazy Evaluation Mitigation:** Addressed Logisim’s lazy evaluation model by implementing additional buffers and manual simulation tick triggering to ensure consistent output[span_32](end_span).

## Project Structure
* `/circ`: Contains the `.circ` file for Logisim Evolution.
* `/docs`: Contains the full **CPU Design Project Report** in PDF format.

---
*[span_33](start_span)Developed as part of Computer Science 306 course at Study.com[span_33](end_span).*
