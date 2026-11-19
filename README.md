# Verilog 8-bit CPU

A simple 8-bit CPU designed from scratch in Verilog HDL, built module by module with a self-checking testbench for each part.

## Status

**Work in progress.** Modules are implemented and verified one at a time.

- [ ] ALU (`rtl/alu.v`)
- [ ] Register file (`rtl/register_file.v`)
- [ ] Program counter (`rtl/program_counter.v`)
- [ ] Control unit (`rtl/control_unit.v`)
- [ ] CPU top level (`rtl/cpu_top.v`)
- [ ] Full CPU testbench (`tb/cpu_tb.v`)

## Project Structure

```text
verilog-8bit-cpu/
│
├── rtl/                  # Synthesizable design sources
│   ├── alu.v
│   ├── register_file.v
│   ├── program_counter.v
│   ├── control_unit.v
│   └── cpu_top.v
│
├── tb/                   # Testbenches
│   ├── alu_tb.v
│   ├── register_file_tb.v
│   └── cpu_tb.v
│
├── docs/                 # Design documentation
│   ├── architecture.md
│   └── design_decisions.md
│
├── simulation/           # Simulation outputs (waveforms, logs)
├── reports/              # Reports and results
│
├── ai-usage-log.md       # Record of AI assistance used
├── README.md
└── .gitignore
```

## Tools

The project uses the following tools:

- [Icarus Verilog](https://steveicarus.github.io/iverilog/) – Verilog compilation and simulation.
- [GTKWave](https://gtkwave.sourceforge.net/) – Simulation waveform visualization.

Other Verilog-compatible simulators may also be used.

## Running Simulations

Run the following commands from the repository root. Each testbench is compiled together with the module it tests.

The following examples assume that the corresponding Verilog modules and testbenches have been implemented.

```bash
# ALU
iverilog -o simulation/alu_tb.vvp tb/alu_tb.v rtl/alu.v
vvp simulation/alu_tb.vvp

# Register file
iverilog -o simulation/register_file_tb.vvp tb/register_file_tb.v rtl/register_file.v
vvp simulation/register_file_tb.vvp

# Full CPU
iverilog -o simulation/cpu_tb.vvp tb/cpu_tb.v rtl/*.v
vvp simulation/cpu_tb.vvp
```

To view simulation waveforms, configure the testbench to generate a `.vcd` file in the `simulation/` directory, then open it using:

```bash
gtkwave simulation/<name>.vcd
```

Note: The `simulation/` directory must exist before running these commands.

Simulation outputs (`*.vvp`, `*.vcd`, `*.fst`, `*.out`, `*.log`) are ignored by Git.

## Documentation

- [Architecture](docs/architecture.md) – Block diagram, datapath and instruction set.
- [Design Decisions](docs/design_decisions.md) – Reasoning behind key design choices.

## AI Usage

AI assistance used during this project is documented in [ai-usage-log.md](ai-usage-log.md).

## Author

**Akasha Withanage**

---

*An educational project exploring digital logic design, computer architecture, Verilog HDL and hardware verification.*