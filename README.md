# Temperature Control with PID Simulation

A thermal control loop and signal processing architecture programmed on a **Siemens S7-1200 (CPU 1215C)** using **TIA Portal**. 

### 🌡️ Project Highlights
* **Analog Signal Normalization:** Utilized `NORM_X` and `SCALE_X` blocks to convert raw peripheral analog inputs (`%MW64`, 0-27648) into physical engineering units (0-100°C).
* **Dynamic PWM Control:** Derived thermal error (`Error = |Setpoint - Actual|`) using `CALCULATE` and `ABS` blocks. Programmed an `IN_RANGE` 50% PWM duty-cycle loop (5s ON / 5s OFF via `TP`/`TOF` timers) to prevent thermal overshoot.
* **Live Signal Filtering:** Built a 1-second sampling loop using positive edge detection and a 5-sample FIFO shift-register array (`MOVE` blocks) to calculate a rolling average for sensor noise smoothing.

### 📂 Repository Files
* **Temperature_Control_Logic.pdf:** PDF export of the Main OB1 ladder logic.
* **Network_Screenshots:** Visual captures of the analog scaling and PWM ladder networks.
* **Temperature_Control.zap15:** Raw TIA Portal V15 archive file.
