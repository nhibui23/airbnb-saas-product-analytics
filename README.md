# Airbnb NYC Project

## Motivation
As a frequent traveler between Villanova and New York City, I have always been curious about what separates a great Airbnb listing from a mediocre one. Pricing seems inconsistent, quality varies widely, and some neighbourhoods clearly outperform others. This project therefore takes a data-driven approach to understand what actually drives listing success on the Airbnb platform.

Using the public NYC Airbnb dataset (~102K listings), I conducted a full product analytics investigation from data cleaning and exploratory analysis through A/B testing and formal statistical testing to deliver actionable recommendations for Airbnb's product team.

## Dataset
[Airbnb Open Data](https://www.kaggle.com/datasets/arianazmoudeh/airbnbopendata) with 102,599 NYC listings, cleaned down to 63,718 usable rows across 21 columns.

## Business Questions
1. What host-controlled factors most significantly impact review ratings?
2. Does enabling Instant Book lead to higher review engagement?
3. Which neighbourhoods show the strongest potential for growth?

## Key Findings

**Factors that significantly impact ratings:**
- Availability is the strongest predictor (ANOVA p < 0.0001, 3 significant pairs in Tukey's HSD)
  => Hosts who list less frequently achieve higher ratings, likely due to better maintenance and preparation between guests.
- Monthly stays (8–30 nights) significantly outperform short and medium stays (p = 0.0001)
  => Both hosts and guests appear more invested in longer commitments.
- Very high priced listings ($1000+) rate significantly lower than mid-range listings (p = 0.0004)
  => Guest expectations scale with price, and when listings fail to deliver, ratings suffer.

**Factors that do not matter:**
- Instant Book shows no significant impact on engagement (Welch's t-test p = 0.38, Cohen's d = 0.007, power = 14.3%), as all 4 validation methods confirm this.
- Host identity verification has nearly np effect on ratings (p = 0.62).

**Growth opportunity:**
- The Bronx has the highest average rating (3.36), strong review activity (1.85/month), and the lowest listing supply among major boroughs (2,049)
- Mott Haven, Schuylerville, and Belmont are the top 3 neighbourhoods for targeted host acquisition.

## Project Structure

```
├── data/
│   ├── Airbnb_Open_Data.csv
│   └── Airbnb_Open_Data_Cleaned.csv
├── notebook/
│   ├── 01_data_prep.ipynb
│   ├── 02_eda.ipynb
│   ├── 03_ab_testing.ipynb
│   ├── 04_location_analysis.ipynb
│   ├── 05_statistical_testing.ipynb
│   └── 06_final_conclusion.ipynb
├── sql/                              # Coming soon
├── requirements.txt
└── README.md
```

## Methodology
- **Data Cleaning:** Removed dollar signs from price columns, dropped inactive listings with no reviews, handled outliers including negative minimum nights and availability exceeding 365 days
- **EDA:** Explored initial distributions and group comparisons using histograms, bar charts, box plots, and correlation heatmaps
- **A/B Testing:** Welch's t-test comparing instant bookable vs non-instant bookable listings, which was later validated with Cohen's d effect size, post-hoc power analysis, 95% confidence intervals, and KDE distribution plots.
- **Statistical Testing:** ANOVA with Tukey's HSD post-hoc correction for multi-group comparisons, which contrasted with my findings in EDA.

## Product Recommendations
1. Develop a pricing guidance tool to help hosts avoid overpricing relative to their listing quality
2. Promote monthly stays as a premium tier with dedicated host badges and guest discounts
3. Encourage hosts to schedule maintenance breaks rather than listing year-round
4. Focus host acquisition efforts in the Bronx, specifically Mott Haven, Schuylerville, and Belmont
5. Shift resources away from Instant Book as a growth lever

## Limitations
- Snapshot data only
  => We can't track how listings evolve over time
- No actual booking or revenue data
  => These reviews serve as a proxy for demand
- Review ratings are small groups (1–5)
  => Hard to identify differences between groups
- All findings are correlational, not causal
  => We can't land at a definite conclusion for causal relationships
- Results are specific to NYC and may not generalize to other markets
  => This strategy may differ from other trends in other areas
- No revenue metrics
  => We can't specifically make decisions related to revenue growth, as listing priced high but rarely booked can't be distinguished from one that is both high-priced and popular

## Future data needed
- Booking volume data to measure actual demand
- Time-series data to validate whether recommendations improve outcomes
- Listing photo and description quality for potential maintenance suggestions
- Guest demographics to understand rating behavior across traveler types
- Competitor pricing data to build the recommended pricing tool

## Tools
Python (pandas, numpy, seaborn, matplotlib, scipy, statsmodels) · SQL (PostgreSQL — coming soon) · Power BI (coming soon)

## Author
**Nhi Bui** — Villanova University  
[LinkedIn](https://linkedin.com/in/nhiuyenbui) · [GitHub](https://github.com/nhibui23)
