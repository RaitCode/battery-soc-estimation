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

- **Green Line (Charging SoC)**: The SOC begins at 0% and increases almost linearly during charging, reflecting a steady positive current (~1.5 A). The SOC reaches nearly 100%, indicating full charge.
- **Blue Line (Current)**: The charging process begins with a relatively high and stable current (~1.5 A), characteristic of a Constant Current (CC) phase. Around 90% State of Charge (SoC), the current begins to drop gradually. This drop likely indicates a transition to a Constant Voltage (CV) phase — a typical behavior in lithium-ion battery charging, where the voltage is held steady and the current tapers off as the battery nears full charge. While the voltage data isn’t shown here, the current profile suggests that such a transition may have occurred. Following a short resting phase, the current turns negative, marking the beginning of the discharge phase, which appears to proceed at a relatively constant current draw (~ -0.6 A).
- **Red Line (Discharging SoC)**: After charging completes, SoC begins to decrease linearly, driven by a relatively constant negative current (~ -0.6 A). The SOC falls from 100% down to nearly 0% as the battery discharges.
- The sharp drop in current during the transition from charge to discharge, and the consistency of the current during both phases, illustrate a well-controlled test environment.

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
