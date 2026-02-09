# Cryptocurrency Dashboard

**Live Cryptocurrency Data Analysis Dashboard Using Power BI**

---

## 📋 Table of Contents
- [Project Overview](#project-overview)
- [Data Source](#data-source)
- [Data Cleaning](#data-cleaning)
- [Analysis Performed](#analysis-performed)
- [Key Performance Indicators](#key-performance-indicators)
- [Visualizations](#visualizations)
- [Dashboard Insights](#dashboard-insights)
- [Project Structure](#project-structure)
- [How to Use](#how-to-use)
- [Technologies Used](#technologies-used)
- [License](#license)

---

## Project Overview

This project delivers a comprehensive cryptocurrency market analysis dashboard built with **Power BI**. It provides real-time insights into the cryptocurrency market landscape, presenting a snapshot of market conditions through interactive visualizations, dynamic filtering, and detailed comparative analysis across multiple crypto assets.

The dashboard consolidates cryptocurrency data from live sources and transforms it into actionable insights for market monitoring and trend analysis.

---

## Data Source

**Source Type**: Live Data  
**API Provider**: CoinGecko API  
**Data Frequency**: Real-time and near real-time updates  
**Data Coverage**: Multiple cryptocurrencies including wrapped and staked assets  

**Data Points Collected**:
- Current cryptocurrency prices
- Market capitalization data
- All-time high and all-time low prices
- 24-hour price changes
- 7-day price changes
- Historical pricing by year
- Asset metadata and classification

---

## Data Cleaning

**Tool**: Power BI Power Query Editor

**Cleaning & Transformation Steps**:
- **Data Extraction**: Importing raw data from CoinGecko API and other source files
- **Data Validation**: Removing invalid or incomplete records
- **Duplicate Removal**: Eliminating duplicate entries across data sources
- **Missing Value Handling**: Managing null or missing cryptocurrency data points
- **Column Transformation**: Formatting and standardizing data types
- **Normalization**: Standardizing units, percentages, and numeric formats
- **Data Type Conversion**: Converting text to numeric, date formatting
- **Aggregation Logic**: Preparing data for KPI calculations
- **Combining Sources**: Merging data from multiple cryptocurrency sources for comprehensive coverage

---

## Analysis Performed

### 1. **Key Performance Indicators (KPIs)**
The dashboard tracks five primary KPIs with large, prominent metric cards displaying real-time data:

- **Coin Count**: Total number of cryptocurrencies being tracked in the analysis
- **Market Cap**: Overall market capitalization across all monitored assets
- **Current Price**: Real-time price data for selected cryptocurrencies
- **Price Change Percentage 24hr**: Percentage price movement over the last 24 hours
- **Price Change Percentage 7d in Currency**: Percentage price movement over the last 7 days

### 2. **Time-Series Analysis**
- **All Time High by Year**: Historical tracking of peak prices organized by year
- Visualization of long-term price fluctuations and trends
- Identification of historical performance patterns for each cryptocurrency
- Year-over-year comparative analysis of peak prices

### 3. **Ranking & Comparative Analysis**
- **Wrapped Asset Comparison**: Analysis of wrapped tokens (e.g., Wrapped Bitcoin)
- **Staked Asset Comparison**: Comparative metrics for staked cryptocurrencies (e.g., Lido Staked Ether)
- **All-Time Highs & Lows**: Detailed tables comparing total counts and aggregate values
- **Performance Ranking**: Ranking cryptocurrencies by various metrics

### 4. **Data Aggregation**
- Consolidated data from multiple cryptocurrency exchanges and data providers
- Unified data structure for comparative analysis across different asset types
- Comprehensive market overview combining multiple data sources

---

## Key Performance Indicators

| KPI | Metric | Purpose |
|-----|--------|---------|
| Coin Count | Total Assets | Track number of cryptocurrencies monitored |
| Market Cap | Total Capitalization | Gauge overall market size and value |
| Current Price | Real-time Pricing | Monitor current rates for selected coins |
| Price Change 24hr | Daily Change % | Identify short-term market movements |
| Price Change 7d | Weekly Change % | Analyze medium-term price trends |

---

## Visualizations

The dashboard employs multiple visualization techniques for comprehensive market analysis:

### 1. **Metric Cards**
- Large, prominently displayed KPI cards
- Real-time or near real-time data updates
- Quick assessment of market state

### 2. **Line Charts**
- **All Time High by Year**: Track historical peak prices
- Time-series representation of price evolution
- Trend identification and historical pattern analysis
- Visual comparison of performance across different timeframes

### 3. **Data Tables**
- **Wrapped Crypto Assets**: Detailed comparison of wrapped tokens
- **Staked Assets**: Analysis of staked cryptocurrency performance
- All-time lows and highs displayed in tabular format
- Sortable and filterable data presentations

### 4. **Interactive Filters**
Dropdown menus for dynamic data exploration:
- **Filter by Name**: Select specific cryptocurrencies for analysis
- **Filter by All Time High by Year**: Focus on specific time periods
- Real-time filtering without page refresh
- Multi-select capability for comparative analysis

### 5. **Comparative Rankings**
- Side-by-side comparison of different crypto assets
- Performance metric rankings
- Visual separation of wrapped, staked, and standard crypto assets

---

## Dashboard Insights

**Market Overview**: The dashboard provides a snapshot of the cryptocurrency market at any point in time, aggregating data from multiple sources for a comprehensive view.

**Price Movement Analysis**: By tracking 24-hour and 7-day changes, users can quickly identify volatile assets and trending cryptocurrencies.

**Historical Performance**: Time-series visualization of all-time highs by year helps identify long-term patterns and historical volatility.

**Asset Classification**: Separate analysis of wrapped and staked assets provides insights into derivative cryptocurrency products and DeFi participation.

**Interactive Exploration**: Dynamic filtering allows users to deep-dive into specific cryptocurrencies or time periods without switching views or dashboards.

---

## Project Structure

```
Cryptocurrency/
├── Analysis/
│   └── Crypto Currency.pbix              # Main Power BI dashboard
├── Data/
│   └── httpsapi.coingecko.comapiv3coinsmar.txt    # Raw API data
├── Description/
│   └── Cryptocurrency.txt                # Detailed analysis documentation
├── Result/
│   ├── Cryptocurrency Dashboard.png      # Dashboard visualization 1
│   └── Cryptocurrency Overview.png       # Dashboard visualization 2
├── LICENSE                               # Project license
├── README.md                             # This file
└── .git/                                 # Version control
```

---

## How to Use

1. **Open Power BI Desktop**
   - Ensure Power BI Desktop is installed on your system

2. **Load the Dashboard**
   - Navigate to: `Analysis/Crypto Currency.pbix`
   - Open the file in Power BI Desktop

3. **Refresh Data**
   - Click the "Refresh" button to pull latest cryptocurrency data from the API
   - Data will update with current market information

4. **Use Dynamic Filters**
   - Use the "Name" dropdown to select specific cryptocurrencies
   - Filter by "All Time High by Year" to focus on specific periods
   - Interact with the dashboard to explore different data combinations

5. **Analyze Trends**
   - Examine line charts for historical price movements
   - Review KPI cards for current market state
   - Compare wrapped and staked assets using data tables
   - Identify patterns and market opportunities

### Prerequisites
- **Power BI Desktop** (latest version recommended)
- **Internet Connection** (for live API data refresh)
- **CoinGecko API Access** (for data updates)

---

## Technologies Used

| Technology | Purpose |
|-----------|---------|
| **Power BI** | Dashboard creation, visualization, and analysis |
| **Power Query Editor** | Data extraction, transformation, and cleaning |
| **CoinGecko API** | Real-time cryptocurrency market data source |
| **DAX** | Advanced calculations, KPI computations, and metrics |
| **M Query Language** | Data transformation logic in Power Query |

---

## Key Features

✅ Real-time data integration from CoinGecko API  
✅ Interactive filtering by cryptocurrency name and time period  
✅ Comprehensive KPI tracking (5 primary metrics)  
✅ Time-series analysis with historical price visualization  
✅ Comparative analysis of wrapped and staked assets  
✅ Dynamic dashboard with refresh capabilities  
✅ Multi-source data aggregation and consolidation  
✅ Professional visualizations and metric cards  

---

## License

This project is licensed under the terms specified in the [LICENSE](LICENSE) file.

---

## Contact & Support

For questions, suggestions, or issues related to this project, please refer to the project documentation or contact the maintainers.

---

