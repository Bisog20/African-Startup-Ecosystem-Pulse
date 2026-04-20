<img width="735" height="951" alt="image" src="https://github.com/user-attachments/assets/515088c7-1bfc-43f0-97f4-86a0d1eb7890" /># African-Startup-Ecosystem-Pulse

An interactive Power BI dashboard analyzing startup funding trends across Africa from 2022 to 2024.

![Dashboard Preview](dashboard-preview.png)

---

## Overview

This project explores the African startup funding landscape using data from Disrupt Africa's annual funding reports. It covers 1,239 funded startups across 31 countries, providing a comprehensive view of where capital is flowing, which sectors are attracting the most investment, and how the ecosystem has evolved over three years.

---

## Key Insights

- **$6.54B** in total funding raised across 2022–2024
- **Nigeria, Egypt, and Kenya** dominate, accounting for the majority of all funding
- **Fintech** remains the leading sector at $2.8B, with Energy emerging as a fast-growing second
- **75.9%** of funded startups have local founders
- Funding peaked in 2022 and has trended downward through 2024, reflecting broader global VC headwinds

---

## Dashboard Features

- **KPI Cards** — Total funding raised, startups funded, countries represented, and average deal size
- **Funding by Country** — Horizontal bar chart ranking all 31 represented African countries
- **Funding Trend by Year** — Line chart showing year-over-year capital flow from 2022 to 2024
- **Funding by Stage and Location** — Stacked bar chart breaking down investment stage across countries
- **Funding by Sector** — Bar chart ranking sectors from Fintech to Ed-Tech
- **Local vs International Founders** — Donut chart showing the founder origin split
- **Year Slicer** — Filter the entire dashboard by 2022, 2023, or 2024

---

## Data Source

Data sourced from **[Disrupt Africa](https://disruptafrica.com/research/)** — African Tech Startups Funding Reports for 2022, 2023, and 2024. Reports are open-sourced and freely available on their research page.

**Columns used:**
`Startup`, `Location`, `Sector`, `Date`, `Amount`, `Investors`, `Stage`, `Debt/Equity`, `Local Founder`, `Intl Founder`, `Launched`, `Accelerator`, `Employees`

---

## Tools Used

- **Power BI Desktop** — Dashboard building and data visualization
- **Power Query** — Data cleaning, transformation, and appending multiple year datasets
- **DAX** — Custom measures for Avg Deal Size, Local Founder %, and Intl Founder %

---

## How to Use

1. Clone or download this repository
2. Download the source data from [Disrupt Africa Research](https://disruptafrica.com/research/) for 2022, 2023, and 2024
3. Open the `.pbix` file in Power BI Desktop
4. Refresh the data source to point to your local data files
5. Explore the dashboard using the year slicer to filter by specific years

---

## DAX Measures

```dax
Avg Deal Size = DIVIDE(SUM('StartupData'[Amount]), COUNT('StartupData'[Startup]))

Local Founder % = DIVIDE(
    CALCULATE(COUNT('StartupData'[Startup]), 'StartupData'[Local Founder] = "Yes"),
    COUNT('StartupData'[Startup])
) * 100

Intl Founder % = DIVIDE(
    CALCULATE(COUNT('StartupData'[Startup]), 'StartupData'[Intl Founder] = "Yes"),
    COUNT('StartupData'[Startup])
) * 100
```

---

## Project Structure

```
african-startup-pulse/
│
├── AfricanStartupPulse.pbix       # Power BI dashboard file
├── data/
│   ├── disrupt_africa_2022.xlsx
│   ├── disrupt_africa_2023.xlsx
│   └── disrupt_africa_2024.xlsx
├── dashboard-preview.png          # Screenshot of the dashboard
└── README.md
```

---

## Author

Built as a data analysis project exploring African startup funding patterns using publicly available ecosystem data.

---

## License

This project is open source. Data is sourced from Disrupt Africa and subject to their terms of use.
