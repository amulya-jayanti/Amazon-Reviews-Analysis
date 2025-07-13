# Amazon-Reviews-Analysis

Amazon Reviews Analysis using Big Data Techniques

📑 Executive Summary

This project analyzes millions of Amazon product reviews (1998–2024) using Big Data tools, uncovering trends, seasonal behaviors, and potential spam patterns. It leverages PySpark for scalable data processing, MinHash LSH for text similarity, and deep EDA for market and behavior insights.

✅ Key Highlights
Processed ~65 million reviews using PySpark and Parquet datasets.\
Identified seasonal spikes, pricing dynamics, and spam behaviors.\
Applied MinHash LSH on Beauty reviews to detect duplicate content.\
Revealed loose correlation between price and review quality/volume.\
Found higher text duplication in older reviews vs recent, likely due to AI-generated diversity.

📊 Data & Methodology

📁 Datasets:
Dataset	Description ->	Size
reviews_parquet	Ratings, review text, timestamps, helpful votes ->	64.6M records\
meta_parquet	Product metadata (title, category, price, image) -> 4.3M records

⚙️ Technologies Used:

PySpark for distributed processing\
Pandas and Matplotlib for local EDA\
MinHash LSH for similarity detection\
Jupyter Notebooks for analysis & reporting

🧹 Data Cleaning & Preprocessing

Dropped nulls, irrelevant fields, and non-English/empty reviews\
Flattened nested structures, normalized timestamps\
Reduced df_reviews from 64,679,785 → 64,556,967 rows\
Filled missing values in key fields like price, main_category, store (rather than dropping)

📈 Timeline Trends & Review Spikes

🔍 Review Activity Over Time\
Pre-2011: Sparse review volume\
2012–2017: Steady growth, platform adoption\
2019–2021: Major spike → COVID, e-commerce boom\
2023–2024: Drop-off likely due to ingestion delays

🎯 Key Observations\
Extreme spikes (~40K reviews/day in 2020) suggest bots or promotions\
Seasonal surges: July (Prime Day) and December (Holiday season)\
Recommendation: Use rolling averages to smooth spikes without ignoring real events

🔝 Top Products by Review Count\
Products like B073R68TSH and B07HRN9J19 had >200 reviews/day\
Peaks cluster in 2020–2021, reflecting lockdown-driven buying\
B001MAOQY2 shows long-term stability → mature product lifecycle

📦 Category-Level Insights

🎁 Seasonal Trends\
Category	-> Peak Time	Notes\
All Beauty, Fashion, Electronics	-> December Holiday gift surge\
Amazon Products, Tech	-> July	Prime Day impact\
Books, Handmade	-> Stable	No strong seasonality

⭐ Ratings vs. Volume\
Highly-rated products (4.9+) ≠ most reviewed\
Popular products tend to get moderately lower ratings\
Volume ≠ Satisfaction → Larger sample sizes reveal more variability

💵 Price vs. Rating & Volume\
Weak correlation between price and:\
Rating\
Number of reviews\
Low-priced items dominate review counts\
Suggests that affordability + utility > premium perception

🧑‍💻 Reviewer Behavior\
Top reviewers post across hundreds of ASINs\
Specialized accounts in niches (e.g., Beauty, Electronics)\
Raises concerns about spam farms or incentivized reviewers\
🔍 Suggestion: Add reviewer diversity as a feature for spam detection

🧪 Text Similarity Detection with LSH\
Focus Category: Beauty\
Sample: 10K reviews\
Used MinHash LSH to detect duplicate titles & texts\
Metric	Value\
Title Duplication Rate	27.46%\
Text Duplication Rate	3.36%

🧠 Clear copy-paste behavior suggests automation or coordinated manipulation

🆕 Review Uniqueness Over Time

Time Period	Duplication Rate\
Pre-2022	7.39%\
2022–2023	2.93%\
✨ Possible Explanations\
AI-generated reviews are more diverse\
Increased efforts to evade detection\
Use of paraphrasing tools

📌 Conclusions & Recommendations

🔍 Patterns Identified\
Clear seasonal surges (July, December)\
Bot-like spikes during product launches/promotions\
Volume ≠ Satisfaction in ratings\
Review duplication still present and detectable

✅ Recommendations\
Use LSH-based duplication scores in spam filters\
Leverage seasonality for marketing/inventory planning\
Monitor reviewer patterns for fraud signals\
Moderate products with explosive growth
