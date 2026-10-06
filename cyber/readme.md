<img width="752" height="223" alt="image" src="https://github.com/user-attachments/assets/126b2649-624a-4257-837b-1640b96a64e3" />
![Uploading image.png…]()
# 🛡️ Global Cybersecurity Attacks & Financial Impact: Power BI Analytics Dashboard

An executive-level business intelligence and data analytics dashboard built using **Microsoft Power BI**. This project explores global cybersecurity threat metrics, financial losses by country and industry, attack vector distributions, and defensive mechanism utilization.

---

## 🏗️ Project Architecture & Data Model Flow

The Power BI solution is structured around a relational star/snowflake schema model optimized for cross-filtering and high-performance slicing:

```text
[ Global_Cybersecurity_Threat_Data (Fact Table) ]
  ├── Columns: Attack_ID, Country, Attack Source, Defense Mechanism Used, 
  │            Financial Loss, Resolution Time, Affected Users, Target Industry
  │
  └── (1-to-Many Relationship: 1-*) ──► [ Attack_desc (Dimension Table) ]
                                            ├── Columns: Attack_ID, Attack Type
                                            │
                                            └── [ Measure Table & Metrix ]
                                                  ├── Measures: Avg_financial_loss
                                                  └── Slicers / Dynamic Metrics

```

---

## 🔍 Detailed Dashboard Architecture & Workflow

### 1. Data Model & Relationships

* **Fact Table (`Global_Cybersecurity_Threat_Data`):** Contains granular logs of individual cyber incidents, tracking metrics like financial loss, affected user counts, incident resolution times in hours, and attack sources.
* **Dimension Table (`Attack_desc`):** Connects to the main log table via a one-to-many relationship (`1-*`) using `Attack_ID`, categorizing records by distinct attack types (e.g., Malware, Ransomware, DDoS, Phishing, SQL Injection, Man-in-the-Middle).
* **Measures & Metrics Tables:** Houses custom DAX calculations (such as `Avg_financial_loss`) to keep the data model clean, modular, and performant.

### 2. Interactive Filtering & Global Slicers

The dashboard utilizes top-level global slicers for seamless drill-down analysis across multiple variables:

* **Country Filter:** Isolate cyber incidents by specific geographical regions.
* **Year Filter:** Analyze multi-year temporal trends (e.g., historical changes from 2015 to 2019).
* **Target Industry & Attack Type Filters:** Slice metrics dynamically by vulnerable sectors (Banking, Education, Healthcare, Government, IT, Retail) and specific attack vectors.

### 3. Key Performance Indicators (KPI Cards) & Visualizations

* **Executive Summary Cards:** Display high-level aggregates including Total Financial Loss ($151.48K+), Total Affected Users (1.51B), Max Resolution Hours (72h), Total Attack Count (3,000), and Targeted Industries Count (7).
* **Total Financial Loss by Country (Bar Chart):** Ranks nations by financial exposure, showing top impacted countries like the UK, Germany, Brazil, Australia, and others.
* **Total Financial Loss by Attack Type (Donut Chart):** Visualizes the financial weight of distinct vectors such as Phishing (17.62%), SQL Injection (16.61%), Ransomware (16.16%), and Malware (15.82%).
* **Target Industry Matrix Table:** Cross-references industries against yearly timelines (2015–2019) to highlight sector vulnerability shifts.
* **Defense Mechanism & Attack Percentage Distribution:** Analyzes defensive tool usage (e.g., VPN, Antivirus, Encryption) alongside severity percentages (Low, Medium, High).

---

## 🚀 Key Features

* **Cross-Filtering Integration:** Clicking on any country, industry, or attack type instantly filters all other visuals on the canvas.
* **DAX Measures:** Custom calculations providing precise financial averages and total risk exposure.
* **Executive Design Layout:** A dark-themed, modern BI interface built for presentation to security stakeholders and management teams.

---

## 🛠️ Tech Stack & Tools

* **Data Visualization & BI:** Microsoft Power BI Desktop
* **Data Modeling:** Power Query, DAX (Data Analysis Expressions)
* **Data Source:** Relational CSV logs / Threat telemetry datasets

---

## 📂 Project Structure

```text
├── Global_Cybersecurity_Attacks_Dashboard.pbix   # Main Power BI file
├── datasets/                                     # Source CSV files (Threats, Attack Types, Metrics)
└── README.md                                     # Project documentation

```

---

## ⚙️ How to View and Run

1. Make sure you have **Microsoft Power BI Desktop** installed on your Windows machine.
2. Clone or download this repository to your local directory.
3. Double-click the `.pbix` file to open the dashboard in Power BI Desktop.
4. Use the global slicers at the top of the canvas to interact with the data filters and explore threat trends.

---

 
