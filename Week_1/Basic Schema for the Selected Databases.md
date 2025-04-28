`Basic Schema for the Selected Databases`

`After analyzing the data, here’s a basic schema for each of the three databases. This will serve as the foundation for developing your financial predictive model.`

---

`1. Doing Business Dataset`

`This dataset appears to contain information about business regulations and economic conditions across countries over time.`

`Table Name: doing_business`

| `Column Name` | `Data Type` | `Description` |
| :---- | :---- | :---- |
| `Country Name` | `Text` | `Full name of the country` |
| `Country Code` | `Text` | `Three-letter country code` |
| `Series Name` | `Text` | `Description of the economic/business indicator` |
| `Series Code`  | `Text` | `Unique code for the indicator` |
| `Year` | `Integer` | `Year of the recorded data` |
| `Value` | `Float` | `Value of the indicator for that year` |
|  |  |  |

`2. World Development Indicators Dataset`

`This dataset provides key economic, financial, and social indicators for different countries over time.`

`Table Name: world_development_indicators`

| `Column Name` | `Data Type` | `Description` |
| :---- | :---- | ----- |
| `Country Name`  | `TEXT` | `Full name of the country` |
| `Country Code` | `TEXT` | `Three-letter country code` |
| `Series Name` | `TEXT` | `Description of the development indicator` |
| `Series Code`  | `TEXT` | `Unique code for the indicator` |
| `Year` | `INTEGER`  | `Year of the recorded data` |
| `Value`  | `FLOAT` | `Value of the indicator for that year` |

---

`3.Global Financial Development Database` 

`The Global Financial Development (GFD) Database is a World Bank dataset that provides comprehensive measures of financial system characteristics and development across different countries. It is used for analyzing trends in financial access, stability, efficiency, and depth.`

| `Column Name`  | `Data Type`  | `Description`  |
| :---- | :---- | :---- |
| `Country Name`  | `Object` | `Name of country`  |
| `County code`  | `Object` | `ISO code of the country` |
| `Series name`  | `Object` | `Indicator name`   |
| `Series code`  | `Object` | `Unique code for the indicator`  |
| `Yearly columns (2007-2021)` | `Object`  | `Financial values per year`  |

`Entity-Relationship (ER) Model Structure`

`Overview`

`This document outlines the ER Model structure for integrating the Global Financial Development Database, Doing Business Database, and World Development Indicators into a relational database. The structure ensures efficiency, eliminates redundancy, and supports robust queries.`

`Entities and Relationships`

`1. Country`

`Primary Key (PK): Country Code`

`Attributes:`

`Country Code (PK) (VARCHAR, Unique)`

`Country Name (VARCHAR)`

`2. Indicator`

`Primary Key (PK): Series Code`

`Attributes:`

`Series Code (PK) (VARCHAR, Unique)`

`Series Name (VARCHAR)`

`3. Financial Data`

`Composite Primary Key (PK): Country Code, Series Code, Year`

`Foreign Keys (FK): Country Code → Country, Series Code → Indicator`

`Attributes:`

`Country Code (FK) (VARCHAR)`

`Series Code (FK) (VARCHAR)`

`Year (INTEGER)`

`Value (FLOAT)`

`Relationships`

`One-to-Many Relationship: A Country can have multiple financial indicators recorded over time.`

`One-to-Many Relationship: An Indicator is measured across multiple countries and years.`

`Financial Data serves as a bridge table connecting Country and Indicator with time-series values.`

