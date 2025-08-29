# DP_Scheduling in Litmus-RT
<img width="1052" height="797" alt="image" src="https://github.com/user-attachments/assets/12bf9521-0bb1-42f3-90de-ef7e73ac5bb5" />

This repository contains research and implementation related to **Dual Priority Scheduling (DP_Scheduling)** within the [Litmus-RT](https://github.com/LITMUS-RT/litmus-rt) framework. The project explores how **Dual Priority Scheduling** can enhance the **predictability, efficiency, and performance** of real-time systems.

---

## 📌 Overview

Real-time systems require predictable and efficient scheduling to guarantee timing constraints. **Dual Priority Scheduling (DP_Scheduling)** is a fixed-priority algorithm that dynamically changes task priorities between two levels (high and low).  

By integrating DP_Scheduling into **Litmus-RT**, this research investigates:
- Improved schedulability analysis
- Reduced response times for critical tasks
- Enhanced overall system utilization
- Practical feasibility on Linux-based real-time platforms

---

## 🛠 Features

- ✅ Implementation of **Dual Priority Scheduling** in Litmus-RT  
- ✅ Support for periodic and sporadic task models  
- ✅ Comparative evaluation against existing Litmus-RT scheduling policies (e.g., EDF, FP)  
- ✅ Benchmarking and performance analysis with synthetic workloads  
- ✅ Documentation of experimental results  

---

## 🔧 Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/csislam/DP_Scheduling.git
   cd DP_Scheduling
Ensure you have Litmus-RT installed and patched kernel. Refer to the Litmus-RT setup guide.

Apply the DP_Scheduling patch:

bash
Copy code
patch -p1 < dp_scheduling.patch
Rebuild and install the kernel:

bash
Copy code
make
sudo make install
🚀 Usage
Configure your real-time tasks using Litmus-RT APIs.

Select DP_Scheduling as the scheduling policy:

bash
Copy code
sudo setsched dp_scheduling <pid>
Run experiments with tasksets and measure performance metrics.

Example:

bash
Copy code
sudo ./run_experiment.sh --policy dp_scheduling --tasks taskset.json

📊 Research Contributions
Theoretical Analysis: Explored the schedulability guarantees of Dual Priority Scheduling.

Implementation: Extended Litmus-RT to support DP_Scheduling.

Experiments: Benchmarked performance improvements compared to EDF and FP scheduling.

Results: Showed measurable improvements in response times and deadline adherence under high load.

📄 Project Structure
bash
Copy code
DP_Scheduling/

│── src/                  # Source code for DP_Scheduling integration

│── patches/              # Kernel patches for Litmus-RT

│── experiments/          # Scripts & configs for benchmarking

│── docs/                 # Research documentation & notes

│── results/              # Experimental outputs and analysis

│── README.md             # Project overview (this file)

📚 References
Burns, A., & Wellings, A. J. (1993). Dual Priority Scheduling: A Practical Method for Achieving Predictable Real-Time Systems.
