# Montgomery Opportunity Scoring Tool

A spatial analysis application designed to identify business opportunities and market attractiveness in Montgomery, Alabama. This tool integrates demographic data from the U.S. Census Bureau with local business license data to provide a comprehensive view of the economic landscape.

## 🚀 Key Features

- **Opportunity Scoring**: Identifies "market gaps" where high customer potential meets low business density.
- **Attractiveness Scoring**: Evaluates the overall appeal of a census tract based on existing business presence and demographic strength.
- **Interactive Spatial Visualization**: Uses Leaflet.js to map data at the Census Tract level.
- **Real-time Data Integration**: Fetches live data from:
  - **U.S. Census ACS 5-Year Estimates** (Income, Population, Education).
  - **Montgomery GIS Business Licenses** (Spatial business density).
  - **TIGER/Line Shapefiles** (Geographic boundaries).

## 📊 Methodology

The tool uses normalized data to calculate several key metrics for each census tract:

### 1. Customer Potential (Demand Score)
Calculated as a weighted average of normalized Population and Median Household Income.
`Score = (0.5 * Normalized Population) + (0.5 * Normalized Income)`

### 2. Opportunity Score (Competition Gap)
Highlights areas that are underserved. It scales the Customer Potential by the inverse of Business Density.
`Score = Customer Potential * (1 - Normalized Business Density)`
*A high score indicates a "market gap" where demand is high but competition is low.*

### 3. Attractiveness Score
A metric for general market health, favoring areas with established business clusters and strong demographics.
`Score = (0.6 * Normalized Business Density) + (0.4 * Customer Potential)`
*A high score indicates a "proven" market with strong existing infrastructure and customer base.*

## 🛠️ Tech Stack

- **Frontend**: React (via CDN), Tailwind CSS
- **Mapping**: Leaflet.js
- **Spatial Analysis**: Turf.js
- **Data**: U.S. Census API, Montgomery GIS REST Services

## 🚦 Getting Started

### Prerequisites
- A modern web browser.
- (Optional) A local web server for development.

### Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/montgomery-opportunity-tool.git
   ```
2. Open `index.html` in your browser.

Alternatively, if you have Node.js installed, you can run:
```bash
npm start
```

## 📄 License
This project is open-source and available under the MIT License.
