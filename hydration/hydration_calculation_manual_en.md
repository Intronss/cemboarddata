## Hydration Calculation User Manual

---

### Example: 5-step C3S hydration using the built-in `box.txt`

#### Required

- **Project Name** (field: `hydration_name`)
  - Example: `hydration_example`
- **Step Time (s)** (field: `step_time`)
  - Default: `1.0`
  - Range: 0.1–10 seconds
  - Note: the same step time is used for **all 5 steps**
- **Hydration Rates (5 steps)** (fields: `rate1` … `rate5`)
  - Default for each: `0.01`
  - Constraints: each rate must be **> 0**, and `rate1+...+rate5 <= 1`
  - Example:
    - `rate1=0.01, rate2=0.01, rate3=0.01, rate4=0.01, rate5=0.01`

#### Optional (leave blank to use defaults)

- **Material Densities (g/cm³)** (density overrides)
  - `density_C3S` (default 3.15)
  - `density_CSH1` (default 2.60)
  - `density_CH` (default 2.211)
  - `density_H2O` (default 0.9982)

- **CH Ksp** (field: `ksp_CH`, default `5.5e-6`)
  - Must be a positive number

---

### Outputs

#### Step-wise outputs (5 steps)

- `step01_C3S_box.txt` … `step05_C3S_box.txt`
- `step01_H2O_box.txt` … `step05_H2O_box.txt`
- `step01_C_S_H_box.txt` … `step05_C_S_H_box.txt`
- `step01_CH_box.txt` … `step05_CH_box.txt`
- `step01_pore_box.txt` … `step05_pore_box.txt`

Note: all files are saved as **flattened 1D columns** (text format), ready for post-processing and visualization.
