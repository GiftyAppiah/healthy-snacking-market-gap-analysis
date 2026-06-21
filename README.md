# Project Brief: The "Sugar Trap" Market Gap Analysis

**Client:** Helix CPG Partners (Strategic Food & Beverage Consultancy)  
**Deliverable:** Interactive Dashboard, Code Notebook & Insight Presentation

---

# Healthy Snacking Market Gap Analysis

## A. Executive Summary

This project analyzed a sample of 200,000 products from the Open Food Facts database to identify underserved opportunities in the healthy snacking market. After data cleaning and validation, 18,119 products with complete nutritional information were retained for analysis. A Nutrient Matrix comparing sugar and protein content revealed that most products are concentrated in high-sugar, low-protein segments, while relatively few products occupy the high-protein, low-sugar space.

The analysis identified a significant market opportunity within the Chocolate & Confectionery category, where only 2.17% of products met the healthy-snacking criteria. Ingredient analysis further showed that Milk/Dairy, Meat/Poultry, and Soy are the most common protein sources among successful high-protein products. Based on the findings, a high-protein, low-sugar chocolate snack is recommended as the most promising product development opportunity.

---

## B. Project Links

### Notebook

Link: https://colab.research.google.com/drive/19xQspHZ2PkiGLy1QIJxB0SI2tuR8aZ-2?usp=sharing

### Dashboard

Link: https://app.powerbi.com/view?r=eyJrIjoiNTZhYzNlMWMtMzllNS00MWU1LThmNDUtZTIyODgyMGUzNDZmIiwidCI6IjEwNGQ4MDQ4LWZkMGMtNDNkNS1hNjMwLWZjNjI5ZTVkYWI1OSJ9&pageName=3d178bef866e05b8e477

### Presentation

Link: https://canva.link/d09dqk6y527qtwl

### Optional Video Walkthrough

Link: [INSERT YOUTUBE LINK]

---

## C. Technical Explanation

### Data Cleaning

The Open Food Facts dataset contains millions of records and hundreds of attributes. To create a manageable and reproducible analysis, a sample of 200,000 products was loaded into Pandas.

The cleaning process included:

- Removing records with missing product names.
- Removing records with missing category information.
- Removing records with missing sugar values.
- Removing records with missing protein values.
- Filtering biologically impossible nutritional values (e.g., sugar or protein values greater than 100g per 100g).
- Retaining only records required for the business analysis.

After cleaning and validation, 18,119 products remained for analysis.

### Category Engineering

The `categories_tags` field contained thousands of detailed and inconsistent category labels. To improve interpretability, products were grouped into 11 high-level categories:

- Breakfast & Cereals
- Beverages
- Dairy Products
- Biscuits & Bakery
- Snacks
- Chocolate & Confectionery
- Meals & Prepared Foods
- Meat & Seafood
- Protein & Fitness
- Plant-Based Foods
- Other

This categorization enabled meaningful comparison across major food segments and supported dashboard filtering and analysis.

### Candidate's Choice Challenge

To provide additional business value, a custom **Market Gap Score** was introduced.

The Market Gap Score combines category size and healthy-product penetration to identify large markets where healthy alternatives remain underrepresented. This metric helps prioritize categories with strong commercial potential rather than relying solely on percentages.

Using this approach, Breakfast & Cereals, Beverages, and Dairy Products emerged as large categories with substantial opportunities for healthy product innovation.

### Key Recommendation

**Based on the data, the biggest market opportunity is in the Chocolate & Confectionery category, specifically targeting products with approximately 20g of protein and less than 2g of sugar per 100g.**

The recommended product concept is a high-protein chocolate snack utilizing dairy- or soy-based  protein sources.

---

## Project Structure

```text
THE-MARKET-GAP-ANALYSIS/
│
├── Assets/
│   └── Dashboard_Screenshot.png
│
├── Dashboard/
│   ├── Market_Gap_Dashboard.pbix
│   └── Market_Gap_Presentation.pdf
│
├── Data/
│   └── openfoodfacts.csv (excluded from GitHub using .gitignore)
│
├── Exports/
│   ├── cleaned_food_analysis.csv
│   ├── opportunity_summary.csv
│   └── protein_sources.csv
│
├── Notebook/
│   ├── analysis.ipynb
│   └── analysis.html
│
├── LICENSE
└── README.md
```

## Repository Contents

### Notebook Files

- **analysis.ipynb** — Main Jupyter notebook containing data cleaning, exploratory analysis, feature engineering, visualization, and business recommendations.
- **analysis.html** — HTML export of the notebook provided to ensure reviewers can view outputs even if GitHub fails to render the notebook.

### Dashboard Files

- **Market_Gap_Dashboard.pbix** — Interactive Power BI dashboard containing all visualizations and business insights.
- **Market_Gap_Presentation.pdf** — Final presentation summarizing the project findings, recommendations, and market opportunity.

### Exported Analysis Files

- **cleaned_food_analysis.csv** — Cleaned dataset used for all analyses and dashboard creation.
- **opportunity_summary.csv** — Summary table containing category-level opportunity metrics, including healthy-product penetration and market gap scores.
- **protein_sources.csv** — Frequency analysis of protein sources identified within high-protein, low-sugar products.

### Assets

- **Dashboard_Screenshot.png** — Screenshot of the final Power BI dashboard used for repository preview and documentation.

### Data

- **openfoodfacts.csv** — Original Open Food Facts dataset used for analysis. This file is excluded from the GitHub repository through `.gitignore` due to its large size.



## Dashboard Preview

![Dashboard Screenshot](https://raw.githubusercontent.com/GiftyAppiah/healthy-snacking-market-gap-analysis/main/Assets/Dashboard_Screenshot.png)

## Tools Used

- Python
- Pandas
- NumPy
- Matplotlib
- Power BI 
- Jupyter Notebook

## Methodology

1. Data Collection and Sampling
2. Data Cleaning and Validation
3. Category Engineering
4. Nutritional Analysis
5. Market Gap Identification
6. Ingredient Mining
7. Dashboard Development
8. Business Recommendation

## 1. Business Context
**Helix CPG Partners** advises major food └──manufacturers on new product development. Our newest client, a global snack manufacturer, wants to launch a "Healthy Snacking" line. They believe the market is oversaturated with sugary treats, but they lack the data to prove where the specific gaps are.

 They have hired us to answer one question: **"Where is the 'Blue Ocean' in the snack aisle?"**

Specifically, they are looking for product categories that are currently under-served—areas where consumer demand for health (e.g., High Protein, High Fiber) is not being met by current product offerings (which are mostly High Sugar, High Fat).

## 2. The Data
You will use the **Open Food Facts** dataset, a free, open, and massive database of food products from around the world.

* **Source:** [Open Food Facts Data](https://world.openfoodfacts.org/data)
* **Format:** CSV (Comma Separated Values)
* **Warning:** The full dataset is massive (over 3GB). You are **not** expected to process the entire file. You should filter the data early or work with a manageable subset (e.g., the first 500,000 rows or specific categories).

## 3. Tooling Requirements
You have the flexibility to choose your development environment:

* **Option A (Recommended):** Use a cloud-hosted notebook like **Google Colab**, or **Deepnote**, etc.
* **Option B:** Use a local **Jupyter Notebook** or **VS Code**.
    * *Condition:* If you choose this, you must ensure your code is reproducible. Do not reference local file paths (e.g., `C:/Downloads/...`). Assume the dataset is in the same folder as your notebook.
* **Dashboarding:** The final output must be a **publicly accessible link** (e.g., Tableau Public, Google Looker Studio, Streamlit Cloud, or PowerBI Web).

---

## 4. User Stories & Acceptance Criteria

### Story 1: Data Ingestion & "The Clean Up"
* *As a** Strategy Director,  
**I want** a clean dataset that removes products with erroneous nutritional information,  
**So that** my analysis is not skewed by bad data entry.

* **Acceptance Criteria:**
    * Handle missing values: Decide what to do with rows that have `null` or empty `sugars_100g`, `proteins_100g`, or `product_name`.
    * Handle outliers: Filter out biologically impossible values.
    * **Deliverable:** A cleaned Pandas DataFrame or SQL table export.

### Story 2: The Category Wrangler
**As a** Product Manager,  
**I want** to group products into readable high-level categories,  
**So that** I don't have to look at 10,000 unique, messy tags like `en:chocolate-chip-cookies-with-nuts`.

* **Acceptance Criteria:**
    * The `categories_tags` column is a comma-separated string (e.g., `en:snacks, en:sweet-snacks, en:biscuits`). You must parse this string.
    * Create a logic to assign a "Primary Category" to each product based on keywords.
    * Create at least 5 distinct high-level buckets.

### Story 3: The "Nutrient Matrix" Visualization
**As a** Marketing Lead,  
**I want** to see a Scatter Plot comparing Sugar (X-axis) vs. Protein (Y-axis) for different categories,  
**So that** I can visually spot where the products are clustered.

* **Acceptance Criteria:**
    * Create a dashboard (PowerBI, Tableau, Streamlit, or Python-based charts) displaying this relationship.
    * Allow the user to filter the chart by the "High Level Categories" you created in Story 2.
    * **Key Visual:** Identify the "Empty Quadrant" (e.g., High Protein + Low Sugar).

### Story 4: The Recommend ation
**As a** Client,  
**I want** a clear text recommendation on what product we should build,  
**So that** I can take this to the R&D team.

* **Acceptance Criteria:**
    * On the dashboard, include a "Key Insight" box.
    * Complete this sentence: *"Based on the data, the biggest market opportunity is in [Category Name], specifically targeting products with [X]g of protein and less than [Y]g of sugar."*

---

## 5. Bonus User Story: The "Hidden Gem"
**As a** Health Conscious Consumer,  
**I want** to know which specific ingredients are driving the high protein content in the "good" products,  
**So that** I can replicate this in our new recipe.

* **Acceptance Criteria:**
    * Analyze the `ingredients_text` column for products in your "High Protein" cluster.
    * Extract and list the Top 3 most common protein sources (e.g., "Whey", "Peanuts", "Soy").

---

## 6. The "Candidate's Choice" Challenge
**As a** Creative Analyst,  
**I want** to add one additional feature or analysis to this project that I believe provides massive value,  
**So that** I can show off my business acumen.

* **Instructions:**
    * Add one more chart, filter, or metric that wasn't asked for.
    * Explain **why** you added it.
    * **There is no wrong answer, but you must justify your choice.**

---

## 7. Submission Guidelines
Please edit this `README.md` file in your forked repository to include the following three sections at the top:

### A. The Executive Summary
* A 3-5 sentence summary of your findings.

### B. Project Links
* **Link to Notebook:** (e.g., Google Colab, etc.). *Ensure sharing permissions are set to "Anyone with the link can view".*
* **Link to Dashboard:** (e.g., Tableau Public / Power BI Web, etc.).
* **Link to Presentation:** A link to a short slide deck (PDF, PPT) AND (Optional) a 2-minute video walkthrough (YouTube) explaining your results.

### C. Technical Explanation
* Briefly explain how you handled the "Data Cleaning".
* Explain your "Candidate's Choice" addition.

**Important Note on Code Submission:**
* Upload your `.ipynb` notebook file to the repo.
* **Crucial:** Also upload an **HTML or PDF export** of your notebook so we can see your charts even if GitHub fails to render the notebook code.
* Once you are ready, please fill out the [Official Submission Form Here](https://forms.office.com/e/heitZ9PP7y) with your links

---

## 🛑 CRITICAL: Pre-Submission Checklist

**Before you submit your form, you MUST complete this checklist.**

> ⚠️ **WARNING:** If you miss any of these items, your submission will be flagged as "Incomplete" and you will **NOT** be invited to an interview. 
>
> **We do not accept "permission error" excuses. Test your links in Incognito Mode.**

### 1. Repository & Code Checks
- [ ] **My GitHub Repo is Public.** (Open the link in a Private/Incognito window to verify).
- [ ] **I have uploaded the `.ipynb` notebook file.**
- [ ] **I have ALSO uploaded an HTML or PDF export** of the notebook.
- [ ] **I have NOT uploaded the massive raw dataset.** (Use `.gitignore` or just don't commit the CSV).
- [ ] **My code uses Relative Paths.** 

### 2. Deliverable Checks
- [ ] **My Dashboard link is publicly accessible.** (No login required).
- [ ] **My Presentation link is publicly accessible.** (Permissions set to "Anyone with the link can view").
- [ ] **I have updated this `README.md` file** with my Executive Summary and technical notes.

### 3. Completeness
- [ ] I have completed **User Stories 1-4**.
- [ ] I have completed the **"Candidate's Choice"** challenge and explained it in the README.

**✅ Only when you have checked every box above, proceed to the submission form.**

---
