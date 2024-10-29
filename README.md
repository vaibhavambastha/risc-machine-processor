# RISC Machine

This project implements a Reduced Instruction Set Computer (RISC) machine architecture using synthesizable Verilog HDL. The design focuses on modular components, pipelined instruction execution, and performance optimization. Key features include a full datapath with instruction memory, register management, and memory-mapped I/O, simulating a range of ARMv7 operations.

## Key Components

### 1. Core Architecture
- **Arithmetic Logic Unit (ALU)**: Supports essential arithmetic and logical operations, including addition, subtraction, and comparison (CMP).
- **Register File**: Manages a set of general-purpose registers with read and write capabilities for fast instruction execution.
- **Instruction Decoder**: Translates binary instructions into control signals. Supports ARMv7 instructions such as `CMP`, `SUB`, `LDR`, and `STR`.
- **CPU Controller**: A finite-state machine (FSM) that manages the fetch, decode, execute, memory access, and write-back stages of instruction execution.
- **RAM**: A memory module that holds both instructions and data, with an interface for memory-mapped I/O, allowing interaction with external devices.

### 2. Data Path and Pipelining
- **Data Path**: Implements efficient data movement between components like the ALU, register file, and RAM. The data path enables smooth instruction execution through each pipeline stage.
- **Instruction Pipelining**: The CPU is pipelined to optimize performance across instruction fetch, decode, execute, memory access, and write-back stages. Pipeline hazards are minimized to ensure seamless data flow and improved instruction throughput.

### 3. Supported ARMv7 Operations
- **Arithmetic and Logic Operations**: Supports instructions like `CMP` (compare) and `SUB` (subtract) for logical and arithmetic processing.
- **Memory Operations**: Implements `LDR` (load) and `STR` (store) to allow data movement between the CPU and memory.
- **Control Operations**: Includes `HALT` to stop program execution, facilitating controlled termination of instruction processing.

## Testing and Verification

- **Verilog Test Benches (ModelSim)**: Developed extensive test benches to simulate the RISC machine's instruction execution in ModelSim. These tests verify the reliability of each instruction, ensuring correctness across the instruction set.
- **DE1-SoC FPGA Deployment**: Synthesized the RISC design onto the DE1-SoC FPGA board. Utilized board LEDs and switches for output display and debugging, confirming functionality in hardware.
- **Assembler for Instruction Testing**: Used assembler to convert assembly code into machine code, which can be loaded into memory for testing. This enables efficient unit testing of each instruction within the memory system.
