# Dynamic Parking Pricing System

**Capstone Project : Summer Analytics 2025 • Consulting & Analytics Club IIT Guwahati**  
**Author :** **Kangkan Kalita** • *kalitakangkan.239@gmail.com*

---

## ⚙️ Overview

An end-to-end Python-based system that simulates real-time dynamic parking pricing for multiple urban lots. It processes data streams, computes responsive pricing models, smooths outputs, and offers interactive dashboards for analysis.

**Key Features:**
- Simulates streaming data with **Pathway**
- Implements **3 pricing strategies**: Baseline Linear, Demand-Based, and optional Competitive
- **Exponential moving average smoothing** for price stabilization  
- Static & interactive **Bokeh/Panel dashboards** for live-style visualization
- Easily reusable for any lot by leveraging per-lot loops

---

## 📁 Repository Structure

```text
├── data/
│   └── dataset.csv
├── notebooks/
│   └── Capstone_Project_SA_2025.ipynb
├── figures/
│   └── parking_pricing_dashboard.html
├── requirements.txt
├── LICENSE
└── README.md

````

---

## 🚀 Installation

1. Clone the repo:
   ```bash
   git clone https://github.com/Kangkan-Kalita/parking-pricing-system.git
   cd parking-pricing-system


2. Install dependencies (in a virtual environment):

   ```bash
   pip install -r requirements.txt
   ```
3. Open `notebooks/Dynamic_Parking_Pricing.ipynb` in Jupyter or Google Colab.

---

## 🧪 Usage

Run cells in the following logical order:

1. **Cell 1** – Setup & imports
2. **Cell 2** – Load and preprocess raw dataset
3. **Cell 3** – Generate baseline prices per lot
4. **Cell 4** – Compute demand-based scores and pricing
5. **Cell 5** – (*Optional*) Competitive pricing adjustments
6. **Cell 6.1** – Export `parking_stream_full.csv` for replay
7. **Cell 6.2** – Generate final CSV (`parking_stream_final.csv`) with smoothed prices
8. **Cell 7** – Interactive Panel dashboard per lot
9. **Cell 8** – Saving the output into CSV & JSON

The notebook is fully self-contained and runs from start to finish without errors.

---

## 📊 Models & Methodology

| Model Type      | Core Principle                                        | Output Range | Responsiveness to Occupancy |
| --------------- | ----------------------------------------------------- | ------------ | --------------------------- |
| Baseline Linear | Linear step-by-step update using occupancy rate       | \$5–20       | Low (correlation \~0.02)    |
| Demand-Based    | Tanh-normalized combination of demand signals         | \$5–20       | Higher (correlation \~0.63) |
| Competitive     | Optional: adjusts pricing based on nearby lot pricing | Varies       | Extensible to multi-lot use |

All models respect clipping bounds and start from a \$10 base price per lot.

---

## 🔍 Outputs & Insights

* **`parking_stream_full.csv`**: raw features for simulated streaming
* **`parking_stream_final.csv`**: enriched with `BaselinePrice`, `DemandScore`, `DemandPrice`, `SmoothedDemandPrice`
* Example static visualizations and demand-score histograms (stored in `figures/`) illustrate model behavior and stability.

---

## 🧾 Contributing & Extensions

Contributions are welcome! For example:

* Refine demand function & tune hyperparameters
* Implement end-to-end deployment using live ingestion (Kafka, REST)
* Build predictive rerouting suggestions based on queue forecasts
* Add a widget to switch lots dynamically or select date ranges
* Share feedback or open feature requests via GitHub Issues

If you contribute, please format notebooks cleanly, document any modifications, and follow the existing markdown commentary style.

---

## 📧 Contact

Kangkan Kalita • (kalitakangkan.239@gmail.com)
