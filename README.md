# Customer Segmentation & Reward Strategy for TravelTide

This project focuses on helping TravelTide, an online travel booking platform, improve customer retention
through a data-driven reward system. Using behavioral data, I segmented customers, assigned value scores, 
and proposed personalized perks to increase engagement and loyalty.

**Project Walkthrough Video**: [Watch here]()

---

##  Project Overview

- **Goal:** Develop a reward strategy based on customer segmentation and value scoring to increase platform engagement and retention.
- **Data Sources:** Session, booking, hotel, flight, and user data from January 4, 2023, onward.
- **Target Users:** Customers with 8 or more sessions on the platform.

---

## Data Preparation

- Merged multiple datasets to get a full view of user behavior.
- Cleaned data: removed canceled bookings, recalculated trip duration and handled expected missing values.
- Feature engineering included:
  - Age derivation and bucketing
  - Session duration (in seconds)
  - Trip distance via Haversine formula
  - Booking rate and total spending
  - Customer value score (1–4)

---

## Customer Segmentation

Users were segmented based on booking frequency per session:
- **Low Booker:** ≤ 20% bookings per session
- **Occasional Booker:**  21%-50% bookings per session
- **Frequent Booker:**  51%-80% bookings per session
- **Super Booker:**   80% bookings per session

A **Customer Value Score (1–4)** was then assigned based on:
- Booking behavior
- Total spending
- Engagement level (session activity and duration)

---

## Key Findings (EDA)

- Most users fall under Low/Occasional Booker segments.
- Highest value users (Score 4) are rare but contribute significantly to revenue.
- Users aged 30–50 show the highest engagement and booking frequency.
- Higher scores have greater session time, clicks and spending.

---

##  Reward Strategy

| **Score** | **Perk**                                                | **Business Rationale**                                                                 |
|-----------|----------------------------------------------------------|------------------------------------------------------------------------------------------|
| 1         | 10% discount on next booking (valid 6 months)            | Drives first-time rebooking and encourages conversion among low-value users             |
| 2         | 3% personal discount (valid 1 year)                      | Incentivizes long-term retention and increases total customer spend                     |
| 3         | One-time free breakfast during stay                      | Adds perceived luxury, boosts user satisfaction without deep discounting                |
| 4         | Free hotel or flight upgrade (VIP perk)                  | Rewards loyalty, encourages advocacy and long-term brand affinity among top customers   |

---

##  Methodology

- Attempted unsupervised clustering (K-Means), but low Silhouette Scores led to a rule-based scoring instead.
- Visualized customer engagement and value with plots by score and behavior.
- Designed perks tailored to each group to maximize business impact.

---

##  Project Structure

```bash
customer_segmentation/
│
├── data/
│   ├── customer_perks.csv        # Final dataset with value scores and assigned perks
│   └── iata_icao.csv             # Airport location data used for distance calculation
│
├── docs/
│   ├── TravelTide_presentation.pptx.pdf       
│   └── TravelTide_report.pdf   
│ 
├── notebook/
│   └── traveltide_analysis.ipynb       
│
└── README.md                          
```


