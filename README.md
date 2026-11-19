# Verilog 8-bit CPU



A simple 8-bit CPU designed from scratch in Verilog HDL, built module by module with a self-checking testbench for each part.



## Status



Work in progress. Modules are implemented and verified one at a time.



- \[ ] ALU (`rtl/alu.v`)

- \[ ] Register file (`rtl/register\_file.v`)

- \[ ] Program counter (`rtl/program\_counter.v`)

- \[ ] Control unit (`rtl/control\_unit.v`)

- \[ ] CPU top level (`rtl/cpu\_top.v`)

- \[ ] Full CPU testbench (`tb/cpu\_tb.v`)



## Project Structure



```

verilog-8bit-cpu/

├── rtl/              Synthesizable design sources

│   ├── alu.v

│   ├── register\_file.v

│   ├── program\_counter.v

│   ├── control\_unit.v

│   └── cpu\_top.v

├── tb/               Testbenches

│   ├── alu\_tb.v

│   ├── register\_file\_tb.v

│   └── cpu\_tb.v

├── docs/             Design documentation

│   ├── architecture.md

│   └── design\_decisions.md

├── simulation/       Simulation outputs (waveforms, logs)

├── reports/          Reports and results

├── ai-usage-log.md   Record of AI assistance used in the project

├── README.md

└── .gitignore

```



## Tools



Examples below use \[Icarus Verilog](https://steveicarus.github.io/iverilog/) and \[GTKWave](https://gtkwave.sourceforge.net/). Any other Verilog simulator works too.



## Running Simulations



Run these commands from the repository root. Each testbench is compiled together with the module it tests.



```bash

# ALU

iverilog -o simulation/alu\_tb.vvp tb/alu\_tb.v rtl/alu.v

vvp simulation/alu\_tb.vvp



# Register file

iverilog -o simulation/register\_file\_tb.vvp tb/register\_file\_tb.v rtl/register\_file.v

vvp simulation/register\_file\_tb.vvp



# Full CPU

iverilog -o simulation/cpu\_tb.vvp tb/cpu\_tb.v rtl/\*.v

vvp simulation/cpu\_tb.vvp

```



To view waveforms, have the testbench write a `.vcd` file into `simulation/`, then open it:



```bash

gtkwave simulation/<name>.vcd

```



Simulation outputs (`\*.vvp`, `\*.vcd`, `\*.fst`, `\*.out`, `\*.log`) are ignored by Git.



## Documentation



- \[Architecture](docs/architecture.md): block diagram, datapath and instruction set

- \[Design decisions](docs/design\_decisions.md): the reasoning behind key design choices



## AI Usage



AI assistance used during this project is recorded in \[ai-usage-log.md](ai-usage-log.md).



## Author



<Akasha Withanage>



