# CellMechAI  
_A multimodal deep learning framework for predicting cell mechanics from genomics and imaging data_

## 📌 Summary
CellMechAI is a proof-of-concept project that integrates **genomics (gene expression)** and **cell imaging** with **deep learning** to predict the **mechanical properties of cells** (e.g., stiffness, deformability).  
This project sits at the intersection of **biology, physics, and artificial intelligence**:  

- **Biology** → provides gene expression and microscopy data.  
- **Physics** → defines measurable mechanical phenotypes (softness, stiffness, traction).  
- **AI** → learns predictive models from multi-modal data.  

Potential applications include:  
- **Classification**: normal vs cancerous cells.  
- **Drug screening**: monitoring how treatments alter cell mechanics.  
- **Biological discovery**: identifying genes most correlated with mechanical states.  

## 🗺️ Project Plan

**Week 1 (Prototype)**  
- ✅ Load datasets (gene expression + cell images).  
- ✅ Train baseline models (MLP for gene expression, CNN for images).  
- ✅ Build simple multimodal fusion model (concat embeddings).  
- ✅ Add proxy regression head for "mechanical property".  
- ✅ Perform basic interpretability (SHAP on gene encoder).  

**Future Extensions**  
- Add real physics-informed losses (traction balance, smoothness).  
- Use scRNA-seq embeddings (scVI, transformers).  
- Incorporate U-Net for pixel-wise mechanics prediction.  
- Apply explainability techniques to discover gene–mechanics links.  

## 🧠 Model Architecture

- **Gene encoder** → PCA + MLP → latent vector z_rna.  
- **Image encoder** → pretrained ResNet18 → latent vector z_img.  
- **Fusion** → concatenate z_rna + z_img → joint embedding z_joint.  
- **Multi-head outputs**:  
  - Head A: Physics regression (proxy stiffness values).  
  - Head B: Classification (normal vs cancer).  
  - Head C: Gene importance analysis.  

