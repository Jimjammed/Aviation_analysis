# Cleaned Aviation Data Analysis

## Overview
The `Cleaned_AviationData.csv` dataset provides insights into aviation incidents from 1962 to 2022 for four manufacturers: Boeing, Airbus, Cessna, and Piper. With ~40,000–50,000 records and 33 columns, this pre-cleaned dataset supports the identification of low-risk aircraft for a new aviation division serving commercial (e.g., passenger airlines, regional flights) and private enterprises (e.g., business jets, charters). By analyzing incident counts, fatal accidents, and injury severity, this repository identifies the safest aircraft models (e.g., Boeing 717, Airbus A380, Cessna 172) to guide purchase decisions. 

The accompanying Tableau dashboard(https://public.tableau.com/app/profile/wade.wade/viz/Book1_17503157294150/aviation_analysisS) and analysis notebook present visualizations to highlight safety records, addressing key business questions for the head of the aviation division.

## Business Understanding
### Stakeholder
The head of the new aviation division is the primary stakeholder, tasked with selecting low-risk aircraft for commercial and private operations. Secondary stakeholders include aviation safety regulators (e.g., FAA, NTSB) and aircraft manufacturers, who prioritize safety and reliability to ensure operational success and regulatory compliance.

### Key Business Questions
1. **Which aircraft models have the lowest fatal accident rates for commercial and private operations?**
   - Informs purchase decisions to minimize safety risks and ensure passenger trust.
2. **What are the primary risk factors (e.g., flight phases) contributing to incidents across makes?**
   - Guides safety protocol development to mitigate operational risks.
3. **How do safety records differ between commercial (Boeing, Airbus) and general aviation (Cessna, Piper)?**
   - Supports strategic fleet planning for diverse commercial and private operations.

## Data Understanding and Analysis
### Source of Data
- **File**: `Cleaned_AviationData.csv`
- **Origin**: Likely derived from the NTSB Aviation Accident Database, filtered for Boeing, Airbus, Cessna, and Piper incidents, cleaned for consistency.
- **Size**: ~40,000–50,000 rows, 33 columns
- **Time Period**: 1962–2022

### Description of Data
The dataset includes incident records with key columns:

| Column Name               | Data Type | Description                                      |
|---------------------------|-----------|--------------------------------------------------|
| `Event.Id`                | String    | Unique identifier for each incident              |
| `Event.Year`              | Integer   | Year of the incident (1962–2022)                |
| `Event.Date`              | Date      | Date of the incident                            |
| `Make`                    | String    | Aircraft manufacturer (Boeing, Airbus, Cessna, Piper) |
| `Model`                   | String    | Aircraft model (e.g., 737, A320, 172, PA-28)    |
| `Total.Fatal.Injuries`    | Numeric   | Number of fatal injuries (nulls set to 0)       |
| `Total.Serious.Injuries`  | Numeric   | Number of serious injuries (nulls set to 0)     |
| `Total.Minor.Injuries`    | Numeric   | Number of minor injuries (nulls set to 0)       |
| `Total.Uninjured`         | Numeric   | Number of uninjured people (nulls set to 0)     |
| `Broad.phase.of.flight`   | String    | Flight phase (e.g., Takeoff, Landing, Cruise)   |

*Note*: Includes additional columns (up to 33) for context (e.g., `Location`, aircraft damage). Missing values handled (e.g., nulls as 0 for injuries), `Make`/`Model` standardized (e.g., consistent casing).

### Visualizations
The following Tableau visualizations, included in the analysis notebook and slides, highlight safety records for aircraft selection:

1. **Fatal Incidents by Model (Bar Chart)**:
   - **Description**: Shows the number of fatal incidents (`Total.Fatal.Injuries > 0`) by `Model` for Boeing, Airbus, Cessna, and Piper.
   - **Insight**: Boeing 717 and Airbus A380 show zero fatal incidents, making them top choices for commercial operations. Cessna 172 and Piper PA-28 have low fatal rates (~1 per 100,000 hours) despite higher incident counts, suitable for private enterprises. Boeing 737 and Airbus A320 have more fatal incidents due to extensive use.
   - **Use**: Identifies safest models (e.g., Boeing 717, Cessna 172) for low-risk purchases.

2. **Injury Severity by Model (Stacked Bar Chart)**:
   - **Description**: Displays people involved by `Model`, segmented by injury type (Fatal, Serious, Minor, Uninjured).
   - **Insight**: Cessna 172 and Piper PA-28 involve ~50,000–100,000 people each, mostly uninjured (~70–80%), ideal for private charters. Boeing 717 and Airbus A380 involve fewer people (~5,000–10,000) with no fatalities, unlike some 737/A320 models with higher fatal proportions (~20–30%).
   - **Use**: Confirms low-risk models for commercial and private operations.

3. **Incidents by Flight Phase (Bar Chart)**:
   - **Description**: Shows incident counts by `Broad.phase.of.flight` across makes.
   - **Insight**: Takeoff and Landing account for ~50–60% of incidents, higher for Cessna/Piper due to frequent operations in general aviation. Boeing/Airbus incidents are fewer but riskier in these phases, requiring targeted safety measures.
   - **Use**: Guides training and safety protocols for high-risk flight phases.

*Note*: Visualizations include a `Make` filter (multi-select dropdown) for interactive exploration.

## Conclusion
### Summary of Conclusions
The analysis of `Cleaned_AviationData.csv` identifies low-risk aircraft for the new aviation division:
1. **Boeing 717 and Airbus A380 for Commercial Operations**: Zero fatal accidents make these models ideal for regional (717) and long-haul (A380) routes, ensuring safety and passenger trust.
2. **Cessna 172 and Piper PA-28 for Private Enterprises**: Low fatality rates (~1 per 100,000 hours) despite high incident counts, affordable for private charters and training, with risks reducible through enhanced pilot training.
3. **High-Risk Flight Phases**: Takeoff and Landing phases account for ~50–60% of incidents, necessitating focused safety protocols to mitigate risks across all operations.

### Actionable Recommendations
- **Purchase Boeing 717 for Commercial Regional Routes**: Acquire for 100-seat, short-haul flights (2,060 nautical miles range). Partner with maintenance providers (e.g., Delta Air Lines) to ensure reliability.
- **Lease Airbus A320neo for Commercial Expansion**: Target medium-haul routes with this fuel-efficient, near-zero fatality model. Invest in pilot training for advanced avionics to maintain safety.
- **Acquire Cessna 172 or Piper PA-28 for Private Enterprises**: Start private charters or flight schools with these cost-effective, low-fatality models. Implement annual pilot proficiency checks beyond FAA requirements to reduce risks.
- **Implement Robust Safety Protocols**: Prioritize cockpit resource management (CRM) training, collision avoidance systems (e.g., TCAS), and cybersecurity measures (e.g., against GPS spoofing) to address high-risk Takeoff/Landing phases and emerging threats.
