# Book Market Intelligence Dashboard

**A data-driven market analysis for online book retail strategy** — addressing competitive intelligence, pricing optimisation, and inventory gaps.

## Business Problem

An online book retailer faced strategic uncertainty:
- *Which genres drive the market?* 
- *How does pricing vary by category, and what's the opportunity?*
- *Where are demand gaps — high-rated books with insufficient stock?*
- *How do ratings and pricing correlate across genres?*

This project delivers actionable market intelligence to inform **catalogue strategy, pricing decisions, and inventory procurement**.

---

## Project Overview

**Market Intelligence Workflow:**
1. **Data Collection** – Scrape 1,000 books across 30+ genres from a live marketplace using BeautifulSoup
2. **Data Transformation** – Clean encoding errors, standardise formats, and engineer demand-analysis metrics using pandas
3. **Interactive Dashboard** – Visualise market dynamics with genre, demand category, and price-range filters in Excel
4. **Strategic Insights** – Identify demand gaps, pricing patterns, and competitive positioning opportunities

## Dataset

- **Volume**: 1,000 books across 30+ genres
- **Scope**: Title, genre, price (£), rating (1–5), stock count, availability
- **Source**: [books.toscrape.com](https://books.toscrape.com) (representative market proxy)
- **Collection Period**: June 2026

## Strategic Framework: Demand Analysis Matrix

Books are categorised across a **rating × stock** matrix to identify strategic opportunities:

| Rating | Stock | Strategic Category | Business Action |
|--------|-------|-------------------|-----------------|
| 4–5 ⭐ | 0–10 | **Demand Gap** | Replenish inventory — unmet demand for high-quality titles |
| 4–5 ⭐ | 11–22 | **Well Supplied** | Maintain current strategy — optimal stock-rating balance |
| 1–3 ⭐ | 11–22 | **Review Pricing** | Consider discounts or delisting — overstock of low-rated titles |
| 1–3 ⭐ | 0–10 | **Low Priority** | Discontinue — minimal demand and low quality signals |

### Distribution (1,000 books analysed)
- **Demand Gap**: 217 books (21.7%) — High-value inventory opportunities
- **Well Supplied**: 158 books (15.8%) — Balanced portfolio
- **Review Pricing**: 260 books (26.0%) — Pricing/positioning needed
- **Low Priority**: 365 books (36.5%) — Low strategic value

---

## Key Market Insights

### 1. Genre Concentration
- **Top 7 genres account for 29% of the catalogue**, indicating market concentration
- *Philosophy* and *Mystery* are the largest categories (41 books each)
- *Womens Fiction* is the only genre with 44 titles — emerging category

### 2. Pricing Patterns
- **Average price**: £30.50 across all genres
- **Price range**: £1–£60 (wide variation)
- **Music has the widest price range (£58.54)** — premium positioning opportunity
- **Young Adult has the narrowest range (£46.66)** — competitive pricing pressure

### 3. Rating-Price Correlation
- **Average rating**: 3.77/5 (relatively balanced distribution)
- **No strong correlation between price and rating** — high price ≠ higher quality signals
- *Implication*: Price transparency and customer reviews matter more than absolute price

### 4. Demand Gaps (Strategic Priority)
- 217 high-rated (4–5⭐) books with low stock (0–10 units)
- **Revenue opportunity**: Restocking these titles captures unmet demand from satisfied customers
- **Lower risk**: Quality already validated by ratings

---

## Marketing Intelligence Dashboard

![Book Market Intelligence Dashboard](https://github.com/BenaData/book-market-intelligence-analysis/blob/main/Dashboard.png)

**Interactive Features:**
- **Genre Filter**: Drill down by category (Womens Fiction, Music, Romance, Academic, etc.)
- **Demand Category Filter**: Focus on specific strategic priorities
- **KPIs at a Glance**: Total books, avg stock, avg price, avg rating across filters
- **Visualisations**:
  - Catalogue distribution by genre (pie chart)
  - Demand category breakdown (donut chart)
  - Pricing pattern by genre (horizontal bar chart)
  - Price range variance (dual-axis comparison)


## How to Use This Intelligence

### For Catalogue Strategy
1. Filter by **Demand Gap** category to identify high-rated, under-stocked titles
2. Cross-reference by genre to understand which categories have unfilled demand
3. **Action**: Prioritise procurement of demand-gap titles to capture unmet customer demand

### For Pricing Optimisation
1. Examine **Price Range by Genre** to identify competitive pricing windows
2. Compare average prices within your target genres
3. **Action**: Position pricing within competitive range while maintaining margin

### For Inventory Management
1. Use **Demand Category Distribution** to rebalance stock allocation
2. Reduce stock of "Review Pricing" titles (low-rated overstock)
3. Increase stock of "Demand Gap" titles (validated quality, unmet demand)
4. **Action**: Shift inventory investment from low-priority to high-opportunity categories

### For Market Entry
1. Identify underrepresented genres (low catalogue count but growing categories like Womens Fiction)
2. Use pricing and rating data to position competitively
3. **Action**: Develop targeted buying strategy for emerging or high-margin categories

## Strategic Recommendations

### 1. **Seize Demand Gaps** (Quick Win)
- **217 high-rated books with stock < 10 units** represent immediate revenue opportunity
- Restocking validated titles minimises risk; customer ratings signal quality
- **Recommendation**: Fast-track procurement of top 50 demand-gap titles for immediate inventory boost

### 2. **Review Overstock Positioning** (Margin Protection)
- 260 low-rated (1–3⭐) books with healthy stock indicate pricing or positioning issues
- **Recommendation**: Either (a) discount to accelerate sell-through, or (b) delist slow-moving inventory to free capital for demand-gap titles

### 3. **Diversify Genre Strategy** (Growth)
- Top 7 genres hold 29% of catalogue; opportunity to build depth in high-growth categories
- Womens Fiction is emerging (44 titles); Young Adult shows tight pricing (competitive pressure)
- **Recommendation**: Allocate 15–20% of new budget to underrepresented but trending genres

### 4. **Price Transparently** (Competitive Advantage)
- No strong rating-price correlation suggests customers prioritise reviews over absolute price
- Wide price ranges within genres (£1–£60) indicate pricing flexibility
- **Recommendation**: Develop transparent pricing strategy; emphasise customer reviews in marketing

## Technologies Used

**Data Collection**: BeautifulSoup, requests  
**Data Processing**: pandas, numpy  
**Data Storage**: Excel (openpyxl), .xlsm (macro-enabled)  
**Visualisation**: Excel pivot tables, charts, slicers  
**Development Environment**: Jupyter Notebook, Python 3

## Files Explained

| File | Purpose |
|------|---------|
| `Book_Market_Scraper.ipynb` | Collects 1,000 book records from live marketplace via web scraping |
| `book_market_data_cleaning.ipynb` | Transforms raw data into analysis-ready format; engineers demand analysis categories |
| `book_market_data.xlsx` | Raw scraped dataset (before cleaning) |
| `book_market_clean_data.xlsx` | Production-ready dataset with strategic categories |
| `book_market_intelligence_project.xlsm` | **Executive dashboard** — Interactive filters, charts, KPIs for decision-making |

## How to Reproduce & Extend

### Step 1: Set Up Environment
```bash
git clone https://github.com/YOUR-USERNAME/book-market-analysis.git
cd book-market-analysis
pip install -r requirements.txt
```

### Step 2: Run Data Pipeline
1. **Scraping**: Open `01_Data_Collection/Book_Market_Scraper.ipynb`
   - Scrapes 50 pages × 20 books/page = 1,000 records
   - Output: `book_market_data.xlsx`

2. **Cleaning & Feature Engineering**: Open `02_Data_Transformation/book_market_data_cleaning.ipynb`
   - Fixes encoding issues, standardises data types
   - Engineers `Demand Analysis` strategic categories
   - Output: `book_market_clean_data.xlsx`

### Step 3: Analyse & Visualise
- Open `book_market_intelligence_project.xlsm` to explore interactive dashboard
- Use genre and demand category filters to drill down into specific market segments
- Export reports for stakeholder presentations

### Extending the Analysis
```python
import pandas as pd

df = pd.read_excel('book_market_clean_data.xlsx')

# Analyse demand gaps by genre
demand_gap_by_genre = df[df['Demand Analysis'] == 'Demand Gap'].groupby('Genre').size()
print(demand_gap_by_genre.sort_values(ascending=False))

# Calculate pricing elasticity by rating
pricing_by_rating = df.groupby('Rating')['Price (£)'].agg(['mean', 'std', 'count'])
print(pricing_by_rating)
```

---

### Note on Dashboard File
The `.xlsm` file contains:
- Macro-enabled Excel workbook with interactive filters
- Multiple sheets: Dashboard, Data, Demand Analysis, Pricing Analysis
- Pivot tables and slicers for real-time filtering
- Can be opened in Excel, LibreOffice, or Google Sheets (with limited macro support)

## Skills Demonstrated

### Business Intelligence
- **Market analysis** – Competitive positioning, pricing strategy, demand forecasting
- **Strategic framework design** – Demand analysis matrix, risk-return categorisation
- **Data-driven recommendations** – Translating insights into actionable business strategy
- **Stakeholder communication** – Visualising complexity for executive decision-making

### Data Engineering
- **Web scraping** – BeautifulSoup, pagination, handling dynamic content
- **Data cleaning & transformation** – Pandas, encoding issues, derived metrics
- **ETL pipeline** – End-to-end data workflow from source to analysis-ready format

### Analytics & Visualisation
- **Excel dashboards** – Interactive filters, pivot tables, multi-sheet analysis
- **Business intelligence visuals** – Effective chart selection for insights (pie, bar, donut, range charts)
- **KPI design** – Selecting and calculating metrics that drive business decisions

### Tools
- **Python**: requests, BeautifulSoup, pandas, numpy
- **Excel**: Pivot tables, data tables, slicers, interactive charts, macros
- **Data formats**: .xlsx, .xlsm (macro-enabled)

## Real-World Application

This project demonstrates how data engineering and business intelligence combine to solve real problems:

✅ **Problem Identification** → Retailer needs competitive market intelligence  
✅ **Data Strategy** → Determine what to measure and where to collect it  
✅ **Pipeline Automation** → Scale data collection and transformation  
✅ **Strategic Insights** → Identify demand gaps, pricing opportunities, genre strategies  
✅ **Actionable Recommendations** → Drive purchasing, pricing, and cataloguing decisions  

The project moves beyond "data collection" to "market leadership" — using competitive intelligence to outpace rivals.

---

## Notes

- Data is sample/educational (books.toscrape.com is a sandbox site)
- Scraper respects site structure and pagination; adjust `range(1, 51)` to modify page count
- Stock counts are illustrative; real inventory data would require API access
- Dashboard filters are fully interactive — export specific reports for stakeholder presentations

## License

This project is open source and available for educational and portfolio purposes.

---

**Questions or improvements?** Feel free to open an issue or submit a pull request.
