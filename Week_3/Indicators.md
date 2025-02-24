**`Indicators`**  
**`Overview`**

`This document describes the schema design for a relational database storing economic, social, public debt, environmental, and statistical indicators for various countries. The database is implemented in MySQL, ensuring efficient storage, retrieval, and analysis of country-level indicators.`

**`Database Schema Design`**

`The database consists of seven primary tables:`

1. **`Countries`**  
2. **`Series`**  
3. **`Economic_Indicators`**  
4. **`Social_Indicators`**  
5. **`Public_Debt_Indicators`**  
6. **`Environmental_Indicators`**  
7. **`Statistical_Indicators`**

`Each table uses primary keys (PK) and foreign keys (FK) to maintain relationships and data integrity.`

## `Database Entities and Attributes:`

### `Countries Table`

`The Countries table stores information about different countries`

| `Attribute` | `Type` | `Purpose` |
| :---- | :---- | :---- |
| `country_code (PK)` | `TEXT` | `Unique ISO country code` |
| `name` | `TEXT` | `Full country name` |
| `region` | `TEXT` | `Geographical region` |
| `Income_level` | `TEXT` | `Classification by income` |

### `Series Table` 

| `Attribute` | `Type` | `Purpose` |
| :---- | :---- | :---- |
| `series_code`  | `TEXT` | `Unique code for the indicator` |
| `series_id (PK)` | `INTEGER` | `Unique identifier for each indicator` |
| `series_name` | `TEXT` | `Full name of the indicator` |
| `category` | `TEXT` | `Type of indicator` |

### `Economic Indicators Table`

| `Attribute` | `Series Code` | `Type` | `Purpose` |
| :---- | :---- | :---- | :---- |
| `country_code (FK)` |  | `TEXT` | `Links to Countries table` |
| `series_id (FK)` |  | `TEXT` | `Unique code for statistical indicator` |
| `year (PK)` |  | `INTEGER` | `The year of data` |
| `gdp` | `NY.GDP.MKTP.CD`  | `REAL` | `Gross Domestic Product (USD)` |
| `gdp_growth_rate` | `NY.GDP.MKTP.KD.ZG` | `REAL` | `Annual GDP growth percentage` |
| `inflation_rate` | `FP.CPI.TOTL.ZG`  | `REAL` | `Annual price change percentage` |
| `consumer_price_index (CPI)` | `FP.CPI.TOTL` | `REAL` | `Inflation trends over time` |
| `trade_balance` | `NE.RSB.GNFS.CD` | `REAL` | `Exports minus imports` |
| `fdi` | `BN.KLT.DINV.CD` | `REAL` | `Foreign direct investment net` |
| `government_spending` | `GC.XPN.TOTL.GD.ZS`  | `REAL` | `Total government spending` |
| `Exports of goods and services` | `NE.EXP.GNFS.KD.ZG` |  |  |
| `Imports of goods and services` | `NE.IMP.GNFS.KD.ZG` |  |  |
| `Gross_National_Income (GNI)` | `NY.GNP.MKTP.CD`  |  |  |
| `GDP_per_Capita` | `NY.GDP.PCAP.CD` |  |  |
| `Unemployment_Rate` | `SL.UEM.TOTL.NE.ZS` |  |  |
| `Gross_Capital_Formation` | `NE.GDI.TOTL.CD` |  |  |
| `Tax_Revenue` | `GC.TAX.TOTL.GD.ZS` |  |  |
| `Interest_Rate` | `FR.INR.RINR` |  |  |
| `Labor_Force_Participation_Rate` | `SL.TLF.CACT.NE.ZS` |  |  |
| `Government_Consumption` | `NE.CON.GOVT.ZS` |  |  |
| `Investment_in_R&D` | `GB.XPD.RSDV.GD.ZS` |  |  |
| `Capacity_Utilization` | `NE.GDI.FPRV.ZS` |  |  |
| `Current_Account_Balance` | `BN.CAB.XOKA.CD` |  |  |
| `Import_Volume_Index` | `NE.IMP.GNFS.CD` |  |  |
| `Export_Volume_Index` | `NE.EXP.GNFS.CD` |  |  |
| `Business_Confidence_Index` | `IC.BUS.EASE.XQ` |  |  |
| `Household_Consumption_Expenditure` | `NE.CON.PRVT.ZS` |  |  |
| `Total_Investment_(Gross Fixed Capital Formation)` | `NE.GDI.TOTL.ZS` |  |  |
| `Corporate_Profits` | `NY.GDP.FCST.CD` |  |  |
| `Savings_Rate` | `NY.GNS.ICTR.ZS` |  |  |
| `Private_Sector_Credit` | `FM.AST.PRVT.GD.ZS` |  |  |
| `Lending_Interest_Rate` | `FR.INR.LEND` |  |  |
| `Exchange_Rate_Volatility` | `PA.NUS.FCRF` |  |  |
| `Balance_of_Payments` | `BN.GSR.GNFS.CD` |  |  |
| `Employment-to-Population_Ratio` | `SL.EMP.TOTL.SP.ZS` |  |  |
| `Youth_Unemployment_Rate` | `SL.UEM.1524.ZS` |  |  |
| `Total reserves (includes gold)` | `FI.RES.TOTL.CD` |  |  |
| `External debt stocks` | `DT.DOD.DECT.GN.ZS` |  |  |
| `Core inflation rate` | `FP.CPI.TOTL.ZG` |  |  |

### 

### `Social Indicators Table`

| `Attribute` | `Series Code` | `Type` | `Purpose` |
| :---- | :---- | :---- | :---- |
| `country_code (FK)` |  | `TEXT` | `Links to Countries table` |
| `series_id (FK)` |  | `TEXT` | `Unique code for statistical indicator` |
| `year (PK)` |  | `INTEGER` | `The year of data` |
| `life_expectancy` | `SP.DYN.LE00.IN` | `REAL` | `Average lifespan in years` |
| `literacy_rate` | `SE.ADT.LITR.ZS` | `REAL` | `Percentage of literate adults` |
| `poverty_rate` | `SI.POV.NAHC` | `REAL` | `Population below the poverty line` |
| `unemployment_rate` | `SL.UEM.TOTL.NE.ZS` | `REAL` | `Percentage of jobless labor force` |
| `labor_force_participation` | `SL.TLF.CACT.NE.ZS` | `REAL` | `Percentage of working-age population in labor force` |
| `Population_Growth_Rate` | `SP.POP.GROW` |  |  |
| `Infant_Mortality_Rate` | `SP.DYN.IMRT.IN` |  |  |
| `Maternal_Mortality_Rate` | `SH.STA.MMRT.NE` |  |  |
| `School_Enrollment_Rate` | `SE.PRM.ENRR` |  |  |
| `Gender_Equality_Index` | `SG.GEN.PARL.ZS` |  |  |
| `Crime_Rate` | `VC.IHR.PSRC.P5` |  |  |
| `Income_Inequality (Gini Index)` | `SI.POV.GINI` |  |  |
| `Population_Density` | `EN.POP.DNST` |  |  |
| `Social_Protection_Coverage` | `per_si_allsi.cov_pop_tot` |  |  |
| `Youth_Literacy_Rate` | `SE.ADT.1524.LT.ZS` |  |  |
| `Access_to_Electricity` | `EG.ELC.ACCS.ZS` |  |  |
| `Employment_Rate` | `SL.EMP.TOTL.SP.NE.ZS` |  |  |
| `Migration_Rate` | `SM.POP.NETM` |  |  |
| `Population_Living_in _Slums` | `EN.URB.MCTY.TL.ZS` |  |  |
| `Child_Labor_Rate` | `SL.TLF.0714.ZS` |  |  |
| `Suicide_Rate` | `SH.STA.SUIC.P5` |  |  |
| `Access_to_Internet` | `IT.NET.USER.ZS` |  |  |
| `Political_Stability_Index` | `PV.EST` |  |  |
| `Fertility_Rate` | `SP.DYN.TFRT.IN` |  |  |
| `Old_Age_Dependency_Ratio` | `SP.POP.DPND.OL` |  |  |
| `Healthy_Life_Expectancy` | `SH.DYN.NCOM.ZS` |  |  |
| `Exposure to Air Pollution (PM2.5, µg/m³)` | `SH.STA.AIRP.P5` |  |  |
| `Total Labor Force` | `SL.TLF.TOTL.IN` |  |  |
| `Current Health Expenditure per Capita (USD)` | `SH.XPD.CHEX.PC.CD` |  |  |
| `Primary School Completion Rate (%)` | `SE.PRM.CMPT.ZS` |  |  |

### `Public Debt Indicators Table`

| `Attribute` | `Series Code` | `Type` | `Purpose` |
| :---- | :---- | :---- | :---- |
| `country_code (FK)` |  | `TEXT` | `Links to Countries table` |
| `series_id (FK)` |  | `TEXT` | `Unique code for statistical indicator` |
| `year (PK)` |  | `INTEGER` | `The year of data` |
| `quarter (PK)` |  | `TEXT` | `The fiscal quarter` |
| `total_gov_debt` | `GC.DOD.TOTL.GD.ZS` | `REAL` | `Government debt in USD` |
| `debt_to_gdp_ratio` | `GC.DOD.TOTL.GD.ZS` | `REAL` | `Debt as % of GDP` |
| `external_debt_stocks` | `DT.DOD.DECT.CD` | `REAL` | `Total external debt.` |
| `Debt_Service_Ratio` | `DT.TDS.DPPG.CD` |  |  |
| `Budget_Deficit` | `GC.NLD.TOTL.GD.ZS` |  |  |
| `Debt_Expenditure_as_%_of_GDP` | `GC.XPN.TOTL.GD.ZS` |  |  |
| `Gross PSD, Central Gov., All maturities, All instruments, Domestic creditors, Nominal Value, US$` | `DP.DOD.DECD.CR.CG.CD` |  |  |
| `Gross PSD, Central Gov., All maturities, All instruments, Domestic currency, Nominal Value, US$` | `DP.DOD.DECN.CR.CG.CD` |  |  |
| `Gross PSD, Central Gov., All maturities, All instruments, External creditors, Nominal Value, US$` | `DP.DOD.DECX.CR.CG.CD` |  |  |
| `Gross PSD, Central Gov., All maturities, All instruments, Foreign currency, Nominal Value, US$` | `DP.DOD.DECF.CR.CG.CD` |  |  |
| `Gross PSD, Central Gov., All maturities, All instruments, Nominal Value, US$` | `DP.DOD.DECT.CR.CG.CD` |  |  |
| `Gross PSD, Central Gov., All maturities, Currency and deposits, Nominal Value, US$` | `DP.DOD.DLCD.CR.CG.CD` |  |  |
| `Gross PSD, Central Gov., All maturities, Debt securities, Nominal Value, US$` | `DP.DOD.DLDS.CR.CG.CD` |  |  |
| `Gross PSD, Central Gov., All maturities, Insurance, pensions, and standardized guarantee schemes, Nominal Value, US$` | `DP.DOD.DLIN.CR.CG.CD` |  |  |
| `Gross PSD, Central Gov., All maturities, Loans, Nominal Value, US$` | `DP.DOD.DLLO.CR.CG.CD` |  |  |
| `Gross PSD, Central Gov., All maturities, Other accounts payable, Nominal Value, US$` | `DP.DOD.DLOA.CR.CG.CD` |  |  |
| `Gross PSD, Central Gov., All maturities, Special Drawing Rights, Nominal Value, US$` | `DP.DOD.DLSD.CR.CG.CD` |  |  |
| `Gross PSD, Central Gov., Long-term, All instruments, Nominal Value, US$` | `DP.DOD.DLTC.CR.CG.CD` |  |  |
| `Gross PSD, Central Gov., Long-term, With payment due in more than one year, All instruments, Nominal Value, US$` | `DP.DOD.DLTC.CR.M1.CG.CD` |  |  |
| `Gross PSD, Central Gov., Long-term, With payment due in more than one year, Debt securities, Nominal Value, US$` | `DP.DOD.DLDS.CR.M1.CG.CD` |  |  |
| `Gross PSD, Central Gov., Long-term, With payment due in more than one year, Insurance, pensions, and standardized guarantee schemes, Nominal Value, US$` | `DP.DOD.DLIN.CR.M1.CG.CD` |  |  |
| `Gross PSD, Central Gov., Long-term, With payment due in more than one year, Loans, Nominal Value, US$` | `DP.DOD.DLLO.CR.M1.CG.CD` |  |  |
| `Gross PSD, Central Gov., Long-term, With payment due in more than one year, Other accounts payable, Nominal Value, US$` | `DP.DOD.DLOA.CR.M1.CG.CD` |  |  |
| `Gross PSD, Central Gov., Long-term, With payment due in more than one year, Special Drawing Rights, Nominal Value, US$` | `DP.DOD.DLSD.CR.M1.CG.CD` |  |  |
| `Gross PSD, Central Gov., Short-term, All instruments, Nominal Value, US$` | `DP.DOD.DSTC.CR.CG.CD` |  |  |
| `Gross PSD, Central Gov., Short-term, Currency and deposits, Nominal Value, US$` | `DP.DOD.DSCD.CR.CG.CD` |  |  |
| `Gross PSD, Central Gov., Short-term, Debt securities, Nominal Value, US$` | `DP.DOD.DSDS.CR.CG.CD` |  |  |
| `Gross PSD, Central Gov.-D1, All maturities, Debt securities + loans, Nominal Value, US$` | `DP.DOD.DLD1.CR.CG.CD` |  |  |
| `Gross PSD, Central Gov.-D2, All maturities, D1+ SDRs + currency and deposits, Nominal Value, US$` | `DP.DOD.DLD2.CR.CG.CD` |  |  |
| `Gross PSD, Central Gov.-D2A, All maturities, D1+ currency and deposits, Maastricht debt, US$` | `DP.DOD.DLD2A.CR.CG.CD` |  |  |
| `Gross PSD, Central Gov.-D3, All maturities, D2+other accounts payable, Nominal Value, US$` | `DP.DOD.DLD3.CR.CG.CD` |  |  |
| `Gross PSD, Central Gov.-D4, All maturities, D3+insurance, pensions, and standardized guarantees, Nominal Value, US$` | `DP.DOD.DLD4.CR.CG.CD` |  |  |
| `Gross PSD, General Gov., All maturities, All instruments, Domestic creditors, Nominal Value, US$` | `DP.DOD.DECD.CR.GG.CD` |  |  |
| `Gross PSD, General Gov., All maturities, All instruments, Domestic currency, Nominal Value, US$` | `DP.DOD.DECN.CR.GG.CD` |  |  |
| `Gross PSD, General Gov., All maturities, All instruments, External creditors, Nominal Value, US$` | `DP.DOD.DECX.CR.GG.CD` |  |  |
| `Gross PSD, General Gov., All maturities, All instruments, Foreign currency, Nominal Value, US$` | `DP.DOD.DECF.CR.GG.CD` |  |  |
| `Gross PSD, General Gov., All maturities, All instruments, Nominal Value, US$` | `DP.DOD.DECT.CR.GG.CD` |  |  |
| `Gross PSD, General Gov., All maturities, Currency and deposits, Nominal Value, US$` | `DP.DOD.DLCD.CR.GG.CD` |  |  |
| `Gross PSD, General Gov., All maturities, Debt securities, Nominal Value, US$` | `DP.DOD.DLDS.CR.GG.CD` |  |  |
| `Gross PSD, General Gov., All maturities, Insurance, pensions, and standardized guarantee schemes, Nominal Value, US$` | `DP.DOD.DLIN.CR.GG.CD` |  |  |
| `Gross PSD, General Gov., All maturities, Loans, Nominal Value, US$` | `DP.DOD.DLLO.CR.GG.CD` |  |  |
| `Gross PSD, General Gov., All maturities, Other accounts payable, Nominal Value, US$` | `DP.DOD.DLOA.CR.GG.CD` |  |  |
| `Gross PSD, General Gov., All maturities, Special Drawing Rights, Nominal Value, US$` | `DP.DOD.DLSD.CR.GG.CD` |  |  |
| `Gross PSD, General Gov., Long-term, All instruments, Nominal Value, US$` | `DP.DOD.DLTC.CR.GG.CD` |  |  |
| `Gross PSD, General Gov., Long-term, With payment due in more than one year, All instruments, Nominal Value, US$` | `DP.DOD.DLTC.CR.M1.GG.CD` |  |  |
| `Gross PSD, General Gov., Long-term, With payment due in more than one year, Debt securities, Nominal Value, US$` | `DP.DOD.DLDS.CR.M1.GG.CD` |  |  |
| `Gross PSD, General Gov., Long-term, With payment due in more than one year, Insurance, pensions, and standardized guarantee schemes, Nominal Value, US$` | `DP.DOD.DLIN.CR.M1.GG.CD` |  |  |
| `Gross PSD, General Gov., Long-term, With payment due in more than one year, Loans, Nominal Value, US$` | `DP.DOD.DLLO.CR.M1.GG.CD` |  |  |
| `Gross PSD, General Gov., Long-term, With payment due in more than one year, Other accounts payable, Nominal Value, US$` | `DP.DOD.DLOA.CR.M1.GG.CD` |  |  |
| `Gross PSD, General Gov., Long-term, With payment due in more than one year, Special Drawing Rights, Nominal Value, US$` | `DP.DOD.DLSD.CR.M1.GG.CD` |  |  |

### 

### `Environmental Indicators Table`

| `Attribute` | `Series Code` | `Type` | `Purpose` |
| :---- | :---- | :---- | :---- |
| `country_code (FK)` |  | `TEXT` | `Links to Countries table` |
| `series_id (FK)` |  | `TEXT` | `Unique code for statistical indicator` |
| `year (PK)` |  | `INTEGER` | `The year of data` |
| `renewable_energy_consumption` | `EG.FEC.RNEW.ZS` | `REAL` | `Renewable energy as % of total` |
| `access_to_electricity` | `EG.ELC.ACCS.ZS` | `REAL` | `Population with electricity` |
| `forest_area` | `AG.LND.FRST.ZS` | `REAL` | `Forested land percentage` |
| `Land area (sq. km)` | `AG.LND.TOTL.K2` |  |  |
| `CO₂_Emissions_per_Capita` | `EN.GHG.CO2.PC.CE.AR5` |  |  |
| `Water_Quality_Index` | `ER.H2O.FWST.ZS` |  |  |
| `Pollution_Levels` | `EN.ATM.PM25.MC.M3` |  |  |
| `Carbon_Footprint_Index` | `EN.GHG.CO2.RT.GDP.PP.KD` |  |  |
| `Sustainable_Agriculture_Rate` | `AG.CON.FERT.ZS` |  |  |
| `Fertilizer consumption` | `AG.CON.FERT.ZS` |  |  |
| `Air_Quality_Index` | `EN.ATM.PM25.MC.ZS` |  |  |
| `Ecosystem_Health_Index` | `ER.PTD.TOTL.ZS` |  |  |
| `Deforestation_Rate` | `AG.LND.FRST.ZS` |  |  |
| `Climate_Change_Adaptation_Score` | `EN.CLC.DRSK.XQ` |  |  |
| `Drought_Frequency_Index` | `EN.CLC.MDAT.ZS` |  |  |
| `Water_Scarcity_Index` | `ER.H2O.INTR.PC` |  |  |
| `Energy_Efficiency_Index` | `EG.EGY.PRIM.PP.KD` |  |  |
| `Marine_Pollution_Index` | `ER.MRN.PTMR.ZS` |  |  |
| `Sustainable_Fisheries_Rate` | `EN.FSH.THRD.NO` |  |  |
| `Natural_Disaster_Impact_Score` | `EN.CLC.DRSK.XQ` |  |  |
| `Investment_in_Renewable_Energy` | `EG.ELC.RNEW.ZS` |  |  |
| `Natural_Resource_Depletion` | `NY.GDP.TOTL.RT.ZS` |  |  |
| `Industrial_Emissions _Reduction_Rate` | `EN.GHG.ALL.MT.CE.AR5` |  |  |
| `Sustainable_Energy_Sector_Index` | `EG.FEC.RNEW.ZS` |  |  |
| `Greenhouse_Gas_Reduction_Rate` | `EN.GHG.ALL.LU.MT.CE.AR5` |  |  |
| `Access to clean fuels and technologies for cooking` | `EG.CFT.ACCS.ZS` |  |  |
| `Alternative and nuclear energy (% of total energy use)` | `EG.USE.COMM.CL.ZS` |  |  |
| `Aquaculture production (metric tons)` | `ER.FSH.AQUA.MT` |  |  |
| `Carbon intensity of GDP (kg CO2e per constant 2015 US$ of GDP)` | `EN.GHG.CO2.RT.GDP.KD` |  |  |
| `Energy imports, net (% of energy use)` | `EG.IMP.CONS.ZS` |  |  |
| `Energy intensity level of primary energy` | `EG.EGY.PRIM.PP.KD` |  |  |
| `Energy use (kg of oil equivalent per capita)` | `EG.USE.PCAP.KG.OE` |  |  |
| `Fossil fuel energy consumption` | `EG.USE.COMM.FO.ZS` |  |  |
| `Total greenhouse gas emissions per capita` | `EN.GHG.ALL.PC.CE.AR5` |  |  |
| `Total fisheries production (metric tons)` | `ER.FSH.PROD.MT` |  |  |
| `Water productivity` | `ER.GDP.FWTL.M3.KD` |  |  |

### 

### `Statistical Indicators Table` 

| `Attribute` | `Series Code` | `Type` | `Purpose` |
| :---- | :---- | :---- | :---- |
| `country_code (FK)` |  | `TEXT` | `Links to Countries table` |
| `series_id (FK)` |  | `TEXT` | `Unique code for statistical indicator` |
| `year (PK)` |  | `INTEGER` | `The year of data` |
| `Business process` | `SPI.D5.2.10.GSBP` |  |  |
| `Business/establishment census (Availability score over 20 years)` | `SPI.D4.1.3.BIZZ` |  |  |
| `Classification of national industry` | `SPI.D5.2.3.CNIN` |  |  |
| `Classification of status of employment` | `SPI.D5.2.6.EMPL` |  |  |
| `Compilation of government finance statistics` | `SPI.D5.2.8.FINA` |  |  |
| `Compilation of monetary and financial statistics` | `SPI.D5.2.9.MONY` |  |  |
| `CRVS (WDI)` | `SPI.D4.2.3.CRVS`  |  |  |
| `Dimension 2.1: Data Releases`  | `SPI.DIM2.1.INDEX` |  |  |
| `Dimension 2.2: Online access` | `SPI.DIM2.2.INDEX` |  |  |
| `Dimension 3.2: Economic Statistics` | `SPI.DIM3.2.INDEX` |  |  |
| `Dimension 4.1: Censuses and Surveys - Censuses only` | `SPI.DIM4.1.CEN.INDEX` |  |  |
| `Dimension 4.2: Administrative Data` | `SPI.DIM4.2.INDEX` |  |  |
| `Dimension 4.3: Geospatial Data` | `SPI.DIM4.3.INDEX` |  |  |
| `Dimension 5.1: Legislation and governance` | `SPI.DIM5.1.INDEX` |  |  |
| `Dimension 5.2: Standards and Methods` | `SPI.DIM5.2.INDEX` |  |  |
| `Finance Indicator based on PARIS21 indicators on SDG 17.18.3 & SDG 17.19.1` | `SPI.D5.5.DIFI` |  |  |
| `Legislation Indicator based on PARIS21 indicators on SDG 17.18.2`  | `SPI.D5.1.DILG` |  |  |
| `GOAL 1: No Poverty (5 year moving average)` | `SPI.D3.1.POV` |  |  |
| `GOAL 8: Decent Work and Economic Growth (5 year moving average)` | `SPI.D3.8.WORK` |  |  |
| `GOAL 9: Industry, Innovation and Infrastructure (5 year moving average)` | `SPI.D3.9.INDY` |  |  |
| `Health/Demographic survey (Availability score over 10 years)` | `SPI.D4.1.7.HLTH` |  |  |
| `Labor force participation rate by sex and age (%)` | `SPI.D1.5.LFP` |  |  |
| `Labor Force Survey (Availability score over 10 years)` | `SPI.D4.1.6.LABR` |  |  |
| `National Accounts base year` | `SPI.D5.2.2.NABY` |  |  |
| `ODIN Open Data Openness score` | `SPI.D2.2.Openness.subscore` |  |  |
| `Pillar 1 - Data Use - Score`  | `SPI.INDEX.PIL1` |  |  |
| `Pillar 2 - Data Services - Score` | `SPI.INDEX.PIL2` |  |  |
| `Pillar 3 - Data Products - Score` | `SPI.INDEX.PIL3` |  |  |
| `Pillar 4 - Data Sources - Score` | `SPI.INDEX.PIL4` |  |  |
| `Pillar 5 - Data Infrastructure - Score` | `SPI.INDEX.PIL5` |  |  |
| `Population & Housing census (Availability score over 20 years)` | `SPI.D4.1.1.POPU` |  |  |
| `System of national accounts in use` | `SPI.D5.2.1.SNAU` |  |  |
|  |  |  |  |

	

