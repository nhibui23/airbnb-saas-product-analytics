# Airbnb NYC Product Analytics

*A growth playbook: where Airbnb should expand, what new hosts should build, and which features to deprioritize.*

**You're a Product Analyst at Airbnb. The growth team has one question:**  
**Where should we invest next, and what should a new host in that market do to succeed?**

I analyzed around 64,000 NYC listings across 5 boroughs to identify:
1. What host factors actually drive review ratings
2. Whether the Instant Book feature moves the needle on engagement
3. Which neighborhoods represent the biggest untapped growth opportunity

The result is a growth playbook for Airbnb on where to expand, what to build, and which features to deprioritize.

---

## Results at a Glance
- **Availability** is the #1 driver of review ratings (ANOVA p < 0.0001)
- **Instant Book** has no measurable impact on engagement (p = 0.38)
- **The Bronx** is the clearest growth opportunity with the highest ratings and lowest supply

## Key Findings

**Factors that significantly impact ratings:**
- Availability is the strongest predictor (ANOVA p < 0.0001, 3 significant pairs in Tukey's HSD)
- Monthly stays (8–30 nights) significantly outperform short and medium stays (p = 0.0001)
- Very high priced listings ($1000+) rate significantly lower than mid-range listings (p = 0.0004)

**Factors that do not matter:**
- Instant Book shows no significant impact on engagement (Welch's t-test p = 0.38, Cohen's d = 0.007, power = 14.3%), as all 4 validation methods confirm this
- Host identity verification has nearly no effect on ratings (p = 0.62)

**Growth opportunity:**
- The Bronx has the highest average rating (3.36), strong review activity (1.85/month), and the lowest listing supply among major boroughs (2,049)
- Mott Haven, Schuylerville, and Belmont are the top 3 neighbourhoods for targeted host acquisition

## Product Recommendations
1. Develop a pricing guidance tool to help hosts avoid overpricing relative to their listing quality
2. Promote monthly stays as a premium tier with dedicated host badges and guest discounts
3. Encourage hosts to schedule maintenance breaks rather than listing year-round
4. Focus host acquisition efforts in the Bronx, specifically Mott Haven, Schuylerville, and Belmont
5. Shift resources away from Instant Book as a growth lever

---

## Motivation
As a frequent traveler between Villanova and New York City, I have always been curious about what separates a great Airbnb listing from a mediocre one. Pricing seems inconsistent, quality varies widely, and some neighbourhoods clearly outperform others. This project takes a data-driven approach to understand what actually drives listing success on the Airbnb platform.

## Dataset
[Airbnb Open Data](https://www.kaggle.com/datasets/arianazmoudeh/airbnbopendata) — 102,599 NYC listings, cleaned down to 63,718 rows across 21 columns.

## Tools Used
- **Python** (pandas, numpy, matplotlib, seaborn, scipy, statsmodels) for analysis & statistical testing
- **PostgreSQL** for market segmentation & deep-dive queries
- **Power BI** for executive dashboard
- **Claude API** for AI-powered insight layer

## How to Read This Project

**If you have 2 minutes:** Read the Results at a Glance and Key Findings sections above.

**If you have 10 minutes:** Open `06_final_conclusion.ipynb` for the executive memo with specific recommendations.

**If you have 30 minutes:** Walk through notebooks 02–05 to see the full analysis, statistical testing, and decision logic.

## Project Structure
