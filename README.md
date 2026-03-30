# 📡 Variogram Modelling with Random Forest
 
A machine learning approach to variogram modelling in geostatistics, replacing classical parametric models (Power, Logarithmic, Spherical…) with a **Random Forest Regressor** trained on experimental variogram data.
 
---
 
## 🧠 Context
 
Variograms are central tools in geostatistics — they describe the spatial autocorrelation of a variable as a function of distance `h`. Classical fitting methods rely on hand-picked parametric models. This notebook explores whether a **data-driven Random Forest model** can outperform them.
 
**Result: MSE reduced by ~85.25%** compared to the classical Power model.
 
---
 
## 📂 Project Structure
 
```
├── Variogram-modelling.ipynb        # Main notebook
├── Donnees_Vario2.xlsx              # Experimental variogram dataset (h, γ(h))
├── Correction_Donnees_Vario.xlsx    # Classical models reference (Power, Log)
└── README.md
```
 
---
 
## ⚙️ Methodology
 
| Step | Description |
|------|-------------|
| **Data loading** | Experimental variogram data: lag distance `h (km)` and semivariance `γ(h)` |
| **EDA** | Histograms, correlation matrix, γ(h) vs h visualization |
| **Modelling** | Random Forest Regressor (`n_estimators=100`, `random_state=42`) |
| **Split** | 80% train / 20% test |
| **Evaluation** | RMSE, MSE, MAE, R² |
| **Comparison** | RF model vs Power model from reference Excel file |
 
---
 
## 📊 Results
 
| Model | RMSE | MSE | MAE | R² |
|-------|------|-----|-----|----|
| Random Forest (n=100) | 1.332 | 1.773 | 1.040 | 0.927 |
| Random Forest (n=200) | 1.331 | 1.771 | 1.054 | 0.927 |
| Power model (classical) | — | ~12.0* | — | — |
 
*\*Estimated from the 85.25% MSE reduction reported in the notebook.*
 
---
 
## 🛠️ Requirements
 
```bash
pip install pandas numpy matplotlib seaborn scikit-learn openpyxl
```
 
---
 
## 🚀 Usage
 
1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/variogram-modelling.git
   cd variogram-modelling
   ```
 
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
 
3. Open the notebook:
   ```bash
   jupyter notebook Variogram-modelling.ipynb
   ```
 
4. Make sure both Excel files (`Donnees_Vario2.xlsx` and `Correction_Donnees_Vario.xlsx`) are in the same directory.
 
---
 
## 🔮 Possible Extensions
 
- Hyperparameter tuning with `GridSearchCV`
- Comparison with SVR, XGBoost, or neural networks
- Extension to 2D/3D variogram surfaces
- Application to real spatial datasets (soil, water quality, elevation)
 
---
 
## 👤 Author
 
**Tini** — Eco-hydrology & Integrated Water Resources Management Student  
Institut National de l'Eau (INE) — Université d'Abomey-Calavi, Bénin
 
---
 
## 📄 License
 
MIT License — feel free to use and adapt with attribution.
 
