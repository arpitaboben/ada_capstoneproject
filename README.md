# 🚚 Delivery Route Optimization — ADA Capstone Project

**Author:** Arpita  
**Course:** Algorithm Design & Analysis (ADA)  
**Repo:** `delivery-route-mini-project-Arpita`

---

## Problem Statement

E-commerce platforms like Amazon and Flipkart face complex last-mile delivery challenges combining time windows, vehicle weight constraints, and optimal routing. This project models and solves that problem using six algorithmic paradigms from the ADA syllabus.

---

## Project Structure

```
delivery-route-mini-project-Arpita/
├── delivery_route_optimization.ipynb   ← Main notebook (all tasks)
├── requirements.txt                    ← Python dependencies
├── README.md                           ← This file
└── images/
    ├── dashboard.png                   ← 4-plot analysis dashboard
    └── mst.png                         ← MST visualization
```

---

## Algorithm Strategies

| # | Algorithm | Strategy | Time Complexity | Purpose |
|---|-----------|----------|-----------------|---------|
| 1 | **Recursive Route Cost** | Divide & Conquer | O(n!) | Models route cost using base/recursive cases |
| 2 | **Greedy Selection** | Greedy | O(n log n) | Selects parcels by value-to-weight ratio |
| 3 | **DP Time Windows** | Dynamic Programming | O(n) | Validates feasibility of delivery schedule |
| 4 | **Dijkstra** | Graph / Greedy | O((V+E) log V) | Shortest path from warehouse to each customer |
| 5 | **Prim's MST** | Graph / Greedy | O(E log V) | Minimum spanning tree for coverage analysis |
| 6 | **Held-Karp TSP** | Bitmask DP | O(n² · 2ⁿ) | Exact optimal delivery sequence |

---

## Input Setup

- **8 locations**: Warehouse (depot) + 7 delivery sectors
- **7 parcels**: each with value (₹), weight (kg), delivery time window
- **Vehicle**: 15 kg capacity, 30 km/h speed, shift starts 9:00 AM

---

## How to Run

```bash
# 1. Clone the repo
git clone https://github.com/<your-username>/delivery-route-mini-project-Arpita.git
cd delivery-route-mini-project-Arpita

# 2. Create virtual environment
python -m venv venv
source venv/bin/activate        # Windows: venv\Scripts\activate

# 3. Install dependencies
pip install -r requirements.txt

# 4. Create images folder
mkdir -p images

# 5. Launch JupyterLab
jupyter lab

# 6. Open and run delivery_route_optimization.ipynb
```

---

## Key Results

| Metric | Value |
|--------|-------|
| TSP optimal route distance | See notebook output |
| Parcels selected (Greedy) | Based on 15 kg capacity |
| Total delivery value | ₹ (sum of selected parcels) |
| MST total cost | See notebook output |
| Dijkstra — farthest node | Sector G (30 km) |

---

## Reflection Highlights

- **Greedy** is the fastest but suboptimal for multi-constraint problems.
- **Held-Karp TSP** is exact but exponential — infeasible beyond ~20 nodes.
- Combining Greedy selection + DP time-window checking + TSP routing gives a realistic end-to-end pipeline.
- Future extensions: multi-vehicle VRP, fuel-cost modeling, traffic-aware edge weights.

---

## References

- Cormen, Leiserson, Rivest, Stein — *Introduction to Algorithms* (CLRS)
- MIT OCW — TSP and NP-hard problems
- NetworkX documentation: https://networkx.org
- GeeksforGeeks — Held-Karp, Dijkstra, Prim's implementations
