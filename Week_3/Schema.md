**Schema**

**Countries Table**  
CREATE TABLE IF NOT EXISTS Countries (  
    country\_code VARCHAR(10) PRIMARY KEY,  
    country\_name TEXT NOT NULL  
);

**Series Table:**  
CREATE TABLE IF NOT EXISTS Series (  
    series\_code VARCHAR(50) PRIMARY KEY,  
    series\_name TEXT NOT NULL  
);

**Economic Indicators Table:**  
CREATE TABLE IF NOT EXISTS Economic\_Indicators (  
    country\_code VARCHAR(10) NOT NULL,  
    country\_name TEXT NOT NULL,  
    series\_code VARCHAR(50) NOT NULL,  
    series\_name TEXT NOT NULL,  
    year INT NOT NULL,  
    value DECIMAL(15,2),  
    PRIMARY KEY (country\_code, series\_code, year),  
    FOREIGN KEY (country\_code) REFERENCES Countries(country\_code),  
    FOREIGN KEY (series\_code) REFERENCES Series(series\_code)  
);

**Environmental Indicators Table:**

CREATE TABLE IF NOT EXISTS Environmental\_Indicators (  
    country\_code VARCHAR(10) NOT NULL,  
    country\_name TEXT NOT NULL,  
    series\_code VARCHAR(50) NOT NULL,  
    series\_name TEXT NOT NULL,  
    year INT NOT NULL,  
    value DECIMAL(15,2),  
    PRIMARY KEY (country\_code, series\_code, year),  
    FOREIGN KEY (country\_code) REFERENCES Countries(country\_code),  
    FOREIGN KEY (series\_code) REFERENCES Series(series\_code)  
);

**Public Debt Indicators Table:**  
CREATE TABLE IF NOT EXISTS Public\_Debt\_Indicators (  
    country\_code VARCHAR(10) NOT NULL,  
    country\_name TEXT NOT NULL,  
    series\_code VARCHAR(50) NOT NULL,  
    series\_name TEXT NOT NULL,  
    year INT NOT NULL,  
    quarter VARCHAR(2) NOT NULL,  
    value DECIMAL(15,2),  
    PRIMARY KEY (country\_code, series\_code, year, quarter),  
    FOREIGN KEY (country\_code) REFERENCES Countries(country\_code),  
    FOREIGN KEY (series\_code) REFERENCES Series(series\_code)  
);

**Social Indicators Table**:  
CREATE TABLE IF NOT EXISTS Social\_Indicators (  
    country\_code VARCHAR(10) NOT NULL,  
    country\_name TEXT NOT NULL,  
    series\_code VARCHAR(50) NOT NULL,  
    series\_name TEXT NOT NULL,  
    year INT NOT NULL,  
    value DECIMAL(15,2),  
    PRIMARY KEY (country\_code, series\_code, year),  
    FOREIGN KEY (country\_code) REFERENCES Countries(country\_code),  
    FOREIGN KEY (series\_code) REFERENCES Series(series\_code)  
);

**Statistical Indicators Table:**

CREATE TABLE IF NOT EXISTS Statistical\_Indicators (  
    country\_code VARCHAR(10) NOT NULL,  
    country\_name TEXT NOT NULL,  
    series\_code VARCHAR(50) NOT NULL,  
    series\_name TEXT NOT NULL,  
    year INT NOT NULL,  
    value DECIMAL(15,2),  
    PRIMARY KEY (country\_code, series\_code, year),  
    FOREIGN KEY (country\_code) REFERENCES Countries(country\_code),  
    FOREIGN KEY (series\_code) REFERENCES Series(series\_code)  
);

