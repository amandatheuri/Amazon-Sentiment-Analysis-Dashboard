#  Amazon Product Sentiment Analysis & Text Mining

A hybrid data analytics project combining **Python (NLP)** and **Tableau** to transform over 5,000 unstructured customer reviews into actionable product development and marketing insights.

---

## Executive Summary
Analysis of 5,000 product reviews reveals exceptional brand loyalty, with **93.7% of reviews skewing positive** and driving an overall average rating of **4.6 / 5**. 

While smart-home devices (such as the *Amazon Echo Show* and *Echo Plus*) drive the highest volume of customer engagement, niche products like the *Fire HD 10 Tablet* achieve the highest relative satisfaction despite lower sales volume, representing a key area for targeted marketing expansion. However, localized text-mining uncovered deep feature-level complaints regarding battery retention on specific hardware lines.

---

## Tableau Dashboard Overview

### <img width="403" height="235" alt="image" src="https://github.com/user-attachments/assets/7510b53c-1684-4e6b-b90b-9562dc4df29a" />


* **High-Level KPIs:** Dynamically tracks Review Count (5,000), Average Rating (4.597), and Total Positive Reviews (4,686).
* **Interactivity:** Built-in dashboard action filters allow users to click any sentiment segment (Positive/Neutral/Negative) to instantly isolate and drill down into product-specific rating distributions.
* **Granular Tracking:** Features a dual-bar chart system tracking volume vs. quality by comparing overall review counts against average star ratings.

---

## Deep-Dive Python Insights (NLP Pipeline)

While the Tableau dashboard highlighted high-level satisfaction, star ratings alone couldn't explain *why* certain products lagged. By building a natural language processing pipeline in Python, I mined the raw text reviews to uncover the underlying drivers of negative sentiment.

### 1. Overcoming the "Stop Word" Noise
Initial tokenization was heavily flooded with grammatical noise (e.g., *'in', 'they', 'these', 'was'*). I implemented an **NLTK-based text cleaning pipeline** to filter out standard English stop words and e-commerce fluff text, successfully isolating high-value nouns and adjectives.

### 2. The Core Discovery: The Battery Lifespan Crisis
The programmatic word-frequency count revealed a major, localized hardware issue:

* **The Numbers:** The terms **"batteries"** (889 occurrences) and **"battery"** (277 occurrences) appeared a combined **1,166 times** within negative review text, heavily accompanied by the descriptors **"last"** (270) and **"long"** (176).
* **The Product Mapping:** Cross-referencing these keywords with product fields showed these complaints explicitly clustered around the **"tablet"** (294), **"fire"** (256), and **"kindle"** (195) text segments.

**Strategic Takeaway:** This explains *why* the Amazon Fire Tablet sits at the bottom of the Tableau "Average Product Rating" chart. While Amazon's smart-speaker ecosystem (Echo) is flawlessly optimized, the screen-based tablet devices suffer from a systemic battery retention defect that directly triggers lower customer ratings.

---

## Tech Stack & Libraries
* **Data Visualization:** Tableau Desktop
* **Language:** Python 3
* **Data Manipulation:** Pandas
* **Natural Language Processing:** NLTK (VADER Sentiment Lexicon)
* **Statistical Plotting:** Matplotlib & Seaborn
