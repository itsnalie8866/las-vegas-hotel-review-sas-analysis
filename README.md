# las-vegas-hotel-review-sas-analysis
This repository contains my MANG1041 – Business Analytics Programming I coursework on analysing TripAdvisor hotel reviews using SAS. The project includes a full SAS program, dataset, coursework brief, and the final submitted report.

---

# **Las Vegas Hotel Rating Prediction **

**Tools:** SAS (PROC IMPORT, PROC MEANS, PROC CORR, PROC REG, PROC SQL, ODS PDF)
**Dataset:** TripAdvisor Las Vegas Strip Hotels (UCI Machine Learning Repository)
**Grade:** **94/100**

This project analyses hotel reviews from 21 Las Vegas Strip properties to understand what drives higher customer ratings.
Using SAS, I built a complete analytical workflow—from import and cleaning to aggregation, modelling, correlation analysis, SQL filtering, and automated PDF reporting.

---

## 📁 **Repository Contents**

* **Coursework_Ans_SAS2.docx / .pdf** — full SAS program with answers, comments, and analysis  
* **Coursework_Ques_SAS2.pdf** — coursework specification and task instructions (Tasks 1–14) 
* **Las_Vegas.xlsx** — TripAdvisor hotel review dataset

---

## 📌 **Overview**

This project explores how hotel features—such as star rating, amenities, and traveller types—impact customer review scores on TripAdvisor.
The analysis concludes with a predictive linear regression model and a polished, client-style PDF report ranking high-performing hotels.

---

## 🎯 **Objectives**

* Understand the main drivers of higher hotel ratings
* Analyse rating differences between traveller segments (Couples, Families, Business, etc.)
* Build a hotel-level dataset with aggregated average scores
* Explore relationships between hotel characteristics and satisfaction
* Develop a regression model predicting hotel performance
* Automate reporting using SAS ODS PDF

---

## 🛠️ **Methodology**

### **1. Importing & Exploring the Dataset**

* Imported *Las_Vegas.xlsx* using `PROC IMPORT`
* Inspected variable formats, distributions, and categories
* Summarised:

  * User countries
  * Traveller types
  * Review scores

💡 *Finding:* Most reviewers were from only a few countries. Couples formed the largest traveller segment.

---

### **2. Descriptive Statistics by Traveller Type**

Used `PROC MEANS` with `CLASS traveler_type` to compare mean, min, max scores.

💡 *Insight:*

* **Families** and **Couples** tend to give higher ratings
* **Business travellers** provide the lowest, most critical scores

---

### **3. Creating a Hotel-Level Dataset (avg_score)**

Built a clean aggregated dataset:

* Created **hotels** with one row per hotel
* Calculated **avg_score** for each property
* Retained key attributes:

  * `hotel_stars`, `nr_rooms`
  * Amenities: `pool`, `gym`, `spa`, `tennis_court`, `free_internet`, `casino`

💡 *Outcome:* A ranked list of hotels based on average customer score.

---

### **4. Correlation Analysis**

`PROC CORR` examined the relationship between:

* **Hotel stars**
* **Number of rooms**

💡 *Insight:*
Higher-star hotels tend to be larger, but only **moderate correlation** — showing the strip has diverse hotel designs (boutique vs mega-resort).

---

### **5. Linear Regression Model (Predicting avg_score)**

Built using `PROC REG`:

**Dependent variable:** avg_score
**Predictors:**

* hotel_stars
* free_internet
* pool
* gym
* spa

💡 **Key Findings:**

* ⭐ More stars → significantly higher customer ratings
* ⭐ Spa presence & free internet → strong positive impact on satisfaction
* ⭐ Model performance:

  * R² ≈ 0.75 → strong predictive power
  * Amenities explain much of the variation, but not all (service quality missing)

---

### **6. Traveller Segment-Specific Scoring**

Filtered data for one segment (e.g., Families):

* Created **selected** dataset
* Built **hotels2** with segment-specific avg_score
* Sorted to identify top and bottom hotels

💡 *Insight:*
Traveller groups have distinct preferences — valuable for targeted hotel marketing.

---

### **7. Automated PDF Reporting (ODS PDF)**

Produced **hotels.pdf** using SAS ODS:

* Used **Sapphire** style
* Included only hotels with **avg_score ≥ 4.0**
* Sorted high → low
* Final columns: `hotel_name`, `hotel_stars`, `avg_score`
* Added title: **“The Best Hotels in Las Vegas”**

💡 *Outcome:* A polished, client-ready report automating insights presentation.

---

## 📊 **Key Insights**

### ⭐ What Drives Higher Ratings?

* Higher **hotel_star ratings** consistently lead to higher review scores
* Amenities such as **spa**, **free internet**, and **gym access** strongly enhance satisfaction
* Traveller segments behave differently — valuable for segmentation and marketing

---

### ⭐ Best-Performing Hotels (Overall)

High-end properties consistently rank top (UCI dataset examples):

* **The Venetian**
* **Bellagio**
* **Wynn Las Vegas**

These hotels regularly score **4.5+** across multiple traveller types.

---

## 💡 **Technical Skills Demonstrated**

* Advanced SAS programming (DATA steps, PROC SQL, PROC REG)
* BY-group aggregation
* Correlation & regression modelling
* Automated reporting with ODS PDF
* Data cleaning and transformation
* Turning analytics into clear business insights

---

## 📝 **Lecturer Feedback**

> “Full marks for your SAS analysis. Well-structured code, excellent reporting, and thorough regression interpretation.”

**Final score:** 94/100

---

## 🏁 **Outcome**

This project strengthened my ability to build **end-to-end analytical workflows**, from data preparation to modelling to automated reporting — reflecting the processes used in real business analytics teams.

