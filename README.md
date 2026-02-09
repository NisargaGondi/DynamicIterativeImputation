# Multi-Constraint Time Series Imputation

[![IEEE](https://img.shields.io/badge/IEEE-2024-blue.svg)](https://ieeexplore.ieee.org/abstract/document/11115894)
[![Python](https://img.shields.io/badge/Python-3.8+-green.svg)](https://www.python.org/)

> **Novel framework for handling missing values in time series data through sequential algorithm application based on dataset constraints**

Published in **IEEE Conference 2024** | [Read the Paper](https://ieeexplore.ieee.org/abstract/document/11115894)

---

## 🎯 Overview

Traditional imputation methods apply single algorithms without considering dataset-specific characteristics. This work introduces a **multi-constraint sequential imputation framework** that identifies optimal algorithm sequences based on:

- **Missing value percentage** - How much data is missing
- **Dataset length** - Temporal span of the time series  
- **Number of variables** - Univariate vs. multivariate complexity

By applying algorithms iteratively in the right order, we achieve **significant accuracy improvements** over individual algorithm approaches.

---

## 📊 Key Results

| Dataset | Individual Algorithm RMSE | Sequential Framework RMSE | Improvement |
|---------|---------------------------|---------------------------|-------------|
| BAFU (water discharge) | 0.371 | 0.148 | **60% reduction** |
| Climate | 0.717 | 0.275 | **62% reduction** |
| Drift10 (gas sensors) | 0.785 | 0.275 | **65% reduction** |

**Example Sequential Pipeline:**  
`SPIRIT (miss_perc) → CDRec (ts_length) → SoftImpute (ts_nbr)` = Better accuracy than any single algorithm

---

## 🔬 Methodology

### 1. Constraint Identification
Analyze dataset characteristics:
- Percentage of missing blocks
- Time series length (1K - 50K observations)
- Number of columns (univariate vs. multivariate)

### 2. Algorithm Selection
Evaluate 12 state-of-the-art algorithms:
- **CDRec** - Centroid decomposition
- **DynaMMo** - Latent variable evolution
- **SVT** - Singular value thresholding
- **GROUSE** - Grassmannian gradient projection
- **SoftImpute** - Soft-thresholded SVD
- **ROSL** - Robust orthonormal subspace learning
- **STMVL** - Spatio-temporal multi-view learning
- **SPIRIT** - Streaming pattern identification
- **TeNMF** - Temporal non-negative matrix factorization
- **TRMF** - Temporal regularized matrix factorization
- **TKCM** - Time series k-nearest centroids matching
- **SVDImpute** - SVD-based imputation

### 3. Sequential Application
Apply algorithms iteratively, refining imputation at each step based on constraint-specific performance.

---

## 🚀 Getting Started

This work builds upon the excellent [ImputeBench framework](https://github.com/eXascaleInfolab/bench-vldb20) by eXascale Infolab.

### Prerequisites
```bash
# Clone the benchmark repository
git clone https://github.com/eXascaleInfolab/bench-vldb20
cd bench-vldb20

# Install dependencies
pip install -r requirements.txt
```

### Running the Framework

1. **Prepare your dataset** in the required format
2. **Analyze constraints** using the dataset profiler
3. **Select algorithm sequence** based on constraint analysis
4. **Run iterative imputation** with the chosen sequence

See the [benchmark documentation](https://github.com/eXascaleInfolab/bench-vldb20) for detailed usage instructions.

---

## 📚 Citation

If you use this work in your research, please cite:
```bibtex
@inproceedings{gondi2024multiconstraint,
  title={Multi-Constraint Time Series Imputation},
  author={Gondi, Nisarga and Kayarvizhy N.},
  booktitle={2024 IEEE International Conference on Computer Science and Engineering (UBMK)},
  year={2024},
  doi={10.1109/...11115894}
}
```

---

## 📖 Publication

**[Multi-Constraint Time Series Imputation](https://ieeexplore.ieee.org/abstract/document/11115894)**  
Nisarga Gondi, Kayarvizhy N.  
*IEEE Conference 2024*

**Abstract:** Imputation of missing values in real-time univariate and multivariate time series is critical for maintaining data quality and model accuracy. While many algorithms exist, their performance is typically evaluated under single-constraint scenarios. This work addresses real-world datasets that exhibit multiple simultaneous constraints by introducing a sequential framework that dynamically selects and orders imputation algorithms based on dataset characteristics, achieving substantial accuracy improvements over traditional single-algorithm approaches.

---

## 🛠️ Technical Details

**Datasets Evaluated:**
- Air Quality (China monitoring stations)
- Water Discharge (BAFU - Swiss rivers)
- Climate Data (NOAA stations)
- Gas Sensors (UCI repository)
- Household Energy (France)
- Temperature (China meteorological)
- Weather (MeteoSwiss)

**Evaluation Metrics:**
- Root Mean Squared Error (RMSE)
- Mean Absolute Error (MAE)
- Mean Squared Error (MSE)

**Framework Implementation:**
Built using Python with the [ImputeBench](https://github.com/eXascaleInfolab/bench-vldb20) benchmarking framework as the foundation.

---

## 🙏 Acknowledgments

This work builds upon the [ImputeBench benchmark suite](https://github.com/eXascaleInfolab/bench-vldb20) developed by the eXascale Infolab research group. We thank them for providing the comprehensive framework that enabled this research.

---

## 📧 Contact

**Nisarga Gondi**  
Carnegie Mellon University  
ngondi@andrew.cmu.edu

**Research Advisor:** Dr. Kayarvizhy N.  
B.M.S. College of Engineering

---

## 🔗 Links

- [IEEE Paper](https://ieeexplore.ieee.org/abstract/document/11115894)
- [ImputeBench Framework](https://github.com/eXascaleInfolab/bench-vldb20)
- [Author's GitHub](https://github.com/NisargaGondi)
- [CMU CyLab Research](https://www.cylab.cmu.edu/)

---

<div align="center">
  <i>Building reliable ML systems through robust data quality frameworks</i>
</div>
