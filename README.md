[Uploading README (6).md…]()
# Customer Segmentation with K-Means & DBSCAN

Unsupervised learning project that segments mall customers by **annual income** and **spending score**, then compares **K-Means** and **DBSCAN** on non-spherical (moon-shaped) data.

## Highlights

- **Preprocessing:** feature selection and standardization with `StandardScaler`
- **Choosing K:** elbow method (WCSS) validated with the Silhouette Score
- **Segmentation:** 5 customer groups visualized with labeled centroids
- **Algorithm comparison:** K-Means fails on crescent shapes, DBSCAN separates them perfectly

## Results

| Task | Result |
|---|---|
| Optimal number of clusters | **K = 5** (elbow point) |
| Silhouette Score (K = 5) | **0.55**, the highest among K = 2 to 10 |
| K-Means on moons | Splits both crescents (ARI = 0.25) |
| DBSCAN on moons (`eps=0.2`, `min_samples=5`) | 2 clusters, 0 noise (ARI = 1.0) |

### Customer Segments

| Segment | Income | Spending | Suggested Action |
|---|---|---|---|
| Target customers | High | High | VIP / loyalty programs |
| Careful spenders | High | Low | Personalized offers |
| Standard customers | Medium | Medium | Regular promotions |
| Budget-conscious | Low | Low | Discounts and deals |
| Impulsive spenders | Low | High | Trendy products, installments |

## Key Takeaway

K-Means assumes compact, roughly spherical clusters and works well for the mall data. DBSCAN groups points by density, so it handles arbitrary shapes and flags outliers as noise, but it is sensitive to `eps` and `min_samples`.

## Project Structure

```
├── Assignment_-_Clustering_Solved.ipynb   # Full solution with outputs
├── Mall_Customers.csv                     # Dataset (200 customers)
└── README.md
```

## Getting Started

```bash
git clone <your-repo-url>
cd <your-repo-folder>
pip install numpy pandas matplotlib seaborn scikit-learn jupyter
jupyter notebook Assignment_-_Clustering_Solved.ipynb
```

## Tech Stack

Python · pandas · NumPy · scikit-learn · Matplotlib · Seaborn
