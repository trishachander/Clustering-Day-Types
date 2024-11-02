# 📅 Revealing Representative Day-Types Using Clustering

## 📚 Course Information
- **Course**: AH2179
- **Module**: 5
- **Project**: Representative Day-Types through Clustering Analysis

## 🎯 Project Overview
This project implements and compares multiple clustering methods to identify representative day-types. The methods explored include **k-means**, **agglomerative**, **DBSCAN**, and **GNN**. The focus is on tuning model parameters and evaluating performance using internal and external metrics to reveal the most representative day types effectively.

## 📊 Model Performance Comparison
| Model             | Silhouette Score | Davies Bouldin Score | Calinski Harabbasz Score | MAE       | MAPE   | Evaluation Metric |
|-------------------|------------------|-----------------------|---------------------------|-----------|--------|-------------------|
| kNN               | 0.26924          | 1.23140              | 118.0547                  | 129.77361 | 8.4901 | 9.2775            |
| Agglomerative     | 0.26377          | 1.35879              | 159.13421                 | 59.98866  | 3.31836| 10.7863           |
| DBSCAN            | 0.28358          | 2.22541              | 9.93803                   | 60.67715  | 3.3573 | 0.3044            |
| GNN               | 0.31493          | 1.07859              | 112.19560                 | 128.16948 | 8.40844| 12.0161           |

## 🏗️ Model Architecture
### Data Preprocessing
- **Scaling**: StandardScaler implementation
- **Feature Selection**: All columns relevant to clustering day-types
- **Parameter Tuning**: Iterative testing with cluster numbers, epsilon for DBSCAN, etc.

### 🤖 Clustering Methods Implemented
1. k-means
2. Agglomerative Clustering
3. DBSCAN
4. GNN (Graph Neural Network)

## ⭐ Best Model Configuration
The **GNN** method emerged as the best performer based on internal and external evaluation metrics. The optimal configuration identified representative day-types with minimal errors and maximized internal scoring metrics.

## 📈 Evaluation Metric Formula
To assess internal performance, a custom evaluation metric was created:
> **`evaluation_metric = silhouette_score * e(-davies_bouldin_score) * calinski_harabbasz_score`** 🚀

This metric enabled a balanced assessment across the different clustering models, providing insights into the most representative configurations.

## 💡 Key Findings & Detailed Reflections

### 🔍 Model Performance Analysis
1. **Clustering Method and Cluster Selection**
   - GNN was the top-performing method, showing distinct patterns for warmer/cooler months and weekdays/weekends in the calendar graph.
   - Agglomerative clustering performed well at 5 clusters, though its performance decreased beyond this point.

2. **Parameter Calibration Observations**
   - **kNN**: Performance dipped between clusters 3-5, particularly with a rise in the Davies-Bouldin Score.
   - **Agglomerative**: Best performance at around 5 clusters, as indicated by the Davies-Bouldin Score.
   - **DBSCAN**: Epsilon value calibration was essential, with optimal performance at epsilon < 1400.
   - **GNN**: Optimal performance observed with 3 clusters, with performance dropping as clusters increased.

### 🎓 Technical Lessons Learned
1. **Challenges in Clustering**
   - Interpreting clustering scores and visual results was subjective, especially with calendar graphs showing diverse patterns.
   - Selecting cluster numbers and tuning epsilon required trial and error, adding time to the analysis process.

2. **Importance of Clustering in AI**
   - Clustering provides valuable insights into large datasets by identifying patterns that aid decision-making and strategy formulation.

3. **Domain-Specific Applications**
   - This clustering approach could aid in train delay predictions and optimizing scheduling based on high-flow periods.

## 🗓️ Visual Results

### 🗓️ Calendar Graph
<img src="https://github.com/user-attachments/assets/094c16d6-ca6a-465b-939e-5fb21e573198" width="400">

### 📈 Flow vs Time of Day
<img src="https://github.com/user-attachments/assets/3cfd6263-9cc1-4478-a322-9449eacf6ac0" width="400">

## 🔮 Future Applications & Transportation Problems

### 📋 Potential Applications
1. **Train Delay Prediction**
   - Cluster-based analysis to predict high-delay periods
   - Optimization of train schedules to meet demand

2. **Traffic Flow Optimization**
   - Identification of peak and off-peak hours for improved scheduling
   - Application in real-time traffic management

3. **Urban Infrastructure Planning**
   - Analyzing utilization patterns to aid in infrastructure planning and maintenance scheduling

### 🛠️ Recommended Techniques
1. **Enhanced Clustering Techniques**
   - Experimentation with additional clustering methods (e.g., spectral clustering)
   - Hybrid models combining clustering with predictive analytics

2. **Advanced Evaluation Metrics**
   - Incorporating cross-validation with clustering to refine parameter selection
   - Additional external validation metrics for robust performance comparison

3. **Data Enrichment for Improved Insights**
   - Integrating temporal and spatial data for enhanced clustering performance
   - Utilizing domain-specific knowledge to refine feature selection

## 🛠️ Dependencies
- Scikit-learn
- Pandas
- NumPy
- Matplotlib
- Seaborn
- NetworkX (for GNN implementation)

---
*Note: This project was completed as part of the AH2179 course, Module 5.* 🎓
