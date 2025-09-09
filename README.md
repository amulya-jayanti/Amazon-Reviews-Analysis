# Amazon Reviews Analysis using Big Data Techniques

This project analyzes millions of Amazon product reviews from 1998 to 2024 using **Big Data** tools to uncover trends, seasonal behaviors, and potential spam patterns. We use **PySpark** for scalable data processing, **MinHash LSH** for text similarity, and extensive **Exploratory Data Analysis (EDA)** for market and behavioral insights.

---

### **Key Highlights**

* Processed approximately **65 million reviews** using PySpark and Parquet datasets.
* Identified significant seasonal spikes, pricing dynamics, and potential spam behavior.
* Applied **MinHash LSH** on product reviews to detect duplicate text.
* Discovered a weak correlation between a product's price and its review quality/volume.
* Found a higher text duplication rate in older reviews compared to more recent ones, suggesting that AI-generated content may be leading to more unique review text.

---

### **Data and Methodology**

#### **Datasets**

| Dataset | Description | Size |
| :--- | :--- | :--- |
| `reviews_parquet` | Ratings, review text, timestamps, helpful votes | ~64.6M records |
| `meta_parquet` | Product metadata (title, category, price, image) | ~4.3M records |

#### **Technologies Used**

* **PySpark:** For distributed data processing.
* **Pandas & Matplotlib:** For local data analysis and visualization.
* **MinHash LSH:** For scalable text similarity detection.
* **Jupyter Notebooks:** For analysis and reporting.

---

### **Key Findings**

#### **Review Activity Over Time**

The analysis of review activity reveals clear trends:
* A major spike in review volume occurred between **2019 and 2021**, likely driven by the e-commerce boom during the COVID-19 pandemic.
* Extreme daily spikes (up to 40,000 reviews/day) suggest bot activity or large-scale promotions.
* **Seasonal surges** are evident in **July** (Prime Day) and **December** (Holiday season).

#### **Category-Level Insights**

* **Seasonal Trends:** Categories like **Beauty**, **Fashion**, and **Electronics** peak in December, while **Amazon Products** and **Tech** see surges in July.
* **Ratings vs. Volume:** Products with the highest ratings (4.9+) are not always the most reviewed. Popular products with a higher review volume tend to have slightly lower average ratings, as a larger sample size captures more variability in customer satisfaction.
* **Price vs. Rating & Volume:** We found a weak correlation between a product's price and its average rating or review volume. Low-priced items tend to dominate review counts, suggesting that affordability and utility are key drivers for customer engagement.

#### **Reviewer Behavior**

The data shows a small number of top reviewers posting across hundreds of products. This raises concerns about spam farms or incentivized reviewers, which could impact the integrity of the review ecosystem.

#### **Text Similarity Detection with LSH**

Using MinHash LSH on a sample of 10,000 **Beauty** reviews, we found:
* **Title Duplication Rate:** 27.46%
* **Text Duplication Rate:** 3.36%

This indicates that some level of copy-paste behavior is present. Furthermore, we observed that review duplication has decreased over time:

| Time Period | Duplication Rate |
| :--- | :--- |
| **Pre-2022** | 7.39% |
| **2022–2023** | 2.93% |

This drop-off could be due to a rise in AI-generated reviews, which tend to be more unique, or increased efforts by platforms and users to evade detection.

---

### **Conclusions and Recommendations**

Based on our analysis, we recommend the following:

* **Spam Detection:** Integrate LSH-based duplication scores into spam filtering systems.
* **Marketing Strategy:** Leverage seasonality and key shopping events for targeted marketing and inventory planning.
* **Fraud Monitoring:** Monitor reviewer patterns, especially those with high review counts across many different products, for potential fraud signals.
* **Explosive Growth:** Moderate products with unusually explosive review growth to investigate potential bot or manipulation activity.
