# 🚌 Istanbul Public Transportation Data Analysis (GTFS)

This project provides a comprehensive data visualization and analysis of Istanbul's public transportation network using **GTFS (General Transit Feed Specification)** data.

**DISCLAIMER**
This project is a personal analysis using data from the IMM (Istanbul Metropolitan Municipality) Open Data Portal; it is intended for educational purposes and does not represent official institutional results or policies.

## 📊 Project Overview
The goal of this analysis is to understand the trip frequencies, route efficiencies, and service distributions across Istanbul. By leveraging Python's data science libraries, we visualize how the city moves.

## 🚀 Key Features
- **Hourly Frequency Analysis:** Visualizing peak hours and trip density throughout the day.
- **Route Popularity:** Identifying the most frequent bus and transit lines in the city.
- **Duration Insights:** Mapping the longest transit routes by average trip duration.
- **Service Distribution:** Breakdown of weekday vs. weekend service levels.

## 🛠️ Tech Stack
- **Python** (Core Analysis)
- **Pandas** (Data Manipulation)
- **Matplotlib & Seaborn** (Data Visualization)
- **GTFS Data** (Static Transit Data)

## 📸 Visualizations
*The dashboard includes:*
1. **Hourly Trip Density** (Line Chart)
2. **Top 15 Frequent Routes** (Bar Chart)
3. **Longest Transit Lines** (Horizontal Bar Chart)
4. **Service Type Distribution** (Pie Chart)
5. **Top 10 Trip Destinations** (Horizontal Bar Chart)

## 📂 Project Structure
├── raw_data/                # Original, unprocessed datasets (.csv)
├── preprocessed_data/       # Cleaned and standardized datasets ready for analysis
├── results/                 # Analysis outputs, visualizations (.png), and result notebooks
├── gtfs_data_cleaning.ipynb # Main script for cleaning and transforming the 4 primary datasets
├── requirements.txt         # Project dependencies (pandas, matplotlib, etc.)
└── README.md                # Project documentation
  

**LOGS and SUMMARIES**

| trips.csv |
String Normalization (`strip()`) <br> • Duplicate Removal (`trip_id`) <br> • Feature Selection | 
Space characters removed, 133,121 records cleaned of duplicates. Unused accessibility fields excluded |
-----
* **String Normalisation:** Applied `strip()` to remove leading/trailing spaces in categorical data.
* **Deduplication:** Performed strict checks on `trip_id` to ensure each trip is unique.
* **Exclusion:** Accessibility-related fields were removed as they were out of scope for operational analysis.
* Peak direction and directional flow analysis.
* Establishing a clear Route → Trip relationship.


| stop_times.csv |
• Missing Value Handling <br> • Data Type Conversion <br> • Duplicate Cleaning | 30 incomplete rows deleted (8047 → 8017). Conformed to GTFS standards (int conversion). |
-----
* **Missing Data Management:** Rows with missing critical fields (`agency_id`, `route_short_name`, etc.) were removed to ensure data integrity.
* **GTFS Standardization:** `agency_id` and `route_type` were converted to `int` format to comply with global transit standards.
* **Deduplication:** Cleaned records based on `route_code` to prevent redundant entries.
* **Handling Nulls:** The `route_desc` column was mostly empty; these were filled with an empty string (`""`) to prevent errors in future data processing steps.


| **routes.csv** |
• Encoding & Whitespace Fix <br> • Feature Selection <br> • ID Identification | Text inconsistencies resolved. Analytically irrelevant Visual/URL fields excluded. |
-----
* **Identifier Management:** `route_id` was treated as a primary identifier field for relational integrity.
* **Text Normalization:** Fixed encoding-related inconsistencies and whitespace issues in text fields to ensure searchability.
* **Data Pruning:** Visual assets (logos/colors) and URL fields were excluded as they provided no analytical value for the operational scope.
