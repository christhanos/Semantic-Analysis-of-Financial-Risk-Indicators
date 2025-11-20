# 🕵️‍♂️ Market Manipulation Detection: Semantic Web Crawler

![Python](https://img.shields.io/badge/Python-3.9%2B-blue?style=for-the-badge&logo=python)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?style=for-the-badge&logo=pandas)
![Seaborn](https://img.shields.io/badge/Seaborn-Visualization-green?style=for-the-badge&logo=pandas)
![SciPy](https://img.shields.io/badge/SciPy-Signal%20Processing-8CAAE6?style=for-the-badge&logo=scipy)
![License](https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge)

> **A targeted Web Scraping & NLP Pipeline designed to detect, quantify, and analyze semantic indicators of market manipulation, high-risk crypto assets, and "pump-and-dump" schemes within the Greek financial web ecosystem.**

---

## 📑 Table of Contents
- [📍 Overview](#-overview)
- [⚙️ Methodology](#%EF%B8%8F-methodology)
- [📊 Key Findings](#-key-findings)
- [🛠 Tech Stack](#-tech-stack)
- [🚀 Installation & Usage](#-installation--usage)
- [📈 Visualizations](#-visualizations)
- [🤝 Contributing](#-contributing)

---

## 📍 Overview
In the modern high-frequency trading environment, digital media plays a pivotal role in shaping market sentiment. This project automates the detection of **"Red Flag"** terminology across major financial news portals.

The system answers three key questions:
1.  **Temporal Dynamics:** *When* do spikes in manipulation terminology occur?
2.  **Source Attribution:** *Which* domains act as primary aggregators of risk-related content?
3.  **Semantic Distribution:** *What* is the frequency distribution of high-risk terminology?

---

## ⚙️ Methodology
The analysis follows a structured **Data Science Lifecycle**:

### 1. Data Acquisition (ETL) 🕸️
We implemented a custom **Breadth-First Search (BFS)** crawler that:
* Traverses major portals (*Naftemporiki, Capital, Euro2day*) starting from seed URLs.
* Adheres to a strict **Ethical Scraping Framework** (Politeness delays, `robots.txt` compliance).
* Filters content using a `deque` structure to manage the crawling frontier.

### 2. Feature Extraction 📝
Unstructured HTML data is parsed to isolate textual content, which is then mapped against a curated **Dictionary of Risk**.
* **Categories:** `Financial Services`, `Crypto`, `Red Flags`, `Indirect Indices`.
* **NLP:** Tokenization and stopword removal (e.g., filtering 'η').

### 3. Signal Processing & Anomaly Detection 📉
We utilized **SciPy** to detect statistical anomalies in keyword velocity.
* **Algorithm:** `scipy.signal.find_peaks`
* **Threshold:** Dynamic thresholding ($\mu + \sigma$) to identify high-density scraping intervals.

### 4. Iterative Refinement (Bootstrapping) 🤖
Post-analysis, we employed **Generative AI (Gemini Pro)** to semantically expand the vocabulary, reducing the *False Negative* rate for future iterations.

---

## 📊 Key Findings

| Insight | Description |
| :--- | :--- |
| **Hub Page Bias** | Spikes in detection (e.g., at **21:26**, **21:41**) correlated with "Aggregation" pages (lists of articles) rather than single breaking news stories. |
| **Seed Dominance** | Over **95%** of detected terms originated from the 3 seed domains, confirming the "walled garden" nature of high-quality financial news. |
| **The "Long Tail"** | Semantic analysis revealed a power-law distribution: the top 30 terms (e.g., *Market*, *Trend*) account for the vast majority of matches. |

---

## 🛠 Tech Stack

| Component | Tools Used |
| :--- | :--- |
| **Core Logic** | `Python`, `Collections (deque, defaultdict)` |
| **Scraping** | `Requests`, `BeautifulSoup4`, `Urllib` |
| **Analysis** | `Pandas`, `NumPy` |
| **Viz** | `Matplotlib`, `Seaborn` |
| **Stats** | `SciPy Signal Processing` |

---

## 🚀 Installation & Usage

### Prerequisites
Ensure you have Python 3.8+ installed.

### 1. Clone the Repo
```bash
git clone [https://github.com/yourusername/market-manipulation-crawler.git](https://github.com/yourusername/market-manipulation-crawler.git)
cd market-manipulation-crawler
