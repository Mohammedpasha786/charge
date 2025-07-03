# 🧠 Asynchronous FIFO Design and Verification – Milestone 1

This project implements the core components of an **Asynchronous FIFO** system in Verilog. Milestone 1 includes the design and verification of:

- ✅ Dual-Port Memory Module  
- ✅ 2 Flip-Flop Synchronizer  
- ✅ Basic Testbenches for both components  


## 📁 Project Structure

async-fifo/
├── src/
│ ├── dual_port_ram.v # Dual-port memory (read/write from two clock domains)
│ └── sync_2ff.v # 2 flip-flop synchronizer for metastability control
├── tb/
│ ├── tb_dual_port_ram.v # Testbench for dual-port memory
│ └── tb_sync_2ff.v # Testbench for flip-flop synchronizer
├── README.md
└── .gitignore

## 📦 Module Descriptions

### 🔄 dual_port_ram.v
A dual-port RAM that supports simultaneous read/write access from two different clock domains (clk_a and clk_b).

### 🔗 sync_2ff.v
A 2-stage flip-flop synchronizer used to transfer control signals safely between asynchronous clock domains.


## 🧪 Testbenches

### ✅ `tb_dual_port_ram.v`
- Writes and reads from separate ports and verifies data consistency.
- Simulates two independent clocks using different periods.

### ✅ `tb_sync_2ff.v`
- Simulates input signal transitions and confirms safe synchronization across clock domains.



## 🛠️ How to Run (Using Icarus Verilog)

```bash
# Compile and run dual port RAM test
iverilog -o tb_dual_port_ram tb/tb_dual_port_ram.v src/dual_port_ram.v
vvp tb_dual_port_ram

# Compile and run synchronizer test
iverilog -o tb_sync_2ff tb/tb_sync_2ff.v src/sync_2ff.v
vvp tb_sync_2ff
