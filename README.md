# Project03_46W38
Wind Power forecasting

## Dataset Description
The project relies on an hourly dataset of wind and power production recorded at 4 turbine sites, spanning the period 02.01.2017 → 31.12.2021, and released under an open “CC0 1.0 Universal” license.

### Variables
- Time — `YYYY-MM-DD HH:mm:ss`
- temperature_2m — °F @ 2 m
- relativehumidity_2m — %
- dewpoint_2m — °F
- windspeed_10m — m/s @ 10 m
- windspeed_100m — m/s @ 100 m
- winddirection_10m — deg (0–360) @ 10 m
- winddirection_100m — deg (0–360) @ 100 m
- windgusts_10m — m/s
- power — % of Prated (normalized)

---

## ML Steps

1. **loading**  
2. **preprocessing**  
3. **train/test split — 80% train, 20% test**  
4. **training**  
5. **testing**  
6. **evaluation**
   - **Plots**
     - Scatter plot: `y_true vs y_pred`
     - Error distribution
   - **Numerical metrics (regression)**
     - MSE — Mean Squared Error  
     - RMSE — Root Mean Square Error  
     - MAE — Mean Absolute Error  
     - R² — coefficient of determination  
7. **save_model**

---

## project03_46W38 Structure 

├── main.py                # entry point
├── load_data.py           # reading datasets
├── preprocessing.py       # cleaning and feature engineering
├── training.py            # training and evaluation
├── predicting.py          # loading model and predicting

---

## Pipeline Diagram (Mermaid)

```mermaid
flowchart TB

    classDef inputColor fill:#4B5563,stroke:#1F2937,color:#ffffff;
    classDef pipeColor fill:#6B7280,stroke:#374151,color:#ffffff;
    classDef evalColor fill:#9CA3AF,stroke:#4B5563,color:#ffffff;
    classDef endColor fill:#F59E0B,stroke:#B45309,color:#ffffff;

    subgraph INPUT["Dataset 2017–2021"]
        A["Wind Speed & Power Data"]
    end
    class A,INPUT inputColor;

    subgraph PIPELINE["ML Pipeline"]
        B["Load Data"]
        C["Preprocessing"]
        D["Train/Test Split (80/20)"]
        E["Training"]
        F["Testing"]
    end
    class B,C,D,E,F,PIPELINE pipeColor;

    subgraph EVAL["Evaluation"]
        G1["Scatter Plot"]
        G2["Error Distribution"]
        H1["MSE"]
        H2["RMSE"]
        H3["MAE"]
        H4["R²"]
    end
    class G1,G2,H1,H2,H3,H4,EVAL evalColor;

    J["Save Model"]
    class J endColor;

    A --> B --> C --> D --> E --> F --> EVAL --> J
```

