# Briggs-Rauscher Reaction Video Analysis

This repository contains code and data for analyzing the Briggs-Rauscher oscillating chemical reaction from video. The workflow includes frame extraction, feature engineering, exploratory data analysis (EDA), and machine learning models to predict the time remaining in the reaction.

## Project Structure

- `briggs.ipynb` — Main Jupyter notebook with all code, EDA, and modeling.
- `videoplayback.mp4` — Original reaction video.
- `videoplayback_normal_speed.mp4` — Video resampled to real time.
- `FRAME/` — Extracted frames from the video (ignored by git).
- `FRAMENEW/` — Alternative frame extraction folder (ignored by git).
- `df.csv`, `final_df.csv` — Feature datasets (ignored by git).

## Main Steps

1. **Frame Extraction**
   - Extract frames from the video every 0.5s (or 0.1s for high-res) after 15s.
2. **Feature Engineering**
   - CNN embeddings (ResNet18)
   - Color histograms (RGB, 32 bins)
   - Edge/texture features (Sobel)
   - Statistical features (mean, diff, entropy, skew, std, peak bin)
3. **EDA**
   - Color cycles, edge/texture over time
   - PCA/t-SNE, autocorrelation, peak detection
   - 3D RGB trajectory, histogram heatmap
4. **Modeling**
   - Linear Regression (various feature sets)
   - XGBoost Regression
   - LSTM Regression (PyTorch)
   - Vision Transformer (ViT, Hugging Face and custom PyTorch)
   - All models predict time remaining in the reaction

## Usage

1. Clone the repository and install requirements:
   ```bash
   pip install -r requirements.txt
   ```
2. Run the notebook `briggs.ipynb` step by step.
3. Place your video file as `videoplayback.mp4` in the root directory.
4. Outputs (frames, CSVs) are generated automatically.

## Data
- **Frames**: Extracted to `FRAME/` (ignored by git)
- **Feature CSVs**: `df.csv`, `final_df.csv` (ignored by git)

## Results
- EDA plots and model performance metrics are shown in the notebook.
- Best models achieve high R² for time-remaining prediction.

## Notes
- All large files and outputs are ignored by `.gitignore`.
- For custom video or frame rates, adjust parameters in the notebook.

## License
MIT License

---

*Created by [Uttkarsh Solanki], 2025*
