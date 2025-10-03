# 🚀 VLSI RISC-V SoC Tapeout — Week 1: RTL Simulation & Synthesis

## 📅 Duration
**Week 1:** 20/09/2025 – 27/09/2025  
**Program:** VSD RISC-V Reference SoC Tapeout

## 🎯 Objective
Explore RTL design, simulation, synthesis, and gate-level validation using open-source tools. Understand how Verilog maps to hardware and how synthesis optimizations affect logic and timing.

## 🧰 Tools Used
- **Yosys** – RTL synthesis
- **Icarus Verilog** – Simulation
- **GTKWave** – Waveform visualization
- **SKY130 PDK** – Technology library

---

## 📚 Day-Wise Summary with Commands

### 🗓️ Day 1: RTL Design Basics
- ✅ Designed 2:1 MUX and D Flip-Flop
- ✅ Created testbenches for simulation
- ✅ Synthesized using Yosys

**Commands:**
```bash
# Simulate RTL
iverilog -o mux_tb.out mux.v mux_tb.v
vvp mux_tb.out
gtkwave dump.vcd

# Synthesize RTL
yosys
> read_verilog mux.v
> synth -top mux
> show





### 🗓️ Day 2: Hierarchical synthesis

yosys
> read_verilog top.v submodule.v
> synth -top top
> show








### 🗓️ Day 3: Optimization pass




yosys
> read_verilog design.v
> opt
> show




### 🗓️ Day 4: Generate netlist



yosys
> read_verilog dff.v
> synth -top dff
> write_verilog dff_netlist.v

# Simulate netlist
iverilog -o dff_gls.out dff_netlist.v dff_tb.v
vvp dff_gls.out
gtkwave dump.vcd

### 🗓️ Day 5: Synthesize conditional logic





yosys
> read_verilog conditional.v
> synth -top conditional
> show

# Simulate loop constructs
iverilog -o loop_tb.out loop.v loop_tb.v
vvp loop_tb.out
gtkwave dump.vcd
