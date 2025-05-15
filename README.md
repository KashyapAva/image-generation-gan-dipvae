# 🖼️ Image Generation using GANs and Disentangled VAEs

This project evaluates the performance of two generative models — **Generative Adversarial Networks (GANs)** and **Disentangled Inferred Prior Variational Autoencoders (DIP-VAEs)** — on MNIST and SVHN datasets for unsupervised image generation.

## 🎯 Objective

To compare GANs and DIP-VAEs on:
- Image quality
- Latent space disentanglement
- Training stability
- Computational efficiency

## 📚 Datasets
- **MNIST**: Handwritten digits (0–9)
- **SVHN**: Street View House Numbers (only digit '5' used for fairness)

## 🧠 Models Implemented

### ✅ Generative Adversarial Network (GAN)
- Generator and Discriminator in adversarial training
- Jensen-Shannon loss for minimax optimization
- Challenges: Mode collapse, sensitivity to learning rates

### ✅ Disentangled Inferred Prior Variational Autoencoder (DIP-VAE)
- Optimizes ELBO with an additional covariance penalty
- Encourages latent factor disentanglement
- Trained with moment-matching regularization on latent covariances

## 🧪 Key Results

- **MNIST**: DIP-VAE produced more stable and sharper reconstructions due to better latent structure and longer training
- **SVHN**: DIP-VAE outperformed GAN under limited compute resources
- GAN struggled with mode collapse and variability without fine-tuning

## 📊 Model Comparison Summary

| Model   | Strengths                          | Limitations                         |
|---------|------------------------------------|-------------------------------------|
| GAN     | Sharp image generation             | Prone to mode collapse, unstable    |
| DIP-VAE | Better disentanglement & stability | Slightly blurrier outputs           |

## ⚙️ Hyperparameters

### DIP-VAE
- Latent dim: 128  
- Epochs: 40  
- Optimizer: Adam  
- Batch size: 64, 128  
- Learning rates: 0.0001–0.005  
- λ_diag: 0.01–0.1  
- λ_offdiag: 0.05–0.5  

### GAN
- Noise dim: 100  
- Epochs: 10  
- Optimizer: Adam  
- Batch size: 64, 128  
- Learning rates: 0.0001–0.005  

## 🔧 Challenges & Solutions

| Challenge                      | Strategy                                 |
|-------------------------------|------------------------------------------|
| Mode collapse (GAN)           | Data augmentation + hyperparameter tuning |
| Over-regularization (DIP-VAE) | Dynamic λ scheduling                     |
| High compute cost             | Subset selection, early stopping         |

## 💡 Future Work
- Use **Inception Score** for objective quality assessment
- Develop hybrid DIP-VAE + GAN architectures
- Explore **RLHF** and **imitation learning** for generative tuning

## 🔗 Code & Report
- Full report: `STAT542_FINAL_Report_G11.pdf`
- [DIP-VAE & GAN code (Google Drive)](https://drive.google.com/drive/folders/1wnbg3v9iRiFsRcNtQHRT3MtUylg2nIJ4)

## 👥 Contributors
- Kashyap Ava (DIP-VAE)
- Govind, Sanyam, Yashna (DIP-VAE & tuning)
- Hetarth, Akshat, Shreya, Ansh (GAN + report)

---

*Final project for STAT 542: Machine Learning in R at UIUC.*
