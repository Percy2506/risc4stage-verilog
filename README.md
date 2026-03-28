# risc4stage-verilog
A 4-stage pipelined RISC processor (IF-ID-EX-WB) implemented in Verilog HDL and simulated using Cadence Xcelium.
# 4-Stage Pipelined RISC Processor — Verilog HDL

A Register Transfer Level (RTL) implementation of a 4-stage 
pipelined RISC processor designed in Verilog HDL and functionally 
verified using Cadence Xcelium with SimVision waveform analysis.

## Pipeline Stages
- **IF** — Instruction Fetch
- **ID** — Instruction Decode
- **EX** — Execute (ALU)
- **WB** — Write Back

## Supported Instructions
| Opcode | Operation |
|--------|-----------|
| ADD | rd = rs1 + rs2 |
| SUB | rd = rs1 - rs2 |
| AND | rd = rs1 & rs2 |
| OR  | rd = rs1 \| rs2 |
| LOAD | rd = rs1 + imm |
| STORE | addr = rs1 + imm |

## Processor Specifications
- 32-bit datapath
- 32-entry general purpose register file
- 16-entry instruction memory
- Fixed 32-bit instruction encoding format
- Synchronous reset

## Instruction Encoding Format
```
[31:28] opcode | [27:23] rd | [22:18] rs1 | [17:13] rs2 | [12:0] imm
```

## Files
| File | Description |
|------|-------------|
| `risc_4stage.v` | Top-level processor module |
| `tb_risc4stage.v` | Testbench for functional verification |

## Simulation Tool
- **Simulator:** Cadence Xcelium
- **Waveform Viewer:** SimVision
- **Timescale:** 1ps/1ps
- **Clock Period:** 10ps

## How to Run
```bash
# Compile
xrun risc_4stage.v tb_risc4stage.v

# View waveforms
simvision risc4stage.vcd
```

## Expected Results
After pipeline execution the register file should contain:
- r2 = 0x00000008 (ADD result: 5 + 3)
- r3 = 0x00000001 (AND result: 5 & 3)
- r4 = 0x00000007 (SUB result: 10 - 3)
- r5 = 0x00000007 (OR result: 4 | 3)

## Author
Designed and simulated as part of a digital design project
using Cadence Xcelium — 2026.
```

---

**GitHub Topics/Tags to add:**
```
verilog  risc-processor  pipeline  cadence-xcelium  
digital-design  rtl  hdl  computer-architecture  
vlsi  simvision  4-stage-pipeline
