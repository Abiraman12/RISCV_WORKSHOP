# RISCV_Practice

Verilog RTL designs, RISC-V processor microarchitectures, testbenches, simulation models, and verification waveforms for digital building blocks and RISC-V cores.

---

## Repository Structure & Modules

### Day 1 – RTL Building Blocks and Self-Checking Verification
- **1.1 Parameterized ALU**: 32-bit parameterized ALU supporting ADD, SUB, AND, OR, XOR, SLT, SLL, SRL with Zero, Negative, Carry, and Overflow status flags.
- **1.2 Up/Down Counter**: Synchronous parameterized up/down counter with load, enable, and clear controls.
- **1.3 Barrel Shifter**: Multi-bit bidirectional barrel shifter (logical left, logical right, arithmetic right).
- **1.4 Register File**: 32x32-bit multi-port register file with two asynchronous read ports and one synchronous write port (x0 hardwired to 0).
- **1.5 Ripple-Carry Adder/Subtractor**: Parameterized ripple-carry adder/subtractor with overflow and carry-out detection.
- **1.6 Priority Encoder and Decoder**: Parameterized priority encoder and binary decoder modules.
- **1.7 LFSR and Shift Register**: Linear Feedback Shift Register (pseudo-random sequence generator) and multi-mode shift register (SISO, SIPO, PISO, PIPO).
- **1.8 Edge Detector and Debouncer**: Positive/negative/dual edge detector with clock divider and debouncer unit.

---

### Day 2 – FSM Controllers and Memory Design
- **2.1 Sequence Detector**: Overlapping and non-overlapping Moore/Mealy sequence detectors (detecting `1011`).
- **2.2 Vending Machine Controller**: FSM supporting multiple coin denominations, item dispense, and exact change return.
- **2.3 Synchronous FIFO**: Dual-port synchronous FIFO with parameterized depth and width, status flags (full, empty, almost-full, almost-empty).
- **2.4 Design Review**: Formal FSM analysis preventing latches, ensuring complete state coverage and glitch-free outputs.
- **2.5 Traffic Light with Pedestrian Request**: Traffic light controller with green/yellow/red timing intervals and pedestrian crosswalk interrupt.
- **2.6 ATM Controller with PIN and Balance**: Secure ATM state machine handling PIN verification, card validation, withdrawal, and balance check.
- **2.7 Round-Robin Arbiter**: Parameterized fair arbiter ensuring starvation-free access among competing bus requestors.
- **2.8 RAM, ROM and Watchdog Timer**: Single-port RAM, synchronous ROM, and system watchdog timer with auto-reset functionality.

---

### Day 3 – Extending the Single-Cycle RISC-V CPU
- **3.1 Instruction Extensions**: RV32I immediate arithmetic, logical, and shift extensions (`ANDI`, `ORI`, `XORI`, `SLTI`, `SLLI`, `SRLI`, `LUI`, `JAL`).
- **3.2 Assembly Programs**: Test programs including Sum of 1 to N, Array Search, and Factorial calculation.
- **3.3 Self-Checking CPU Testbench**: Automated testbench checking register write-back values, PC progression, and memory contents.
- **3.4 Waveform Analysis**: Detailed timing waveforms highlighting instruction fetch, decode, execute, memory, and write-back phases.
- **3.5 Branch and Jump Extensions**: Conditional branching (`BEQ`, `BNE`, `BLT`, `BGE`) and unconditional jumps (`JAL`, `JALR`).
- **3.6 More Assembly Programs**: Sorting algorithms, GCD, and shift-and-add multiplication benchmarks.
- **3.7 Instruction Coverage Matrix**: Comprehensive verification matrix ensuring all opcode formats (R, I, S, B, U, J) are executed.
- **3.8 Bug-Hunt Exercise**: Fault injection analysis verifying testbench diagnostics against sign-extension bugs, x0-write violations, and incorrect branch offsets.

---

### Day 4 – Pipeline Hazards, Analysis and Submission
- **4.1 Data Hazard Handling**: Hazard detection unit and EX/MEM, MEM/WB operand forwarding to eliminate RAW stalls.
- **4.2 Control Hazard Handling**: Branch resolution, branch penalty mitigation, and pipeline flush control.
- **4.3 Performance Comparison**: CPI and cycle count comparison between Single-Cycle and Pipelined architectures.
- **4.5 Hazard Waveform Report**: Waveform traces documenting hazard detection flags, forwarding multiplexer selects, and stall assertions.
- **4.6 Performance Counters**: Hardware cycle counters, retired instruction counters, stall counters, and branch misprediction counters.
- **4.7 Extended Program Runs**: Benchmark execution (Bubble Sort, GCD, Shift-Add Multiplier) analyzing CPI and stalls.
- **4.8 Architecture Diagram and Demo**: Block diagram documentation and demo showing 5-stage pipeline operation.

---

## How to Run Simulations Using ModelSim

1. **Open ModelSim** and navigate to any module directory:
   ```tcl
   cd "path/to/activity"
   ```
2. **Create Working Library**:
   ```tcl
   vlib work
   vmap work work
   ```
3. **Compile Verilog Source & Testbench**:
   ```tcl
   vlog <design_file>.v <testbench_file>.v
   ```
4. **Start Simulation**:
   ```tcl
   vsim work.<testbench_module_name>
   ```
5. **Add Waveforms and Run**:
   ```tcl
   add wave -r *
   run -all
   wave zoomfull
   ```
