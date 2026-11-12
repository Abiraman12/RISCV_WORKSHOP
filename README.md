# RISCV_Practice

RTL designs, testbenches, simulation models, and verification waveforms for RISC-V and digital building blocks.

---

## Day 1 – RTL Building Blocks and Self-Checking Verification

- **1.1 Parameterized ALU**: 32-bit parameterized ALU supporting ADD, SUB, AND, OR, XOR, SLT, SLL, SRL with Zero, Negative, Carry, and Overflow status flags.
- **1.2 Up/Down Counter**: Synchronous parameterized up/down counter with load, enable, and clear controls.
- **1.3 Barrel Shifter**: Multi-bit bidirectional barrel shifter (logical left, logical right, arithmetic right).
- **1.4 Register File**: 32x32-bit multi-port register file with two asynchronous read ports and one synchronous write port (x0 hardwired to 0).
- **1.5 Ripple-Carry Adder/Subtractor**: Parameterized ripple-carry adder/subtractor with overflow and carry-out detection.
- **1.6 Priority Encoder and Decoder**: Parameterized priority encoder and binary decoder modules.
- **1.7 LFSR and Shift Register**: Linear Feedback Shift Register (pseudo-random sequence generator) and multi-mode shift register (SISO, SIPO, PISO, PIPO).
- **1.8 Edge Detector and Debouncer**: Positive/negative/dual edge detector with clock divider and debouncer unit.
