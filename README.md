# COVID-19 Dataset Analysis


> **Comprehensive Power BI implementation for global COVID-19 pandemic tracking and analysis**


## 📊 Executive Summary

This project provides comprehensive documentation and implementation of a COVID-19 dataset analysis using **Microsoft Power BI**. The analysis encompasses data from multiple authoritative sources, tracking confirmed cases, recoveries, and deaths globally. Through systematic data transformation and modeling, this project delivers actionable insights into the pandemic's progression and impact.

### Key Achievements

✅ Unified data model consolidating multiple COVID-19 metrics  
✅ Normalized date structure enabling time-series analysis  
✅ Geographic dimension supporting location-based insights  
✅ Optimized data model with proper relationships and data types  
✅ Real-time data connectivity for continuous monitoring

## 🎯 Project Overview

### Objectives

- 🌍 Analyze global COVID-19 trends across confirmed cases, recoveries, and deaths
- 🔗 Create a unified data model for comprehensive pandemic tracking
- 📈 Enable time-series visualization of pandemic progression
- 🗺️ Provide geographic insights into COVID-19 distribution

### Tools and Technologies

| Tool | Purpose |
|------|---------|
| **Microsoft Power BI Desktop** | Primary analysis and visualization platform |
| **Power Query Editor** | Data transformation and cleaning |
| **Web Data Connector** | COVID-19 dataset retrieval |

## 📡 Data Sources

The project utilizes real-time data from the **Johns Hopkins CSSE COVID-19 Data Repository**:

### Dataset URLs

```
Confirmed Cases:
https://raw.githubusercontent.com/CSSEGISandData/COVID-19/master/csse_covid_19_data/csse_covid_19_time_series/time_series_covid19_confirmed_global.csv

Recovered Cases:
https://raw.githubusercontent.com/CSSEGISandData/COVID-19/master/csse_covid_19_data/csse_covid_19_time_series/time_series_covid19_recovered_global.csv

Death Cases:
https://raw.githubusercontent.com/CSSEGISandData/COVID-19/master/csse_covid_19_data/csse_covid_19_time_series/time_series_covid19_deaths_global.csv
```

### Data Loading Process

1. Launch Power BI Desktop
2. Access 'Get Data' menu
3. Select 'Web' as data source connector
4. Load each dataset (Confirmed, Recovered, Deaths)

## 🔧 Technical Implementation

### Data Cleaning & Transformation

All transformations are performed using **Power Query Editor**:

#### 1. Initial Data Preparation

- **Header Configuration**: Promoted first row to column headers
- **Data Validation**: 
  - ✓ Unique key analysis
  - ✓ Null value detection
  - ✓ Data type verification
- **Column Optimization**: Removed redundant fields

#### 2. Data Restructuring

```
Transformation Steps:
├── Unpivot date columns (wide → long format)
├── Rename columns
│   ├── 'Attribute' → 'Date'
│   └── 'Value' → 'Cases'
├── Convert data types (text → date)
└── Create 'Status' column (Confirmed/Recovered/Deaths)
```

#### 3. Query Standardization

Applied identical transformations to all three data sources:

- ✅ Confirmed Cases Query
- ✅ Recovered Cases Query  
- ✅ Death Statistics Query

#### 4. Location Dimension Creation

Created dedicated Location query for geographic analysis:

- **Source**: Derived from Confirmed Cases query
- **Purpose**: Enable geographic filtering and hierarchical analysis
- **Structure**: Consistent with fact tables

### Data Integration

#### Consolidation Query

Combined all three status-specific queries into a unified fact table:

```
Append Operation:
  ├── Confirmed Cases
  ├── Recovered Cases
  └── Death Cases
  
Result: Single table with status differentiation
```

#### Data Modeling

Established relationships for cross-table analysis:

| Configuration | Value |
|---------------|-------|
| **Primary Key** | Date column |
| **Cardinality** | One-to-Many |
| **Filter Direction** | Single direction |
| **Connected Tables** | Consolidation, Location, Status queries |

## 🎨 Data Pipeline

```mermaid
graph LR
    A[Web Data Source] --> B[Power Query]
    B --> C[Data Cleaning]
    C --> D[Transformation]
    D --> E[Consolidation]
    E --> F[Data Model]
    F --> G[Visualizations]
    G --> H[Dashboard]
```

## 📈 Analysis Findings

### The Big Picture

We tracked COVID-19 across **201 locations worldwide**, revealing critical insights into the pandemic's global impact:

#### Overall Impact Statistics

| Metric | Count | Percentage |
|--------|-------|------------|
| **Confirmed Cases** | 317 billion | 91.91% (active) |
| **Recovered** | 23 billion | 6.81% |
| **Deaths** | 4 billion | 1.28% |

> 💡 While any loss of life is tragic, the recovery rate shows that most people who contracted the virus survived.

### 📊 Temporal Analysis: What Happened Over Time

The pandemic showed distinct phases with clear patterns:

| Year | Confirmed Cases | Trend | Key Insight |
|------|----------------|-------|-------------|
| **2020** | 76 billion | Initial outbreak | Relatively low baseline |
| **2021** | Rising sharply | Escalation phase | Rapid global spread |
| **2022** | 196 billion | **Peak period** | Highest case numbers recorded |
| **2023** | Significant decline | Recovery phase | Marked improvement |

**Key Observation**: Cases peaked in 2022 and showed a significant decline by 2023, indicating we're now in a much better position than at the height of the crisis.

#### ⚠️ Data Inconsistency Alert

**Critical Finding**: While the analysis confirms a drop in confirmed cases in 2023, the number of recovered cases did not increase proportionally to support this claim. Specifically:

- ❌ **Expected**: Recovered cases should increase as confirmed cases decrease
- 📉 **Observed**: The drop in confirmed cases in 2023 did not tally with recovered cases
- 🔍 **Implication**: Potential data collection gaps or reporting inconsistencies in the recovery tracking

This inconsistency requires further investigation to ensure accurate pandemic status reporting.

### 🌍 Geographic Hotspots

Three countries bore the brunt of the pandemic, representing significant case concentrations:

#### Top 3 Most Affected Countries

**1. 🇺🇸 United States**
- **Confirmed Cases**: 53 billion
- **Status**: Highest total case count globally
- **Impact**: Bore the largest burden of the pandemic

**2. 🇮🇳 India**
- **Confirmed Cases**: 29 billion
- **Notable Achievement**: Highest recovery rate among top-affected nations
- **Success Factor**: Effective recovery protocols and healthcare response

**3. 🇧🇷 Brazil**
- **Confirmed Cases**: 21 billion
- **Notable Achievement**: Second-highest recovery rate
- **Success Factor**: Strong recovery management strategies

> 💡 **Pattern Identified**: Large, densely populated countries with high international connectivity were hit hardest. However, India and Brazil demonstrated effective recovery protocols that can serve as models for other nations.

### 📅 Seasonal Patterns & Timing Analysis

Breaking down the data by quarter revealed consistent seasonal trends:

| Quarter | Case Volume | Pattern |
|---------|-------------|---------|
| **Q1** | Highest | Peak transmission period |
| **Q2** | Lowest | Reduced transmission |
| **Q3** | Moderate-High | Secondary peak |
| **Q4** | High | Elevated transmission |

**Key Insight**: Quarter 1 consistently had the highest case numbers across all years, with Quarters 4 and 3 following. Quarter 2 had the lowest numbers. This seasonal pattern suggests the virus spread more readily during certain times of the year.

### 💡 Strategic Recommendations

#### What This Means Going Forward

Based on comprehensive data analysis, the following strategic actions are recommended:

**1. Regional Vigilance**
- 🎯 Maintain heightened monitoring in heavily affected regions
- 📊 Focus resources on US, India, and Brazil for continued support
- 🔍 Track emerging hotspots before they escalate

**2. Adopt Proven Recovery Strategies**
- 🇮🇳 **India Model**: Implement effective recovery protocols that achieved highest recovery rates
- 🇧🇷 **Brazil Model**: Apply successful methods that led to second-highest recoveries
- 🔄 Share best practices globally to improve recovery outcomes

**3. Seasonal Preparedness**
- 📅 **Q1 Preparation**: Increase readiness during Quarter 1 (historically highest cases)
- 🛡️ **Q4/Q3 Vigilance**: Maintain elevated preparedness in Quarters 3 and 4
- 📉 **Q2 Optimization**: Use Quarter 2's lower transmission period for recovery and planning

**4. Data Quality Improvement**
- 🔍 Address identified inconsistencies in recovery data reporting
- 📊 Standardize data collection methodologies globally
- ✅ Implement validation checks to ensure recovered cases align with confirmed case trends

**5. Future Pandemic Preparedness**
- 📚 Document lessons learned from peak periods
- 🌐 Strengthen global health surveillance systems
- 🤝 Foster international collaboration on health data sharing

### 📊 Current Status Assessment

**Positive Trends:**
- ✅ Moved past the peak (2022) with significant 2023 decline
- ✅ Recovery trend is positive overall
- ✅ Better understanding of seasonal patterns
- ✅ Proven recovery strategies from India and Brazil

**Areas Requiring Attention:**
- ⚠️ Data inconsistencies in recovery reporting
- ⚠️ Continued vigilance needed in heavily affected regions
- ⚠️ Seasonal preparation for Q1 transmission peaks

> 🎯 **Conclusion**: The data shows we've moved past the peak, but vigilance remains essential. Understanding these patterns helps us prepare better for any future health emergencies.

## ✨ Features

### Visualization Strategy

- 📈 **Time-Series Analysis**: Track pandemic progression over time
- 🗺️ **Geographic Distribution**: Interactive maps and regional breakdowns
- 📊 **Comparative Analysis**: Compare confirmed, recovered, and death cases
- 🎯 **KPIs**: Key Performance Indicators for critical metrics
- 🔄 **Real-Time Updates**: Direct connection to live data sources

### Data Quality Assurance

- ✓ Consistency validation across all queries
- ✓ Data type integrity for calculations
- ✓ Relationship validation in data model
- ✓ Performance optimization


### Advanced Features

- **Custom Measures**: Create DAX calculations for specific metrics
- **Drill-Through**: Navigate from summary to detailed views
- **Bookmarks**: Save specific view states
- **Parameters**: Dynamic filtering and what-if analysis

## 📐 Data Model

### Fact Table: Consolidation

| Column | Type | Description |
|--------|------|-------------|
| Date | Date | Observation date |
| Cases | Integer | Number of cases |
| Status | Text | Confirmed/Recovered/Deaths |
| Location | Text | Geographic identifier |

### Dimension Table: Location

| Column | Type | Description |
|--------|------|-------------|
| Country/Region | Text | Country name |
| Province/State | Text | State/province (if applicable) |
| Latitude | Decimal | Geographic coordinate |
| Longitude | Decimal | Geographic coordinate |

### Query List

1. **Confirmed Query**: Confirmed COVID-19 cases with full transformation pipeline
2. **Recovered Query**: Recovery statistics with standardized transformations
3. **Deaths Query**: Mortality data with consistent structure
4. **Location Query**: Geographic dimension table for spatial analysis
5. **Consolidation Query**: Unified fact table combining all status categories

## 📊 Sample Visualizations
<img width="1366" height="768" alt="DASHBOARD" src="https://github.com/user-attachments/assets/5180594c-245f-44cd-a483-d302a81c2d18" />

### Dashboard Components

- 🌍 Global heat map of confirmed cases
- 📈 Line chart showing daily trends
- 📊 Bar chart of top affected countries
- 🔢 KPI cards for total cases, recoveries, deaths
- 📅 Time intelligence (YoY, MoM comparisons)


## 📝 Technical Documentation

## 🔍 Data Quality Metrics

- **Data Freshness**: Updated daily from Johns Hopkins CSSE
- **Geographic Coverage**: 190+ countries and territories
- **Historical Depth**: Complete data since January 2020
- **Update Frequency**: Daily automated refresh available

## 📈 Performance Optimization

- Removed unnecessary columns (40% size reduction)
- Implemented proper data types
- Optimized relationships for query performance
- Enabled query folding where possible


## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- **Johns Hopkins CSSE** for maintaining the COVID-19 data repository
- **Microsoft Power BI** team for excellent documentation

## 📧 Contact

For questions, suggestions, or collaboration:

- Open an issue in this repository
- Submit a pull request
- **Email**: Gbenovieobhoo@gmail.com
- **LinkedIn**: [Gbenovie Obhoo](https://linkedin.com/in/gbenovie-obhoo)

---

**Author**: Gbenovie Obhoo | Data Analyst  
**Project Status**: Active Development  
**Power BI Version**: Compatible with Power BI Desktop (latest)

