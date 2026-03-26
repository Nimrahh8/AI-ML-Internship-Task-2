# Multimodal Housing Price Prediction

## Task Objective
The goal of this project is to accurately predict house prices using a **multimodal deep learning approach**, combining both tabular data and image data. The model leverages structured features (like bedrooms, bathrooms, square footage) and visual cues from synthetic house images to improve prediction accuracy.

## Dataset Used
- **Synthetic tabular dataset** (1,000 samples) mimicking real-world housing distributions (King County Housing data):
  - Features: `bedrooms`, `bathrooms`, `sqft_living`, `floors`, `waterfront`, `condition`, `grade`, `yr_built`, `zipcode_enc`
  - Target: `price`
- **Synthetic images** (1,000 house images generated via PIL):
  - House color encodes price tier
  - House width reflects square footage
  - Number of windows represents bedrooms

## Models Applied
1. **Multimodal Model** (best performance):
   - **Image branch**: Pretrained ResNet18 (CNN) → 256-dim features
   - **Tabular branch**: Fully connected MLP → 64-dim features
   - **Fusion**: Concatenation → MLP → Predicted log(price)
2. **Ablation Study Models**:
   - **Image-only model**: ResNet18 → 1 output
   - **Tabular-only model**: MLP → 1 output

## Training Details
- Loss function: Mean Squared Error (MSE) on log-transformed prices
- Optimizer: Adam with weight decay
- Early stopping applied based on validation loss
- Learning rate scheduler (ReduceLROnPlateau)
- Train/Val/Test split: 70/15/15
- Batch size: 32

## Key Results & Findings

| Model               | MAE ($)      | RMSE ($)     |
|--------------------|-------------|-------------|
| Image Only          | 95K – 120K  | 130K – 160K |
| Tabular Only        | 45K – 60K   | 65K – 85K   |
| **Multimodal (both)** | 35K – 50K   | 50K – 70K   |

**Insights**:
- Multimodal model achieves the best accuracy by combining both image and tabular features.
- Tabular features contribute most significantly to prediction accuracy.
- Image features provide complementary information, further improving performance.

**Limitations**:
- Synthetic dataset may not fully represent real-world housing data.
- Training time is higher due to CNN image processing.

**Future Improvements**:
- Use real-world housing datasets for better generalization.
- Explore more advanced architectures (EfficientNet, Vision Transformers).
- Deploy the model as a web application for real-time house price predictions.

## Visualizations
- Training curves (MSE loss over epochs)
- Predicted vs Actual prices scatter plot
- Residual distribution histogram

## Model Saving
- Trained multimodal model along with scaler saved in `./saved_model/multimodal_housing_model.pt` for deployment.
