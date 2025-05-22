# Price Path Simulator

This project demonstrates how to model and simulate asset price movements using two foundational stochastic models: the **Bachelier Model** (based on price differences) and the **Samuelson Model** (based on returns). The goal is to understand how well simple Gaussian-based models can mimic real-world price behavior.

---

## Project Workflow

1. **Data Collection**  
   Retrieve real-world asset data (e.g. MSFT daily closing prices) via the SimFin API.

2. **Data Cleaning & Enrichment**  
   - Filter for relevant fields (date and price).
   - Calculate daily **price differences** and **returns**.

3. **Model Fitting (Gaussian Distribution)**  
   - Fit a **normal distribution** to both price differences and returns.
   - Visualize histograms overlaid with fitted Gaussian curves.

4. **Simulate Price Paths**  
   - Use the Gaussian model to simulate future prices using:
     - **Bachelier Model**: `Pₙ = Pₙ₋₁ + Δ`
     - **Samuelson Model**: `Pₙ = Pₙ₋₁ × (1 + r)`
   - Simulate multiple random paths to reflect the uncertainty of future prices.

5. **Compare to Real Market Data**  
   - Plot simulated paths vs. actual price path.
   - Evaluate model behavior through visualization and summary statistics.

---

## Models Explained

| Model         | Based On         | Formula                        | Behavior                              |
|---------------|------------------|--------------------------------|---------------------------------------|
| Bachelier     | Price differences| `Pₙ = Pₙ₋₁ + Δ`                | Allows negative prices (unrealistic)  |
| Samuelson     | Returns (%)      | `Pₙ = Pₙ₋₁ × (1 + r)`          | Prices always positive (more realistic) |

---

## Requirements

- Python 3.8+
- `pandas`, `numpy`, `matplotlib`, `scipy`, `requests`, `python-dotenv`

Install packages with:

```bash
pip install -r requirements.txt
```

---
## File Structure
```
├── data/  
│   ├── raw/         # Raw price data from SimFin API  
│   ├── processed/   # Cleaned price data  
│   └── enrich/      # Data with price differences and returns  
├── PRICE_PATH_SIM.ipynb   # Main analysis and simulation notebook  
├── README.md        # Project documentation  
```
