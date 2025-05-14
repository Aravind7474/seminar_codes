# seminar_codes
/RealTimeVQVAE
    ├── README.md         # Project description, setup instructions, and usage details.
    ├── requirements.txt  # List of dependencies (e.g., torch, torchvision, matplotlib).
    ├── train.py          # Python script with the training code (as above).
    ├── inference.py      # Script for real-time inference.
    ├── data/             # Folder for sample datasets or instructions for downloading your data.
    ├── notebooks/        # Google Colab notebooks demonstrating the training and inference.
    └── utils/            # Utility functions (e.g., data preprocessing, visualization).



VDR: Neural Spatio-Temporal Data Release with User-Level Differential Privacy

This project implements **VDR (VAE-based Density Release)** — a novel neural approach to privately release spatio-temporal datasets while preserving accuracy under **user-level differential privacy**.

Overview:
Companies like Meta and Google release location datasets that are critical for urban planning, transportation, and public health. However, protecting individual user privacy in such data is challenging, especially when each user contributes multiple records.

This repository introduces a privacy-preserving pipeline based on:
- 3D Histogram Construction
- Laplace Mechanism for Differential Privacy
- Variational Autoencoders (VAE) for Denoising
- Statistical Refinement for Accuracy Recovery

Key Components:

1. **User-Level Sampling**
Limit each user’s data contributions to ensure bounded sensitivity.

2. **Histogram Construction**
Discretize spatial and temporal dimensions into a 3D grid (e.g., lat, lon, time).

3. **Differential Privacy**
Apply Laplace noise to each grid cell using the ε-DP framework.

4. **VAE-Based Denoising**
Train a **Convolutional VAE** to learn latent representations of clean data patterns and denoise the noisy histogram.

5. **Statistical Refinement**
Scale results using a learned correction factor to counterbalance sampling error.


Datasets:

* 📍 Veraset (proprietary)
* 🌐 Foursquare
* 🧭 Gowalla
* 🚖 SF Taxi GPS

Requirements:

* Python 3.8+
* NumPy, Pandas
* TensorFlow or PyTorch
* JAX (optional, for speed)
* Matplotlib (for visualization)

Results:

* 🔐 Achieves strong ε-DP guarantees (e.g., ε = 0.2)
* 🎯 Up to **40% improvement** in hotspot detection over baseline DP
* ⚡ Inference time <1ms

Citation:

If you use this code or build upon it, please cite:


Ahuja, R., Zeighami, S., Ghinita, G., & Shahabi, C. (2023). 
A Neural Approach to Spatio-Temporal Data Release with User-Level Differential Privacy. 
ACM SIGMOD.


Future Work:

* Support for non-stationary mobility data
* Integration with Transformer-based denoisers
* Real-time adaptive refinement




