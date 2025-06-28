
# Visual-Inertial Odometry using Stereo MSCKF

This project implements a Visual-Inertial Odometry (VIO) system based on the Stereo Multi-State Constraint Kalman Filter (S-MSCKF).  
The system extends the mathematical framework of the original MSCKF to handle stereo camera setups, improving depth estimation robustness.

---

## Project Structure

- `vio.py`: Main entry point for running the VIO pipeline.
- `modules/`: Contains core modules for IMU propagation, feature tracking, state augmentation, and measurement update.
- `pangolin_viewer/`: Visualization module using Pangolin for real-time trajectory and feature display.
- `EuRoC_parser/`: Dataset loader for EuRoC MAV dataset format.

---

## Setup Instructions

### 1. Dataset Preparation

- Download the [EuRoC MAV Dataset](https://projects.asl.ethz.ch/datasets/doku.php?id=kmavvisualinertialdatasets).
- Extract the dataset and note the path.

Example path:
```
path/to/your/EuRoC_MAV_dataset/MH_01_easy/
```

### 2. Install Python Requirements

Install required Python packages:
```bash
pip install numpy scipy
```

### 3. (Optional) Install Pangolin for Visualization

Pangolin is used for real-time visualization of the trajectory and features.

#### Option 1: Install via pip
```bash
pip install pangolin
```

#### Option 2: Install from source (recommended if pip version fails)
```bash
# Install system dependencies
sudo apt-get install libglew-dev libboost-dev libboost-thread-dev libboost-filesystem-dev

# Clone Pangolin repository
git clone https://github.com/stevenlovegrove/Pangolin.git
cd Pangolin

# Build and install Pangolin
mkdir build
cd build
cmake ..
cmake --build .
sudo make install
```

> After Pangolin is installed, you can use `--view` option to enable live visualization.

---

## Running the VIO Pipeline

Navigate to the project folder where `vio.py` is located:

```bash
cd /path/to/your/project_folder/
```

### To run with visualization:
```bash
python vio.py --view --path path/to/your/EuRoC_MAV_dataset/MH_01_easy
```

### To run without visualization:
```bash
python vio.py --path path/to/your/EuRoC_MAV_dataset/MH_01_easy
```

> Replace `path/to/your/EuRoC_MAV_dataset/MH_01_easy` with your actual dataset path.

---
