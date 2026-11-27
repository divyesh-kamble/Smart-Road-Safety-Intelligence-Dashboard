<!-- ===================== HEADER BANNER ===================== -->
<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0B0F23,50:00ADFF,100:7C3AED&height=220&section=header&text=Smart%20Road%20Safety&fontSize=60&fontColor=ffffff&animation=fadeIn&fontAlignY=36&desc=Intelligence%20Dashboard&descSize=26&descAlignY=58" width="100%" alt="Smart Road Safety Banner"/>

<a href="https://git.io/typing-svg">
  <img src="https://readme-typing-svg.demolab.com?font=Segoe+UI&weight=600&size=22&duration=3000&pause=800&color=00ADFF&center=true&vCenter=true&width=700&lines=Black+Spot+Detection+%F0%9F%9A%A8;Risk+Factor+Analysis+%F0%9F%93%8A;Safety+Recommendations+%F0%9F%9B%A3%EF%B8%8F;Built+with+Power+BI+%E2%9A%A1" alt="Typing animation"/>
</a>

<br/>

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![DAX](https://img.shields.io/badge/DAX-0B0F23?style=for-the-badge&logo=microsoft&logoColor=00ADFF)
![Power Query](https://img.shields.io/badge/Power%20Query-217346?style=for-the-badge&logo=microsoftexcel&logoColor=white)
![Pages](https://img.shields.io/badge/Report%20Pages-5-7C3AED?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Completed-2EA043?style=for-the-badge)

<br/>

<img src="images/01-overview.png" alt="Dashboard Overview" width="92%"/>

<sub>👆 Overview page of the dashboard</sub>

</div>

---

## 🧭 Quick Navigation

<div align="center">

[📌 Overview](#-project-overview) •
[🎯 Objectives](#-objectives) •
[🧰 Tech Stack](#-tech-stack) •
[🗄️ Data Model](#️-data-model) •
[📊 Dashboard Pages](#-dashboard-pages) •
[🧮 KPIs](#-key-measures) •
[💡 Insights](#-key-insights) •
[✅ Recommendations](#-recommendations) •
[🚀 Run It](#-how-to-use)

</div>

---

## 📌 Project Overview

> **Road accidents are preventable, but only if we know where, when and why they happen.**

This project uses **Microsoft Power BI** to analyze 2018 road accident data. The dashboard turns raw records into interactive visuals showing accident trends, casualty impact, road characteristics, weather and lighting conditions, and junction-level risk, so safety teams can act on evidence.

<div align="center">

| 🚨 Detect | 🔍 Analyze | 🛡️ Recommend |
|:---:|:---:|:---:|
| Find accident hotspots and black spots | Understand risk factors behind severity | Turn findings into safety actions |

</div>

---

## 🎯 Objectives

- ✅ Track accident and casualty volume over time
- ✅ Compare severity (**Slight / Serious / Fatal**) across roads, junctions, weather and light
- ✅ Locate accident hotspots on a map
- ✅ Find which casualty age groups face the highest severity risk
- ✅ Convert findings into practical safety recommendations

---

## 🧰 Tech Stack

<div align="center">

| Tool | Used For |
|:---:|:---|
| <img src="https://img.shields.io/badge/Power%20BI-F2C811?style=flat-square&logo=powerbi&logoColor=black"/> | Report design, interactivity, page navigation |
| <img src="https://img.shields.io/badge/Power%20Query-217346?style=flat-square&logo=microsoftexcel&logoColor=white"/> | Data cleaning and transformation |
| <img src="https://img.shields.io/badge/DAX-0078D4?style=flat-square&logo=microsoft&logoColor=white"/> | KPI measures and calculations |
| <img src="https://img.shields.io/badge/Theme-Innovate%20Dark-0B0F23?style=flat-square"/> | Custom dark layout, 1920×1080 |

</div>

---

## 🗄️ Data Model

The model has **1 fact table** and **2 dimension tables**.

```mermaid
erDiagram
    Fact_Accidents ||--o{ Dim_Casualties : "Accident_Index"
    Fact_Accidents ||--o{ Dim_Vehicles : "Accident_Index"
    Fact_Accidents {
        string Accident_Index
        date Date
        string Accident_Severity
        float latitude
        float longitude
        string Road_Type
        string Junction_Detail
        int Speed_limit
        string Weather_Conditions
        string Light_Conditions
        string Road_Surface_Conditions
        int Number_of_Casualties
    }
    Dim_Casualties {
        string Accident_Index
        int Age_of_Casualty
        string Age_Band_of_Casualty
        string Casualty_Severity
    }
    Dim_Vehicles {
        string Accident_Index
    }
```

<details>
<summary><b>📸 View model diagram from Power BI</b></summary>
<br/>
<img src="images/data-model.png" alt="Data Model" width="90%"/>
</details>

---

## 📊 Dashboard Pages

<div align="center">

```mermaid
flowchart LR
    A([🏠 Overview]) --> B([🛣️ Analysis])
    B --> C([🎛️ Interactive])
    C --> D([💡 Insights])
    D --> E([🙏 Thank You])
    style A fill:#00ADFF,color:#fff,stroke:none
    style B fill:#7C3AED,color:#fff,stroke:none
    style C fill:#0EA5E9,color:#fff,stroke:none
    style D fill:#F59E0B,color:#fff,stroke:none
    style E fill:#2EA043,color:#fff,stroke:none
```

<sub>Every page has top-right navigation buttons to jump between pages.</sub>

</div>

<br/>

### 🏠 Page 1: Overview
High-level KPIs and trends with a 📅 **Date Range** slicer.

- 🔢 **KPI cards:** Total Accidents • Total Casualties • Avg Casualties per Accident • Fatal Accident %
- 📈 Monthly accident trends (line chart)
- 🍩 Accident severity distribution (donut)
- 📊 Accidents by day of week (column)
- 🚦 Accidents by speed limit (bar)
- 🌊 Casualties by month (area)

<div align="center"><img src="images/01-overview.png" width="90%" alt="Overview"/></div>

### 🛣️ Page 2: Road & Environmental Analysis

- 🗺️ **Accident Hotspots** map (latitude / longitude)
- 🌙 Severity by light condition (100% stacked bar)
- 🌧️ Accidents by weather condition (bar)
- 🔀 Severity by junction type (bar)
- 🧱 Accidents by road type (treemap)

<div align="center"><img src="images/02-analysis.png" width="90%" alt="Analysis"/></div>

### 🎛️ Page 3: Interactive Insights & Advanced Analysis

- 🏗️ Road type and junction analysis (stacked area, drill-down)
- 🎯 Casualty age vs severity risk (scatter)
- 🧊 Road surface vs severity (matrix)
- 🛤️ Road class severity breakdown (1st and 2nd class)
- 📆 Quarterly accident frequency and casualty impact (combo chart)

> 🧠 **Severity score guide**
> `3` = mostly **Slight** injuries • `2` = mostly **Serious** • `1` = higher share of **Serious / Fatal**.
> **Lower score = higher risk.**

<div align="center"><img src="images/03-interactive.png" width="90%" alt="Interactive Insights"/></div>

### 💡 Page 4: Key Insights & Recommendations
Project summary, findings, recommendations and conclusion.
<div align="center"><img src="images/04-insights.png" width="90%" alt="Key Insights"/></div>

### 🙏 Page 5: Thank You
Closing page: *"Road Pe Dhyan, Ghar Pe Muskaan!"*

---

## 🧮 Key Measures

<div align="center">

| | Measure | What it tells you |
|:---:|:---|:---|
| ⚠️ | `Total Accidents DAX` | How many accidents happened |
| 👥 | `Total Casualties DAX` | How many people were affected |
| 📊 | `Avg Casualties per Accident` | How severe an average accident is |
| 🚨 | `Fatal Accident %` | Share of accidents that were fatal |

</div>

---

## 💡 Key Insights

<table>
<tr>
<td width="50%">

🛣️ **Single carriageway roads** recorded the highest number of accidents.

🟢 **Slight accidents** made up the largest share of all accidents.

🔀 **Severity varied** across road types and junction details.

</td>
<td width="50%">

🚦 **Higher speed limits** showed greater average casualty impact per accident.

🌦️ **Weather and lighting** influenced both frequency and severity.

🎯 **Drill-down analysis** helped identify accident-prone junctions.

</td>
</tr>
</table>

---

## ✅ Recommendations

| # | Action | Focus |
|:-:|:---|:---:|
| 1 | Improve safety measures on high-risk roads | 🛣️ Roads |
| 2 | Install speed control and warning signs at accident-prone locations | 🚦 Speed |
| 3 | Enhance street lighting in critical areas | 💡 Lighting |
| 4 | Increase road safety awareness campaigns | 📢 Awareness |
| 5 | Strengthen emergency response systems | 🚑 Response |
| 6 | Use data-driven planning for future road infrastructure | 📊 Planning |

---

## 🚀 How to Use

```bash
# 1. Clone the repository
git clone https://github.com/your-username/smart-road-safety-dashboard.git
```

1. 📂 Open `Smart_Road_Safety_Intelligence_Dashboard_Final_Project.pbix` in **Power BI Desktop**
2. 🔗 If prompted, update the data source path: *Transform Data → Data source settings*
3. 📅 Use the **Date Range** slicer and click visuals to cross-filter
4. 🧭 Use the top-right buttons to move between pages

<details>
<summary><b>📁 Project structure</b></summary>

```
📦 smart-road-safety-dashboard
 ┣ 📜 Smart_Road_Safety_Intelligence_Dashboard_Final_Project.pbix
 ┣ 📂 data/        → source dataset(s)
 ┣ 📂 images/      → dashboard screenshots
 ┗ 📜 README.md
```
</details>

---

## 👤 Author

<div align="center">

**[Your Name]**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/your-profile)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/your-username)
[![Email](https://img.shields.io/badge/Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:you@example.com)

⭐ *If you found this project useful, give it a star!* ⭐

### 🚗 Road Pe Dhyan, Ghar Pe Muskaan! 😊

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:7C3AED,50:00ADFF,100:0B0F23&height=120&section=footer" width="100%" alt="Footer"/>

</div>
