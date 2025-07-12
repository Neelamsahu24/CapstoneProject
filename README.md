
# 🚗 Dynamic Pricing for Urban Parking Lots

This project simulates a **real-time dynamic pricing system** for urban parking lots using data from 14 lots across 73 days. It models how prices should adapt based on **occupancy, vehicle type, queue length, traffic, special days,** and **nearby competitors** using Python, Pandas, Numpy, Pathway, and Bokeh.

---

## 📊 Project Structure

- **Data Preprocessing**
  - Missing values handled
  - Vehicle types encoded:
    - Car = 1.0, Bike = 0.5, Truck = 1.5
  - Features normalized: `OccupancyRate`, `QueueLength`

- **Model 1: Linear Pricing**
  - Formula: `Price_t+1 = Price_t + α * (Occupancy / Capacity)`
  - Acts as baseline model

- **Model 2: Demand-Based Pricing**
  - Demand calculated from weighted features:
    - Occupancy rate, queue length, traffic, special day, vehicle type
  - Price updated: `Price = BasePrice * (1 + λ * NormalizedDemand)`
  - Keeps prices between `0.5x` and `2x` base price

- **Model 3: Competitive Pricing (Optional)**
  - Uses **Haversine distance** to locate nearby lots
  - Price adjusted relative to **competition status**

---

## ⚙️ Real-Time Engine: Pathway

- Simulates data stream from CSV
- Uses `pw.apply()` to calculate demand and price on the fly
- Outputs include: FinalPrice, demand features

---

## 📈 Visualization: Bokeh

- Real-time line charts for top 5 most active parking lots
- X-axis: Time / Index  
  Y-axis: FinalPrice
- Helps justify price behavior over time

---

## 💡 Key Assumptions

- Trucks are willing to pay more than bikes/cars
- High traffic nearby decreases demand
- Special days boost demand
- Demand increases with occupancy & queue length
- Competitor pricing and availability influence price

---

## 🧠 Outcomes

- Developed 3 dynamic pricing models
- Real-time processing via Pathway
- Live visualization with Bokeh
- Prices are explainable, efficient, and fair

---

## 🛠 Technologies Used

- Programming - Python 3.11
- Data Handling - Pandas, NumPy
- Real-Time Engine - Pathway
- Visualization - Bokeh
- Mapping & Distance - Haversine Formula
- Environment - Google Colab

+------------------------+ | Dataset (CSV Format) | +------------------------+ | v +------------------------+ | Preprocessing Layer | <- Clean traffic strings, map vehicle weights +------------------------+ | v +------------------------+ | Real-Time Ingestion | | Pathway CSV Reader | +------------------------+ | v +------------------------+ | Pathway Logic | | - Compute OccupancyRate| | - Map VehicleType | | - Demand Calculation | | - Price Derivation | +------------------------+ | v +------------------------+ | Stream Output Writer | | JSONL Output File | +------------------------+ | v +------------------------+ | Bokeh Visualization | | - Line plots per lot | | - Price comparisons



---

## 📁 Project Files

- `dynamic_pricing.ipynb`: Main simulation and modeling notebook
- `report.docx`: Capstone project summary
- `README.md`: Project overview

---

## 🚀 Future Enhancements

- Integrate real-time sensor data
- Predictive modeling using ML
- Mobile/web app for end users

---

## 👤 Authors

-Neelam Sahu 
  Capstone Project – Dynamic Pricing, 2025

