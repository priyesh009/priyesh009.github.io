# Territory Factor Enhancement Using Hexagonal Geospatial Methodology

## Overview
This project focuses on improving **territory rating factors** in an insurance pricing algorithm.  
Traditionally, territory factors are defined at the **ZIP code level**, but ZIP boundaries are often arbitrary and do not always align with true risk patterns.  
To address this, I implemented a **hexagonal geospatial approach** using the H3 library in Python.

## Business Problem
- Current territory rating factors are defined at ZIP code level.  
- ZIP boundaries are political/geographic, not risk-aligned.  
- Small exposure in some ZIPs leads to unstable estimates.  
- New ZIP codes lack territory factors altogether.  

The goal was to enhance credibility and smoothness of territory factors while also covering **new ZIP codes** with no historical data.

## Methodology
1. **Hexagonal Grid Creation**  
   - Used Uber's **H3 library** to divide Indiana into hexagons at ~1-mile resolution.  
   - Each insurance policy location was mapped to a hexagon.

2. **Loss Cost Calculation**  
   - For each hexagon:  
     \[
     \text{Loss Cost} = \frac{\text{Incurred Losses}}{\text{Exposure}}
     \]  

3. **Credibility Adjustment**  
   - Hexagons with insufficient exposure borrowed from neighboring rings.  
   - Up to **5 rings** were considered, each with decreasing weight.  
   - Final credibility weight = 1.0 (distributed across rings).  

4. **Inverse Distance Weighting (IDW) for New ZIPs**  
   - New ZIPs with no historical data were assigned factors via **IDW interpolation**.  
   - Neighboring hexagons’ factors contributed with weights proportional to \( 1/distance \).  

5. **Output: Enhanced Territory Factors**  
   - Smooth, stable factors at the **hexagon level**.  
   - Converted back to ZIP level if required for rating engine.  

## Results
- Reduced volatility in small-ZIP rating factors.  
- Created **continuous spatial gradients** of risk instead of abrupt ZIP-based jumps.  
- Produced stable, interpretable factors that can be integrated into the **GLM pricing algorithm**.  

## Tools & Technologies
- **Python (Pandas, NumPy, H3, Geopandas, Shapely, Scikit-learn)**  
- **Matplotlib, Seaborn, Folium** for visualization  
- Insurance actuarial methods: **credibility theory, inverse distance weighting**  

## Portfolio Value
This project demonstrates:  
- Application of **geospatial analytics in actuarial pricing**.  
- Use of **credibility standards** to stabilize insurance rating variables.  
- Handling **missing/new ZIP codes** through spatial interpolation.  
- Strong blend of **statistical rigor** and **business application** in insurance pricing.
