# CREDIT-CARD-FRAUD

## Overview

This repository contains a Python project for customer segmentation using a credit card dataset. The project applies **K-means clustering** to segment customers based on their credit card usage behavior, enabling targeted marketing strategies. The dataset includes 18 features such as balance, purchases, cash advances, and payment behaviors, which are used to identify distinct customer groups.

The script generates actionable marketing insights for each cluster, with a specific fix to ensure all clusters, including **Cluster 3**, receive recommendations—even when feature values are below average.

---

## Dataset

The dataset (`credit_card_dataset.csv`) contains anonymized credit card usage data with the following features:

* `CUST_ID`: Customer identifier *(dropped for clustering)*
* `BALANCE`: Outstanding balance
* `PURCHASES`: Total purchase amount
* `CASH_ADVANCE`: Total cash advance amount
* `PURCHASES_FREQUENCY`: Frequency of purchases (0 to 1)
* `PRC_FULL_PAYMENT`: Proportion of full payments made
* `CREDIT_LIMIT`, `PAYMENTS`, `MINIMUM_PAYMENTS`, etc.: Other behavioral metrics

**Note:** The dataset is not included in this repository due to its size and potential sensitivity. Place `credit_card_dataset.csv` in the project directory to run the script.

---

## Features

* **Data Preprocessing**:

  * Handles missing values using **median imputation**
  * Scales features using **StandardScaler**

* **Clustering**:

  * Uses **K-means clustering** with an optimal number of clusters (default: 4)
  * Cluster count determined using the **elbow method** and **silhouette scores**

* **Visualizations**:

  * Elbow plot
  * Silhouette plot
  * Cluster distribution counts
  * Box plots for key features (`BALANCE`, `PURCHASES`, `CASH_ADVANCE`, `CREDIT_LIMIT`, `PAYMENTS`)

* **Marketing Insights**:

  * Tailored marketing strategies for each cluster
  * Fix ensures clusters with below-average feature values (like Cluster 3) receive actionable recommendations

* **Output**:

  * Saves `credit_card_dataset_with_clusters.csv` with cluster labels

---

## Prerequisites

* Python 3.7 or later
* Install dependencies:

  ```bash
  pip install pandas numpy matplotlib seaborn scikit-learn
  ```

---

## Installation

**Clone the Repository**

```bash
git clone https://github.com/Mithun017/CREDIT-CARD-FRAUD.git
cd CREDIT-CARD-FRAUD
```

**Install Dependencies**

```bash
pip install -r requirements.txt
```

Or manually:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

**Add Dataset**
Place `credit_card_dataset.csv` in the `CREDIT-CARD-FRAUD` directory.

---

## Usage

**Run the script:**

```bash
python customer_segmentation.py
```

**Output:**

* **Console**: Dataset info, missing value counts, cluster centers, summaries, and marketing insights
* **Plots**: Elbow, silhouette, cluster distribution, and box plots
* **File**: Saves results to `credit_card_dataset_with_clusters.csv`

---

## Marketing Insights Example

Each cluster receives insights based on whether features like BALANCE, PURCHASES, CASH\_ADVANCE, and PURCHASES\_FREQUENCY are above or below the mean.

**Example — Cluster 3:**

* Lower balance customers: Promote balance transfer offers to attract more usage
* Low purchase activity: Target with promotional discounts to boost spending
* Low cash advance usage: Educate about cash advance benefits for emergencies
* Infrequent purchasers: Send reminders or incentives to increase card usage

---

## Project Structure

```bash
CREDIT-CARD-FRAUD/
├── customer_segmentation.py         # Main script
├── README.md                        # This file
├── .gitignore                       # Ignores cache files and CSVs
├── LICENSE                          # MIT License
├── credit_card_dataset.csv          # Dataset (add manually)
└── credit_card_dataset_with_clusters.csv  # Output (generated)
```

---

## Notes

* **Cluster 3 Fix**: Marketing recommendations are ensured even for below-average clusters
* **Customization**: You can change `optimal_k` in the script (default: 4)
* **Dataset Sensitivity**: Do not commit `credit_card_dataset.csv` to GitHub. It's excluded in `.gitignore`

---

## Contributing

Contributions are welcome!
**Steps:**

1. Fork the repository
2. Create a feature branch

   ```bash
   git checkout -b feature/your-feature
   ```
3. Commit your changes

   ```bash
   git commit -m "Add your feature"
   ```
4. Push to your branch

   ```bash
   git push origin feature/your-feature
   ```
5. Open a Pull Request

---
