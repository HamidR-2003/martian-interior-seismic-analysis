# martian-interior-seismic-analysis
Seismic analysis of Mars' interior using NASA InSight data, machine learning, and 3D simulation. Confirms liquid core via P/S wave shadow zones and PINN-based modeling

This repository contains all notebooks that perform various data analyses and computational tasks for the analysis of the Martian Core and Seismic data. Each notebook is focused on a specific topic or methodology. Below is a summary of the actions performed and the analysis conducted in each notebook. 

### 1. Signal_processing.ipynb
This notebook focuses on signal processing techniques for analyzing the seismic data which is time-series wave-like data. The key actions include:
- **Signal Loading**: Time-series data was imported and preprocessed from the .mseed files using the Obspy Library.
- **Filtering**: Various filters (e.g., bandpass) were applied to denoise the signal and remove instrumental errors (like spikes).
- **Fourier Analysis**: The frequency components of the signal were extracted using Fast Fourier transforms.
- **Time-Frequency Analysis**: Techniques like wavelet transform were used to analyze signal behavior over time.
- **Visualization**: Spectrograms and time-domain plots were generated to interpret the results.
- **Synthetic Data Simulation**: Synthetic waveforms were generated from the available seismic data for shadow and non-shadow zones. 
- **Supervised ML to classify the Seismic Data**: Logistic Regression was applied to various features obtained from the seismic data to predict whether it is a shadow zone or non-shadow zone.

### 2. Core_radius.ipynb
This notebook focuses on analyzing and determining the core radius of Mars in a dataset. The following steps were performed:
- **Martian Interior Simulation**: Parameters were researched and assumed from various sources and extensive calculations were performed to model the P wave and S wave velocity and the density as a function of depth.
- **Datasets**: The model was compared with the other pre-existing datasets which simulate the P and S wave velocities and Denisty in the Martian Interior.
- **Feature Engineering**: Features like P and S wave velocities and density were separated.
- **Predictive Analysis**: Algorithms like Random Forest were applied to calculate the optimal core radius.
- **Visualization**: Scatter plots to visualize the predicted and actual radius.

### 3. DBSCAN_anomaly.ipynb
This notebook applies the DBSCAN algorithm for anomaly detection in seismic waveform data. Steps include:
- **Introduction to DBSCAN**: A brief overview of how DBSCAN works for clustering and anomaly detection.
- **Dataset Preprocessing**: Amplitude, Frequency, and Phase of the waveforms were separated for individual analysis of anomalies that might be caused by subsurface geological features. The dataset was normalized to improve algorithm efficiency.
- **Parameter Tuning**: Parameters such as `eps` and `min_samples` were adjusted to optimize clustering performance.
- **Anomaly Detection**: Points flagged as anomalies in the amplitude, frequency, and phase plots were visualized and analyzed.

### 4. PINN.ipynb
This notebook implements a Physics-Informed Neural Network (PINN) using a Gaussian Process Neural Network (GPNN) for solving partial differential equations (PDEs) of the P and S waves and mapping them as a function of depth. Highlights include:
- **Physics-Informed Modeling**: Derivation of PDEs and incorporation of physical laws into the neural network structure.
- **Network Design**: Implementing a Gaussian process neural network with PDE loss function.
- **Training and Optimization**: Loss functions were defined to minimize errors in satisfying the physical laws (PDE loss) and boundary conditions (MSE loss).
- **Validation**: Results were validated against analytical or numerical solutions.
- **Visualization**: The solution was visualized using 2D and 3D plots.

## 3D Simulation
The 3D Simulation and the Scientific Functions were performed using [Axisem](https://github.com/geodynamics/axisem) and [SPECFEM3D](https://github.com/SPECFEM/specfem3d) software. The output files are available at the drive link: [3D](https://drive.google.com/drive/folders/1f6Yw_9uvb4SSX5ZxO301iHiITmPXuOnR?usp=drive_link) these files can be opened on PARAVIEW. 

## How to Use
1. Clone the repository: `git clone https://github.com/HamidR-2003/martian-interior-seismic-analysis.git`
2. Install dependencies: Ensure Python and Jupyter Notebook are installed along with necessary libraries `pip install -r requirements.txt`.
4. Follow the steps in the notebook to reproduce the results or modify them for your use case.

---
