**Introduction:** 

We have applied normalization principles to ensure data integrity, avoid redundancy, and maintain efficiency in querying and  in organizing data in a database so that it is not as likely to have data inconsistency and has more accurate data. We have set up relationships between tables 

**Using Normalization Principles**

**1.First Normal Form**

* Certainty of atomicity: Each field has atomic numbers. Rather than keeping many years in one column, for instance, each year has its own row.  
* Removing redundant columns: The schema has a quarter field instead of different columns for each quarter, which cuts down on the need to create extra columns.

**2\. Second Normal Form**  
Removed the a few dependencies:

* Separated the countries and series tables so that attributes only depend on their main keys.  
* Series table stores unique indicators, and each record refers to it using series\_id instead of repeating series information in each indicator table.

**3\. Third normal form:**  
Removed transitive dependencies:

* Series-related data is kept separate from other data in various tables by storing series\_id in a separate table.  
* By using country\_id, information about a country is not repeated in more than one table.

**4.Boyce-Codd Normal Form (BCNF):**  
Keenly maintained functional dependencies:

* Uniquely identifying records without needless dependencies, each table's main key does this.  
* Using auto-incremented ID fields instead of composite keys when they weren't needed kept the data simpler.

**Conclusion:**  
The database schema uses normalization rules to keep data correct, avoid duplicates, and keep queries as fast as possible. After these normalization steps, we’ve have a database that is well-structured, adaptable, and fast.  
