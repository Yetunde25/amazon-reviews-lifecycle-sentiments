# Amazon Reviews Lifecycle-Aware Sentiment Analysis

This repository contains an end-to-end analysis of **Amazon Fashion reviews**, focusing on **lifecycle-aware sentiment modeling** — understanding how customer sentiment evolves across product lifecycle stages.

The project integrates:
- **Data preprocessing** with stratified sampling and oversampling
- **Lifecycle segmentation** of reviews
- **Statistical validation** (z-test, McNemar’s, t-test, sensitivity analysis)
- **Ablation studies** to assess feature importance
- **Interactive visualizations** for insight communication

---
Project Structure

```text
├── data/                  # Raw and processed datasets
├── notebooks/             # Google Colab notebooks for EDA, modeling, and validation
├── src/                   # Python modules for preprocessing, modeling, and evaluation
├── results/               # Generated plots, tables, and metrics
├── requirements.txt       # Python dependencies
├── README.md              # Project documentation
└── LICENSE                # License information
```

##  Key Features

- **Lifecycle-aware segmentation**: Groups reviews by product lifecycle stage to capture temporal sentiment shifts.
- **Balanced sampling**: Uses stratified sampling and oversampling to address class imbalance.
- **Robust statistical testing**: Validates model improvements with multiple statistical tests.
- **Ablation studies**: Quantifies the contribution of each feature group.
- **Interactive dashboards**: Enables stakeholders to explore sentiment trends visually.

## Data Access

The full dataset is too large to store in this repository.  
You can download it from [Google Drive](https://drive.google.com/file/d/12zf0k0unfIOD-awppuUzH5iknsDgea9Y/view?usp=share_link).

Once downloaded, place the file in the `data/` directory before running the notebooks or scripts.

**Note:** The dataset is compressed (`.jsonl.gz`). You’ll need to extract it before use:
```bash
gunzip data/Amazon_Fashion.jsonl.gz
```


##  Methodology

1. **Data Acquisition & Cleaning**  
   - Removed duplicates, handled missing values, normalized text.
2. **Lifecycle Segmentation**  
   - Defined lifecycle stages based on product release and review timestamps.
3. **Feature Engineering**  
   - Text embeddings, sentiment lexicons, temporal features.
4. **Modeling**  
   - Baseline classifiers → tuned models with lifecycle-aware features.
5. **Validation**  
   - Statistical tests to confirm significance of improvements.
6. **Ablation Studies**  
   - Systematic removal of feature groups to assess impact.


##  Running the Project

### Option 1 — Open in Google Colab (Recommended)
- Navigate to the `notebooks/` folder in this repo.
- Click the notebook you want to run.
- Click the **"Open in Colab"** button (or copy the GitHub URL into [Google Colab](https://colab.research.google.com/)).

### Option 2 — Run Locally
```bash
# Clone the repository
git clone https://github.com/Yetunde25/amazon-reviews-lifecycle-sentiments.git
cd amazon-reviews-lifecycle-sentiments

# Create and activate virtual environment (optional but recommended)
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt
```

## Results & Insights
Lifecycle-aware models outperform baseline sentiment models by capturing temporal context.
Early lifecycle stages often show higher positive sentiment, which declines in later stages.
Ablation results confirm that temporal features significantly improve classification accuracy.


## Technologies Used
Python: pandas, NumPy, scikit-learn
Visualization: Matplotlib, Seaborn, Plotly
Statistical Testing: SciPy, statsmodels
Notebooks: Google Colab
Version Control: Git/GitHub
