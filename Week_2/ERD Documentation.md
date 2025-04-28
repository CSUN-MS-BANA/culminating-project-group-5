## **`Overview`**

`The Entity-Relationship Diagram (ERD) for a relational database holding various economic, social, environmental, public debt, and statistical data for nations across several years is described in this paper.`

## **`Database Entities and Attributes`**

`The database consists of seven primary entities:`

1. **`Countries`**  
2. **`Series`**  
3. **`Economic Indicators`**  
4. **`Social Indicators`**  
5. **`Public Debt Indicators`**  
6. **`Environmental Indicators`**  
7. **`Statistical Indicators`**

`Each of these entities has attributes defining the data they store and relationships with other entities.`

## **`Relationships and Cardinality`**

* **`Countries : Indicators (Economic, Social, Public Debt, Environmental, Statistical)`**  
  * **`1:M`** `(One country can have multiple indicators)`  
  * **`Optional Many to Mandatory One`** `(0:M to 1:1)`  
* **`Series : Indicators (Economic, Social, Public Debt, Environmental, Statistical)`**  
  * **`1:M`** `(One series can have multiple data records)`  
  * **`Optional Many to Mandatory One`** `(0:M to 1:1)`

