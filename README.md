# UPS Runtime Calculator

A simple Python tool to estimate the backup runtime of a UPS battery system.

This program calculates the estimated backup time based on:

* Load Power (W)
* Battery Capacity (Ah)
* Battery Voltage (V)
* System Efficiency (%)

The result is displayed in minutes along with a simple runtime category.

---

# Features

* Estimate UPS battery runtime
* Simple command line interface
* Runtime classification (Short / Medium / Long)
* Basic input validation
* Easy to modify for real UPS system calculations

---

# Formula

The runtime is calculated using the following steps.

Energy stored in battery:

Energy (Wh) = Battery Voltage × Battery Capacity

Available energy considering efficiency:

Available Energy = Energy × Efficiency

Runtime:

Runtime (hours) = Available Energy / Load Power

Runtime (minutes) = Runtime × 60

---

# Example

Input

Load Power: 500 W
Battery Capacity: 100 Ah
Battery Voltage: 12 V
Efficiency: 85 %

Output

Estimated runtime: 122.40 minutes
Runtime category: Long

---

# How to Run

Run the program using Python:

python main.py

Then enter the required values when prompted.

---

# Example Execution

## UPS 電池備援時間計算器

請輸入負載功率 (W): 500
請輸入電池容量 (Ah): 100
請輸入電池電壓 (V): 12
請輸入系統效率 (%): 85

預估備援時間：122.40 分鐘
備援時間：長

---

# Project Structure

ups-runtime-calculator

main.py
README.md

---

# Requirements

Python 3.x

No external libraries are required.

---

# Future Improvements

Possible upgrades for this tool:

* Battery series / parallel calculation
* Multiple battery strings
* UPS capacity validation
* Export results to CSV
* Web interface version
* UPS sizing assistant

---

# License

This project is open-source and intended for educational and engineering practice.
