# Particle Placement User Manual

## Introduction

Particle Placement is a three-dimensional particle placement module that randomly places particles in a three-dimensional box of specified dimensions while avoiding collisions between particles. The module supports generating particle configurations based on particle size distributions and probability densities.

## Data Preparation

### Data Format Requirements

- **File format**: Excel file (`.xlsx`)
- **Required columns**:
  - **Size**: Particle size (diameter)
  - **Probability**: Probability of particles of this size (relative values, automatically normalized by the system)
- **Optional columns**:
  - **id**: Particle type identifier (integer, used to distinguish different types of particles)

### File Format Example

| Size | Probability | id |
|------|-------------|-----|
| 0.5  | 10          | 1   |
| 1.0  | 20          | 1   |
| 1.5  | 15          | 2   |
| 2.0  | 25          | 2   |

## Parameter Configuration

### Task Configuration

- **Placement Name**: Name of the placement task; all related files will be stored in a folder with this name.

### Basic Parameters

- **Length**: Length of the box (default: 50).
- **Width**: Width of the box (default: 50).
- **Height**: Height of the box (default: 50).
- **Min1**: Minimum particle size (default: 0.5), used to filter particle data.
- **Max1**: Maximum particle size (default: 5), used to filter particle data.

### Density Parameters

- **Ab_rho**: Absolute density (default: 4.5), used to calculate solid particle volume.
- **Un_rho**: Relative density (default: 1.06), used to calculate solid particle volume.

### File Upload

- **Particle File (required)**: Excel file containing particle size and probability distributions.

## Output Files

After placement is completed, the following files will be generated in the `media/particle_placement/[placement_name]/` directory:

- **box.txt**: Final three-dimensional box data file (flattened one-dimensional array containing length × width × height values).
- **box_pre.txt**: Intermediate result file from Step 1, containing position information for all particles (diameter, x, y, z coordinates, and optional id).
- **Particle.xlsx**: Backup of the uploaded particle file.
- **parameters.json**: Placement parameter configuration file containing all input parameters.
