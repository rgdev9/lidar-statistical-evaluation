# lidar-statistical-evaluation
# Statistical Error Modeling of Depth Sensors

This repository contains the data collection, statistical analysis, and mathematical modeling pipeline developed for my Bachelor Thesis. It evaluates the distance and intensity measurement accuracies of various depth sensors (LiDAR, Time-of-Flight) across different materials and incident angles.

### 🎯 Key Contributions
* **Automated Data Collection:** Developed ROS nodes in Python and C++ to interface with SICK/LDS LiDARs and Kinect v2 ToF cameras, extracting real-time range and intensity data.
* **Statistical Modeling:** Engineered a Python evaluation engine (`lidar.py`, `intensity.py`) using `SciPy` and `lmfit` to fit complex error models (Polynomial, Gaussian, and oscillating sinusoidal functions) to sensor noise profiles.
* **Material Calibration:** Calculated intensity scaling factors and offsets for varying target materials (e.g., aluminium, black/white/grey paper) at angles ranging from 0° to 85°.

### ⚙️ System Architecture & Tools
* **ROS Setup:** Subscribes to `/scan2` and `/kinect2/sd/image_depth` topics.
* **Data Processing:** `numpy`, `scipy`, `statsmodels`, `scikit-learn`.
* **Metrics:** Evaluated models using Mean Squared Error (MSE), Weighted MSE, and Bayesian Information Criterion (BIC).

### 🚀 Usage
**1. Data Collection (ROS)**
Launch the ROS core and the sensor nodes, then run the collection scripts:
```bash
python3 data_collection/recordLDS.py
