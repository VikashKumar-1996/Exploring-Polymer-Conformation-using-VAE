#  Polymer Conformation Generation Using Variational Autoencoder (VAE) Trained on Self-Avoiding Walk (SAW) Data

##  Overview  
This project explores **polymer conformation generation** using a **Variational Autoencoder (VAE)** trained on **Self-Avoiding Walk (SAW)** data. The aim is to synthesize **realistic 3D polymer structures** that obey physical constraints such as fixed bond lengths and excluded volume.

The VAE learns a **latent representation** of polymer conformations and generates novel, physically consistent structures by sampling from the learned latent space.

---

##  Key Features  
- **Self-Avoiding Walk (SAW) Dataset** – ensures non-overlapping and realistic polymer configurations.  
- **Physics-Aware Loss Function** – includes bond length and self-avoidance penalties for physical realism.  
- **Latent Space Sampling** – generates new polymer conformations from learned distributions.  
- **3D Visualization** – converts internal coordinates into Cartesian space for structure plotting.  
- **Regularized Training** – AdamW optimizer, dropout, and early stopping to prevent overfitting.  

---

##  Methodology  

### 1. **Data Generation**
- Generated polymer conformations using **Self-Avoiding Walk (SAW)** algorithm.  
- Each polymer is represented using **internal coordinates** (bond length, bond angle, torsion).  

### 2. **Model Architecture**
- **Encoder** – compresses internal coordinates into a latent vector.  
- **Decoder** – reconstructs coordinates from latent representation.  
- **Loss Function:**
  \[
  L = L_{recon} + \beta L_{KL} + \lambda_1 L_{bond} + \lambda_2 L_{self-avoid}
  \]
  - *Reconstruction Loss* – ensures output accuracy.  
  - *KL Divergence* – regularizes latent space.  
  - *Bond Length Loss* – enforces ~2.0 unit bond distances.  
  - *Self-Avoidance Loss* – prevents atomic overlap.  

### 3. **Training Setup**
- **Optimizer:** AdamW  
- **Batch Size:** 64  
- **Dropout:** 0.2–0.3  
- **Early Stopping:** Enabled  
- **Framework:** PyTorch  

---

##  Results  
- VAE reconstructs and generates **realistic polymer conformations**.  
- Maintains **~2.0 unit bond lengths**.  
- Produces **diverse end-to-end distances** and smooth non-overlapping structures.  

---

## 📂 Repository Structure  

