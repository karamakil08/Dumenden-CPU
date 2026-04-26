# 4-Bit Minimal Logisim CPU

A minimal 4-bit CPU implementation built in Logisim. This project focuses on a **triple-bus architecture** to demonstrate the fundamental flow of data between registers and the ALU.

## 🏗️ Architecture Overview

The CPU is built using Logisim's subcircuit feature, ensuring a modular and clean design. The architecture relies on three primary buses for data transfer, allowing for efficient register-to-register operations.

### Key Specifications

- **Data Width**: 4-bit
- **Instruction Width**: 16-bit
- **Buses**: 3 (Triple-bus system)
- **Software**: Made with Logisim

## ⚡ Arithmetic Logic Unit (ALU)

The ALU executes four core operations based on a 2-bit operation code (bits 13 and 12).

| Opcode | Operation | Function                  |
|--------|-----------|---------------------------|
| 00     | ADD       | Adds values from Ra and Rb |
| 01     | AND       | Logical AND of Ra and Rb   |
| 10     | OR        | Logical OR of Ra and Rb    |
| 11     | XOR       | Logical XOR of Ra and Rb   |

## 📜 Instruction Set Architecture (ISA)

The instruction word is 16 bits long. The hardware decodes the bits according to the following mapping:

| Bits   | Label      | Function                                      |
|--------|------------|-----------------------------------------------|
| 15:14  | Data Op    | Data manipulation (e.g., MOVIMD)              |
| 13:12  | ALU Op     | Selects ADD, AND, OR, or XOR                  |
| 11:9   | -          | Not used (Reserved)                           |
| 8:6    | Ra         | Source Register A                             |
| 5:3    | Rb         | Source Register B                             |
| 2:0    | Rd         | Destination Register                          |

### Data Manipulation

- **MOVIMD** (Move Immediate): The only supported data manipulation operation, used to load immediate values into the system registers.

## 🚀 How to Run

1. **Open the Circuit**: Load the `.circ` file in Logisim.
2. **Toggle the Clock**:
   - Ensure the ROM is loaded with the program.
   - Go to **Simulate → Ticks Enabled** (or press `Ctrl + K`).
3. **Monitor Execution**:
   - The program stored in ROM will execute automatically as the clock ticks.
   - Use the **Poke Tool** to inspect register values in real-time.

## 📂 Design Components

- [x] **ALU Subcircuit**: Modular logic for arithmetic and bitwise operations.
- [x] **Control Unit**: Decodes the 16-bit ROM instructions.
- [x] **Register File**: Manages the storage and retrieval of 4-bit data.
- [x] **Triple-Bus System**: High-speed data paths for Ra, Rb, and Rd.

> [!NOTE]  
> - This CPU is designed as a minimal implementation for **educational purposes**, providing a clear view of how instructions are fetched from ROM and processed through hardware gates. 
> - This README page was prepared with the help of AI (Model: Grok AI).
