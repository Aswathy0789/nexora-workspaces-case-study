# Nexora Workspaces: FY2025 Operations Analysis

## Project Overview

This project is a business operations case study built around a fictional multinational flexible workspace operator, Nexora Workspaces, modeled closely on my real experience working in operations at IWG/Regus. The goal was to take a year of messy, realistic operational data across seven global locations and turn it into a set of clear findings that a leadership team could actually act on. The full workflow covers data cleaning, formula based analysis, PivotTables, budget variance, and a set of business conclusions.

## Tools Used

The dataset was cleaned using Power Query inside Power BI Desktop, then exported into Excel Online for formula work, PivotTables, and analysis. This combination reflects how these tools are used together in a real operations role, where Power BI often handles the heavier data transformation and Excel is used for the day to day reporting and ad hoc analysis.

## The Business Scenario

Nexora Workspaces operates coworking locations across three regions: MEA (Dubai and Abu Dhabi), APAC (Bengaluru, Gurgaon, and Singapore), and EMEA (London and Manchester). Each location reports monthly figures including desk occupancy, revenue, operating cost, service tickets raised and resolved, customer satisfaction, and budgeted targets for revenue and cost.

## Data Cleaning

The raw dataset had the kind of quality issues that show up in real operational reporting. Location names were entered inconsistently, with different spacing, capitalization, and hyphen formatting for the same physical office, for example "Gurgaon Cyber Hub" appearing as "GURGAON CYBER HUB" in some rows. There were also a small number of fully duplicated rows and a handful of missing values in the Tickets Resolved and Customer Satisfaction columns.

Working through Power Query, I standardized the location names using Trim and Capitalize Each Word, then used the Group By feature to confirm every location collapsed down to a single consistent spelling before removing duplicates. This step mattered because checking for duplicates before fixing the naming inconsistencies would have missed rows that were true duplicates but were being read as different locations due to spelling differences.

For the missing values, rather than deleting rows or filling in estimated numbers, I checked whether the gaps were random or clustered. Customer Satisfaction was missing in about four percent of rows, spread across different locations and months with no pattern. Tickets Resolved was also missing in about four percent of rows, and while the months were random, two of the four missing values did come from the same location, Bengaluru Whitefield. Given how small that sample size is, it was not treated as conclusive evidence of a systemic issue, but it was noted as something worth watching if it recurred in a larger dataset. In both cases the missing values were left as true blanks and handled using formulas that exclude blanks automatically, rather than being filled with invented numbers.

![Data Cleaning in Power BI](images/data%20cleaning.png)

## Key Findings

**Occupancy.** Gurgaon Cyber Hub had the highest average occupancy rate across the year at just over eighty seven percent, while Bengaluru Whitefield had the lowest at just under sixty six percent.

![2025 Revenue, Occupancy, and Operating Cost Summary](images/2025%20avg%20revenueoccupanyoperatingcost.png)

**Revenue.** London Canary Wharf generated the highest total revenue for the year, followed closely by Dubai Downtown. This did not fully align with occupancy performance, since London's occupancy rate was actually below average. The likely explanation is that EMEA locations command a higher revenue per desk, possibly due to a more premium client base or additional services such as meeting room usage, though the dataset does not break revenue down by service type, so this remains a hypothesis rather than a confirmed driver.
Looking at revenue by region across each month, both EMEA and MEA show minor month to month dips within an overall upward trend, for example EMEA in October and MEA in April and August, marked in the screenshot below. These are small fluctuations rather than a real decline, since both regions still grew significantly from January to December, but they may be worth checking against seasonal demand patterns

![Monthly Revenue by Region](images/Monthly%20revenue%20by%20region.png)


**Profit and Margin.** After calculating operating cost against revenue, Gurgaon Cyber Hub stood out as the strongest performer, with a profit margin of just over thirty seven percent, nearly double that of London despite London's higher raw revenue. Bengaluru Whitefield had the weakest margin at just under sixteen percent, driven by a combination of below average occupancy and comparatively high operating costs.

![Profitability by Location](images/Profibility%20by%20location.png)

**Service Quality.** Ticket resolution rates followed a similar pattern. Gurgaon and Manchester resolved over ninety percent of tickets raised, while Bengaluru resolved only about seventy two percent, the weakest of all seven locations.

![Ticket Resolution Rate by Location](images/Ticket%20resolution.png)

**Budget Performance.** Comparing actual results against budgeted targets, Gurgaon Cyber Hub beat its revenue budget by nearly thirty two percent, the strongest overperformance in the portfolio. Bengaluru Whitefield was the only location to miss its revenue budget, falling just under two percent short. On the cost side, Abu Dhabi Corniche was the only location that came in under its cost budget, while Manchester City Centre had the largest proportional cost overrun.

![Revenue Variance by Location](images/Revenue%20Variance.png)
![Operating Cost Variance by Location](images/Cost%20variance.png)

## Conclusion

Across every metric measured, occupancy, profit margin, ticket resolution, and budget performance, Gurgaon Cyber Hub was consistently the strongest performing location, while Bengaluru Whitefield was consistently the weakest. This kind of agreement across several independent metrics makes the pattern more credible than any single number on its own. The recurring link between slower ticket resolution and weaker occupancy at Bengaluru suggests that service responsiveness may be affecting client retention there, and it would be worth investigating with more detailed data, such as ticket categories, to confirm whether this is really driving the underperformance or whether other factors are involved.

## Skills Demonstrated

This project involved data cleaning and standardization in Power Query, SUMIFS and AVERAGEIFS based analysis, PivotTable construction across multiple dimensions, budget variance analysis, and translating raw operational numbers into a clear, leadership ready narrative.

