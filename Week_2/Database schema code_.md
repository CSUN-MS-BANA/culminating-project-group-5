Database schema code:

\-- 1\. Create the database  
DROP DATABASE IF EXISTS world\_bank\_focused;  
CREATE DATABASE world\_bank\_focused;

\-- 2\. Switch to the new database  
USE world\_bank\_focused;

\-- 3\. Create tables with the specified indicator categories

\-- Create countries table  
CREATE TABLE countries (  
    country\_code VARCHAR(10) PRIMARY KEY,  
    country\_name VARCHAR(255) NOT NULL  
);

\-- Create series table  
CREATE TABLE series (  
    series\_code VARCHAR(50) PRIMARY KEY,  
    series\_name TEXT NOT NULL,  
    category VARCHAR(50) NOT NULL  
);

\-- Public Debt Indicators  
CREATE TABLE public\_debt\_indicators (  
    country\_code VARCHAR(10) NOT NULL,  
    country\_name VARCHAR(255) NOT NULL,  
    series\_code VARCHAR(50) NOT NULL,  
    series\_name TEXT NOT NULL,  
    Year INT NOT NULL,  
    quarter FLOAT,  
    Value TEXT,  
    PRIMARY KEY (country\_code, series\_code, Year, quarter),  
    FOREIGN KEY (country\_code) REFERENCES countries(country\_code),  
    FOREIGN KEY (series\_code) REFERENCES series(series\_code)  
);

\-- Economical Indicators  
CREATE TABLE economical\_indicators (  
    country\_code VARCHAR(10) NOT NULL,  
    country\_name VARCHAR(255) NOT NULL,  
    series\_code VARCHAR(50) NOT NULL,  
    series\_name TEXT NOT NULL,  
    Year INT NOT NULL,  
    Value TEXT,  
    PRIMARY KEY (country\_code, series\_code, Year),  
    FOREIGN KEY (country\_code) REFERENCES countries(country\_code),  
    FOREIGN KEY (series\_code) REFERENCES series(series\_code)  
);

\-- Environmental Indicators  
CREATE TABLE environmental\_indicators (  
    country\_code VARCHAR(10) NOT NULL,  
    country\_name VARCHAR(255) NOT NULL,  
    series\_code VARCHAR(50) NOT NULL,  
    series\_name TEXT NOT NULL,  
    Year INT NOT NULL,  
    Value TEXT,  
    PRIMARY KEY (country\_code, series\_code, Year),  
    FOREIGN KEY (country\_code) REFERENCES countries(country\_code),  
    FOREIGN KEY (series\_code) REFERENCES series(series\_code)  
);

\-- Social Indicators  
CREATE TABLE social\_indicators (  
    country\_code VARCHAR(10) NOT NULL,  
    country\_name VARCHAR(255) NOT NULL,  
    series\_code VARCHAR(50) NOT NULL,  
    series\_name TEXT NOT NULL,  
    Year INT NOT NULL,  
    Value TEXT,  
    PRIMARY KEY (country\_code, series\_code, Year),  
    FOREIGN KEY (country\_code) REFERENCES countries(country\_code),  
    FOREIGN KEY (series\_code) REFERENCES series(series\_code)  
);

\-- Statistical Indicators  
CREATE TABLE statistical\_indicators (  
    country\_code VARCHAR(10) NOT NULL,  
    country\_name VARCHAR(255) NOT NULL,  
    series\_code VARCHAR(50) NOT NULL,  
    series\_name TEXT NOT NULL,  
    Year INT NOT NULL,  
    Value TEXT,  
    PRIMARY KEY (country\_code, series\_code, Year),  
    FOREIGN KEY (country\_code) REFERENCES countries(country\_code),  
    FOREIGN KEY (series\_code) REFERENCES series(series\_code)  
);

\-- Financial Indicators  
CREATE TABLE financial\_indicators (  
    country\_code VARCHAR(10) NOT NULL,  
    country\_name VARCHAR(255) NOT NULL,  
    series\_code VARCHAR(50) NOT NULL,  
    series\_name TEXT NOT NULL,  
    Year INT NOT NULL,  
    Value TEXT,  
    PRIMARY KEY (country\_code, series\_code, Year),  
    FOREIGN KEY (country\_code) REFERENCES countries(country\_code),  
    FOREIGN KEY (series\_code) REFERENCES series(series\_code)  
);

\-- Create indexes for better query performance  
CREATE INDEX idx\_public\_debt\_country ON public\_debt\_indicators(country\_code);  
CREATE INDEX idx\_public\_debt\_series ON public\_debt\_indicators(series\_code);  
CREATE INDEX idx\_public\_debt\_year ON public\_debt\_indicators(Year);  
CREATE INDEX idx\_public\_debt\_quarter ON public\_debt\_indicators(quarter);

CREATE INDEX idx\_economical\_country ON economical\_indicators(country\_code);  
CREATE INDEX idx\_economical\_series ON economical\_indicators(series\_code);  
CREATE INDEX idx\_economical\_year ON economical\_indicators(Year);

CREATE INDEX idx\_environmental\_country ON environmental\_indicators(country\_code);  
CREATE INDEX idx\_environmental\_series ON environmental\_indicators(series\_code);  
CREATE INDEX idx\_environmental\_year ON environmental\_indicators(Year);

CREATE INDEX idx\_social\_country ON social\_indicators(country\_code);  
CREATE INDEX idx\_social\_series ON social\_indicators(series\_code);  
CREATE INDEX idx\_social\_year ON social\_indicators(Year);

CREATE INDEX idx\_statistical\_country ON statistical\_indicators(country\_code);  
CREATE INDEX idx\_statistical\_series ON statistical\_indicators(series\_code);  
CREATE INDEX idx\_statistical\_year ON statistical\_indicators(Year);

CREATE INDEX idx\_financial\_country ON financial\_indicators(country\_code);  
CREATE INDEX idx\_financial\_series ON financial\_indicators(series\_code);  
CREATE INDEX idx\_financial\_year ON financial\_indicators(Year);

CREATE INDEX idx\_series\_category ON series(category);  
