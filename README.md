[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.14997933.svg)](https://doi.org/10.5281/zenodo.14997933)

# Quantum Cloud Simulation Environment

This **Quantum Cloud Simulation** repository is designed for managing and simulating quantum computing workflows. The system simulates the orchestration of quantum jobs across multiple quantum devices, supporting dynamic job generation, resource allocation, and communication between quantum devices.

## ✨ **What This Work Does**
- Simulates quantum job scheduling and execution across multiple quantum devices.
- Provides support for different **allocation modes** (`simple` and `smart`) to optimize job execution.
- Collects and analyzes key performance metrics like:
  - **Fidelity** — Measures the accuracy of quantum operations.
  - **Communication time** — Measures the time spent communicating between devices.
- Plots the fidelity distribution under different allocation modes using **matplotlib**.

---

## 🚀 **How to Run the Simulation**
### 1. **Set Up the Environment**
Make sure you have Python (>=3.8) installed.

Install the required libraries manually using `pip`:

```bash
pip install numpy matplotlib
```


⸻

2. Run the Jupyter Notebook

Start Jupyter and open the provided notebook:
```bash
jupyter notebook GLSVLSI_2025.ipynb

```

⸻

3. Simulation Overview

In the notebook:
  • The simulation runs using job data from a CSV file (synth_job_batches/1000-large-circuits.csv).
  • Jobs are processed using quantum devices:
  • ibm_strasbourg
  • ibm_brussels
  • ibm_kyiv
  • ibm_quebec
  • ibm_kawasaki
  • Example of running a simulation:
```
python
qcloudsimenv = QCloudSimEnv(
    devices=devices,
    broker_class=ParallelBroker,
    job_feed_method="dispatcher",
    file_path="synth_job_batches/1000-large-circuits.csv",
    allocation_mode='smart',
    printlog=True
)
qcloudsimenv.run()
```


⸻

4. Plotting Results

You can visualize the fidelity distribution for different allocation modes using matplotlib:
```
plt.hist(fidelity_list['smart'], bins=10, color='pink', edgecolor='black', alpha=0.7, label='EASM')
plt.xlabel("Fidelity")
plt.ylabel("Frequency")
plt.legend(loc='upper left')
plt.show()
```


⸻

📊 Results and Analysis
  • The simulation logs fidelity and communication time.
  • Fidelity results are plotted and compared under simple and smart allocation modes.
  • Sample output:
```
Allocation mode: smart
Total Sim-time: 1203.45
Fidelity: 0.9123 ± 0.0132
Comm time: 45.32
```


📄 License

This project is licensed under the MIT License.

⸻
