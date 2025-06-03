# battery-soc-estimation  

Battery State of Charge (SoC) Estimation and Visualization

This project performs **State of Charge (SoC) estimation** of a battery using real current-time data from an eVTOL battery dataset. The estimation is done by numerically integrating the current over time — a technique commonly referred to as **Coulomb Counting**.

The output is a combined plot showing:
- SoC during **charging** and **discharging** phases
- Corresponding **current profile** over time

---

## Output Plot

![SoC Plot](images/soc_and_current_plot.png)  
*Figure: SoC and Current Profile during Battery Charge/Discharge Cycle*

---

## Plot Interpretation

The plot titled **"SoC and Current Profile during Battery Charge/Discharge Cycle"** presents two main aspects of the battery cycle:

* **Green Line (Charging SoC)**: The battery's State of Charge (SOC) rises smoothly from 0% to nearly 100%. This increase reflects the integration of the positive charging current over time.

* **Red Line (Discharging SoC)**: After a brief rest, the battery begins discharging. The SOC decreases as current flows out of the battery, again calculated through time integration of the (now negative) current.

* **Blue Line (Current)**: The charging process starts with a relatively high and stable current (~1.5 A), characteristic of a **Constant Current (CC)** phase. Around **90% SOC**, the current begins to drop. This behavior likely indicates a transition to a **Constant Voltage (CV)** phase — a typical step in lithium-ion battery charging, where the voltage is held constant and the current gradually tapers off as the battery approaches full charge. Although voltage data is not shown, the current trend suggests that this transition may have occurred. After a short resting period with near-zero current, the current turns negative, indicating the start of the **discharge phase**, which appears to be driven by a relatively steady current draw (~0.6 A).

---

## What This Project Demonstrates

- How to estimate battery SoC from time-series current data using integration.
- How to detect charging vs discharging phases automatically based on current polarity.
- How to visualize dual-axis data (SoC and Current) for better interpretability.

---

## Dataset Source

The current and voltage data used in this project is from Carnegie Mellon University's open-source eVTOL Battery Dataset:

📥 [eVTOL Battery Dataset on CMU Kilthub](https://kilthub.cmu.edu/articles/dataset/eVTOL_Battery_Dataset/14226830)

---

## Author Notes

This notebook was developed and run in **VS Code** using a `.ipynb` file. It is a practical example of battery signal processing and numerical estimation.
