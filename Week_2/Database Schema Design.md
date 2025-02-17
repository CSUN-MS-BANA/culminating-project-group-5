**`Overview`**

`The schema design for a relational database keeping economic, social, public debt, environmental, statistical data for different nations is discussed in this paper. SQLite3 is used for implementation of the database guarantees effective country-level indicator storage, retrieval, and analysis.`

**`Database Schema Design`**

`The database consists of seven primary tables:`

1. **`Countries`**  
2. **`Series`**  
3. **`Economic_Indicators`**  
4. **`Social_Indicators`**  
5. **`Public_Debt_Indicators`**  
6. **`Environmental_Indicators`**  
7. **`Statistical_Indicators`** `(updated)`

`Each table uses primary keys (PK) and foreign keys (FK) to maintain relationships and data integrity.`

**`Database Entities and Attributes:`**

**`Countries Table`**

`The Countries table stores information about different countries`

| `Attribute` | `Type` | `Purpose` |
| :---- | :---- | :---- |
| `country_code (PK)` | `TEXT` | `Unique ISO country code` |
| `name` | `TEXT` | `Full country name` |
| `region` | `TEXT` | `Geographical region` |
| `Income_level` | `TEXT` | `Classification by income` |

**`Series Table`** 

| `Attribute` | `Type` | `Purpose` |
| :---- | :---- | :---- |
| `series_code`  | `TEXT` | `Unique code for the indicator` |
| `series_id (PK)` | `INTEGER` | `Unique identifier for each indicator` |
| `series_name` | `TEXT` | `Full name of the indicator` |
| `category` | `TEXT` | `Type of indicator` |

**`Economic Indicators Table`**

| `Attribute` | `Type` | `Purpose` |
| :---- | :---- | :---- |
| `country_code (FK)` | `TEXT` | `Links to Countries table` |
| `series_id (FK)` | `TEXT` | `Unique code for statistical indicator` |
| `year (PK)` | `INTEGER` | `The year of data` |
| `gdp` | `REAL` | `Gross Domestic Product (USD)` |
| `gdp_growth_rate` | `REAL` | `Annual GDP growth percentage` |
| `inflation_rate` | `REAL` | `Annual price change percentage` |
| `consumer_price_index (CPI)` | `REAL` | `Inflation trends over time` |
| `trade_balance` | `REAL` | `Exports minus imports` |
| `fdi` | `REAL` | `Foreign direct investment inflow` |
| `government_spending` | `REAL` | `Total government spending` |

**`Social Indicators Table`**

| `Attribute` | `Type` | `Purpose` |
| :---- | :---- | :---- |
| `country_code (FK)` | `TEXT` | `Links to Countries table` |
| `series_id (FK)` | `TEXT` | `Unique code for statistical indicator` |
| `year (PK)` | `INTEGER` | `The year of data` |
| `life_expectancy` | `REAL` | `Average lifespan in years` |
| `literacy_rate` | `REAL` | `Percentage of literate adults` |
| `poverty_rate` | `REAL` | `Population below the poverty line` |
| `unemployment_rate` | `REAL` | `Percentage of jobless labor force` |
| `labor_force_participation` | `REAL` | `Percentage of working-age population in labor force` |
| `access_to_clean_water` | `REAL` | `Population with safe water access` |

**`Public Debt Indicators Table`**

| `Attribute` | `Type` | `Purpose` |
| :---- | :---- | :---- |
| `country_code (FK)` | `TEXT` | `Links to Countries table` |
| `series_id (FK)` | `TEXT` | `Unique code for statistical indicator` |
| `year (PK)` | `INTEGER` | `The year of data` |
| `quarter (PK)` | `TEXT` | `The fiscal quarter` |
| `total_gov_debt` | `REAL` | `Government debt in USD` |
| `debt_to_gdp_ratio` | `REAL` | `Debt as % of GDP` |
| `interest_payments` | `REAL` | `Debt interest paid.` |
| `external_debt_stocks` | `REAL` | `Total external debt.` |

**`Environmental Indicators Table`**

| `Attribute` | `Type` | `Purpose` |
| :---- | :---- | :---- |
| `country_code (FK)` | `TEXT` | `Links to Countries table` |
| `series_id (FK)` | `TEXT` | `Unique code for statistical indicator` |
| `year (PK)` | `INTEGER` | `The year of data` |
| `co2_emissions` | `REAL` | `CO₂ emissions per capita` |
| `renewable_energy_consumption` | `REAL` | `Renewable energy as % of total` |
| `access_to_electricity` | `REAL` | `Population with electricity` |
| `forest_area` | `REAL` | `Forested land percentage` |

**`Statistical Indicators Table`** 

| `Attribute` | `Type` | `Purpose` |
| :---- | :---- | :---- |
| `country_code (FK)` | `TEXT` | `Links to Countries table` |
| `series_id (FK)` | `TEXT` | `Unique code for statistical indicator` |
| `year (PK)` | `INTEGER` | `The year of data` |
| `money_supply_m1` | `REAL` | `M1- Narrow money supply (cash + checking deposits)` |
| `money_supply_m2` | `REAL` | `M2- Broad money supply (M1 + savings deposits, time deposits)` |
| `money_supply_m3` | `REAL` | `M3- Total money supply (M2 + large deposits, institutional funds)` |
| `exchange_rate` | `REAL` | `Exchange rate vs. USD` |
| `interest_rate` | `REAL` | `Official interest rate set by the central bank` |
| `inflation_rate` | `REAL` | `Annual inflation rate based on the Consumer Price Index (CPI)` |
| `gdp_deflator` | `REAL` | `Measures inflation by comparing current and base-year GDP` |
| `stock_market_index` | `REAL` | `Measures performance of a country’s stock market` |
| `credit_to_private_sector` | `REAL` | `Bank lending to the private sector as % of GDP` |
| `foreign_exchange_reserves` | `REAL` | `Central bank foreign currency holdings` |
| `balance_of_payments` | `REAL` | `Net inflow/outflow of foreign currency` |

