# 🚗 Smart Dynamic Parking Pricing (Real-Time with Pathway & Bokeh)

This project implements a real-time, dynamic parking price prediction system using **Pathway** for stream processing and **Bokeh** for live visualization. The pricing models adapt to live data inputs such as occupancy, queue length, traffic conditions, special events, and vehicle types. The aim is to simulate intelligent, real-world pricing decisions based on supply, demand, and competition.
A Demo Video is attacthed on how to run plots.
gdrive to video here ->
https://drive.google.com/drive/folders/1_wDRBQDy47wibL8R04KQsA-qWSOZRQUn?usp=sharing
---
## 🧰 Tech Stack

| Technology | Role |
|-----------|------|
| **Python** | Core logic and streaming |
| **Pathway** | Real-time data ingestion and streaming processing |
| **Pandas** | Batch computations, pre-processing |
| **Bokeh** | Interactive visualizations |
| **Pyngrok** | Public URL for Bokeh dashboard in notebooks |
| **Jupyter/Colab** | Execution environment |

---

## 🗂️ Project Structure

├── dataset.csv
├── model1_app.py # Linear pricing model
├── model2_app.py # Dynamic pricing model
├── stream_output_model1.csv
├── stream_output_model2.csv
├── README.md
├── ToRUN.py
---

## 🧠 Architecture & Workflow

```mermaid
flowchart TD
    subgraph A[Data Stream]
        A1[dataset.csv - Pathway Stream]
    end

    subgraph B[Model Logic]
        B1[Model 1: Linear Price]
        B2[Model 2: Dynamic Price]
    end

    subgraph C[Output Files]
        C1[stream_output_model1.csv]
        C2[stream_output_model2.csv]
    end

    subgraph D[Visualization]
        D1[Bokeh Line + Scatter]
        D2[Bokeh Daily Avg Scatter]
    end

    A1 --> B1 --> C1 --> D1
    A1 --> B2 --> C2 --> D1
    C1 --> D2
    C2 --> D2
