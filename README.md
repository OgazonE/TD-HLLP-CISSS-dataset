# TD-HLLP-CISSS-dataset

## Overview

This dataset supports the numerical analysis presented in the paper *Time-Definite Hub Line Location Problem (TD-HLLP)*. The instances are designed for use in solving the TD-HLLP, an optimization problem that focuses on designing efficient, time-sensitive hub-line transportation networks. These instances were inspired by real regional healthcare logistics networks in the province of Quebec.

## Files in the Dataset

The dataset consists of several `.csv` files organized in the `HLLP_Dataset` folder:

### 1. **Instance Data Files**
Each instance data file includes:
- **Time Matrix Files (e.g., `I_01_time.csv` to `I_20_time.csv`)**: Contains the origin-destination travel time in minutes between all nodes.
- **Distance Matrix Files (e.g., `I_01_distance.csv` to `I_20_distance.csv`)**: Contains the calculated origin-destination travel distance in kilometers between all nodes, based on a travel speed of 70 km/h.

### 2. **Supplementary Lists**
- **`instance_list.csv`**: Lists the instance identifiers (1 to 20) used in the analysis.
- **`p_list.csv`**: Lists the number of hubs (3, 4, 5) considered in the experiments.
- **`T_list.csv`**: Lists the service levels in minutes (from 60 to 720, in increments of 60) used to evaluate network performance.

## Data Structure

### Time Matrix Files (`I_XX_time.csv`)
- **Format**: Each file contains an N x N matrix, where N is the number of nodes in the instance.
- **Rows and Columns**: Both represent nodes in the network, labeled from 1 to N.
- **Entries**: The travel time (in minutes) between the origin node (row) and the destination node (column).

### Distance Matrix Files (`I_XX_distance.csv`)
- **Format**: Each file contains an N x N matrix, with the same structure as the time matrix files.
- **Entries**: The travel distance (in kilometers) calculated using a travel speed of 70 km/h.

### Instance List (`instance_list.csv`)
- **Content**: A single-column file listing the instance numbers from 1 to 20.

### Number of Hubs (`p_list.csv`)
- **Content**: A single-column file listing the different values for the number of hubs (p = 3, 4, 5) used in the experiments.

### Service Levels (`T_list.csv`)
- **Content**: A single-column file listing the different service level constraints (in minutes) used in the experiments.

## Instance Generation Details

- The time matrices were imported from CSV files that describe the travel times between nodes in minutes.
- Distance matrices were derived from time matrices using the formula: 
  \\
  \[
  \text{Distance (km)} = \\frac{\text{Time (min)}}{60} \\times 70 \text{ km/h}
  \\
  \]
- All matrices were saved in `.csv` format with headers and indices to facilitate easy integration into optimization solvers.

