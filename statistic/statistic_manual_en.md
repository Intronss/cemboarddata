## Statistic User Manual

### Introduction

The Statistic module focuses on **numerical analysis** of 3D voxel box data.  
It provides several methods to compute value distributions and neighborhood-based statistics and exports the results as Excel files for further analysis.

All statistic tasks are based on a box file (flattened 3D data) and box dimensions: `length`, `width`, and `height`.  

### Data Preparation

#### Box Data Format

- **File format**: Text file (`.txt`).
- **Data layout**: One column of numbers, representing a flattened 3D array with size `length × width × height`.

#### Box Dimension Parameters

You must specify:

- **Length**: Number of grid points along the X axis.
- **Width**: Number of grid points along the Y axis.
- **Height**: Number of grid points along the Z axis.

The number of values in the box file must equal `length × width × height`.

---

## Statistic Methods

The module currently supports three main methods:

- **box_statistic**: Global value distribution statistics.
- **positive_sum**: Aggregate statistics for positive values.
- **adjacent_positive_sum**: Neighborhood-based statistics around negative voxels.

For each method, the user specifies:

- **Statistic Name**: Task name, used as the folder name under `media/statistic/`.
- **Box File**: Input `.txt` file containing flattened box values.
- **Length / Width / Height**: 3D box dimensions.
- **Method**: One of the three methods listed above.

---

- After the task is **completed**, you can:
  - Preview the first few rows of the generated Excel file (if implemented),
  - Download all outputs as a zipped archive from the UI.

