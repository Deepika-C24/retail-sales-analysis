# Sales Data Analysis & Reporting System

## Overview

This project analyzes retail sales data from January 2024 to provide business insights including:
- Discount effectiveness and impact analysis
- Sales trends by weekday
- Return cost calculations
- Automated supplier ordering
- Product performance identification
- Price-discount correlation analysis

The system processes over 2,000 transactions across 20 products to generate actionable business intelligence.

## Features

### Data Analysis
- **Discount Impact Analysis**: Compare sales patterns before/after discount policy changes
- **Weekday Business Trends**: Calculate average transactions and revenue by day of week
- **Return Cost Analysis**: Identify most expensive return days based on shelving costs
- **Product Performance**: Track which products are underperforming

### Reporting
- **Automated Supplier Orders**: Generate monthly restock orders based on sales volume
- **Correlation Analysis**: Visualize relationships between product price and discount rates
- **Custom Reports**: Generate formatted text reports for business decision-making

### Data Processing
- CSV file parsing and validation
- Date/time processing and conversion
- Data aggregation and statistical analysis
- File output generation

## Installation

### Prerequisites
- Python 3.7 or higher
- Required libraries: `matplotlib`, `numpy`, `datetime`

### Setup

1. Clone this repository:
```bash
git clone https://github.com/yourusername/sales-data-analysis.git
cd sales-data-analysis
```

2. Install dependencies:
```bash
pip install matplotlib numpy
```

3. Ensure you have the data files:
   - `transactions_Products_January.csv`
   - `transactions_Sales_January.csv`
   - `transactions_Returns_January.csv`

## Usage

### Running the Analysis

```bash
jupyter notebook assignment2.ipynb
```

Or convert to Python script and run:
```bash
jupyter nbconvert --to python assignment2.ipynb
python assignment2.py
```

### Running Individual Functions

```python
from assignment2 import *

# Load data
products_data = read_csv('transactions_Products_January.csv')
sales_data = read_csv('transactions_Sales_January.csv')
returns_data = read_csv('transactions_Returns_January.csv')

# Run specific analysis
discount_impact('2024-01-08', sales_data, products_data)
business_per_weekday(sales_data, returns_data, products_data)
```

## Data Format

### Products Data (`transactions_Products_January.csv`)
```csv
Product_ID,Product_Name,Price,Shelving_Cost
P1,2-in-1 Laptop,1200.00,15.00
P2,Game Laptop,1500.00,15.00
...
```

### Sales Data (`transactions_Sales_January.csv`)
```csv
transaction_id,date,product_id,quantity,discount
1,2024-01-02,P10,1,0.03
2,2024-01-02,P1,2,0.13
...
```

### Returns Data (`transactions_Returns_January.csv`)
```csv
transaction_id,date,product_id,quantity
1,2024-01-03,P10,1
2,2024-01-05,P1,1
...
```

## Analysis Functions

### 1. Discount Impact Analysis
```python
discount_impact(before_change_date, sales_data, products_data)
```
**Purpose**: Analyzes how discount policy changes affect sales

**Output**:
- Percentage of transactions without discounts (before vs after)
- Average discount per product (before vs after policy change)

**Business Value**: Helps evaluate if discount changes increased or decreased revenue

### 2. Business Per Weekday
```python
business_per_weekday(sales_data, returns_data, product_data)
```
**Purpose**: Identifies which days of the week are busiest

**Output**:
- Average number of transactions per weekday
- Average sales amount per weekday

**Business Value**: Enables optimal staff scheduling and inventory planning

### 3. Most Expensive Return Day
```python
most_expensive_return_day(sales_data, returns_data, products_data)
```
**Purpose**: Calculates the highest cost day for returns based on shelving costs

**Output**:
- Date with most expensive returns
- Total shelving cost for that day
- Breakdown of returned products

**Business Value**: Identifies patterns in return behavior for process improvement

### 4. Generate Supplier Orders
```python
generate_order_info(sales_data, returns_data, products_data)
```
**Purpose**: Creates automated monthly restock orders

**Output**:
- Text file: `order_supplier_January.txt`
- Format: `ProductID#ProductName#QuantityToOrder`

**Business Value**: Automates inventory replenishment process

### 5. Unwanted Products Report
```python
unwanted_products(sales_data, returns_data, products_data)
```
**Purpose**: Identifies products with zero or negative net sales

**Output**:
- List of products never sold or with more returns than sales

**Business Value**: Informs decisions about product discontinuation

### 6. Discount-Price Correlation
```python
discount_price_correlation(sales_data, returns_data, products_data)
```
**Purpose**: Analyzes relationship between product price and discount rate

**Output**:
- Scatter plot visualization
- Correlation coefficient

**Business Value**: Guides pricing strategy and discount policies

## Output Examples

### Discount Impact Report
```
Average transaction without discount: 18.45% - 22.13%

Average discount per product:
PID       Product Name  <08-01 - >=08-01
 P1      2-in-1 Laptop  9.25% - 10.50%
 P2        Game Laptop  8.30% - 11.20%
...
```

### Supplier Order File (`order_supplier_January.txt`)
```
P1#2-in-1 Laptop#192
P2#Game Laptop#164
P3#Titan Laptop#148
...
```

### Weekday Business Analysis
```
Average number of transactions per weekday:
Monday:    145
Tuesday:   132
Wednesday: 158
...

Average sales amount per weekday:
Monday:    $15,245.50
Tuesday:   $13,890.25
...
```

## Technical Implementation

### Data Processing Pipeline
1. **Data Ingestion**: Read CSV files using custom parser
2. **Data Validation**: Convert dates, validate formats
3. **Data Transformation**: Aggregate by product, date, weekday
4. **Analysis**: Apply statistical functions
5. **Output Generation**: Create reports and visualizations

### Key Technologies
- **Python**: Core programming language
- **Matplotlib**: Data visualization
- **NumPy**: Numerical computations
- **Datetime**: Date/time processing
- **CSV Processing**: Custom file parsers

## Educational Value

This project demonstrates:
1. **Data Processing**: CSV parsing, data cleaning, validation
2. **Statistical Analysis**: Aggregation, correlation, trend analysis
3. **File I/O**: Reading and writing different file formats
4. **Date/Time Processing**: Working with temporal data
5. **Business Logic**: Implementing real-world business rules
6. **Report Generation**: Creating formatted output for stakeholders

## License

This project is part of an academic assignment and is available for educational purposes.

## Author

*Deepika Chandrashekhar*

•⁠  ⁠GitHub: [@Deepika-C24](https://github.com/Deepika-C24)
•⁠  ⁠LinkedIn: [deepika-chandrashekhar](https://www.linkedin.com/in/deepika-chandrashekhar/)
•⁠  ⁠Email: dchandr1@ualberta.ca
