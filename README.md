# Project2Group1

Project 2: Group1

Members : Sohaila, Yared, Ammar, Abhi

Yared - the Category and Subcategory DataFrames
Sohaila -  the Campaign DataFrame
Ammar - the Contacts DataFrame
Abhi - Schema, EBD and compilation

CREATE TABLE Category (
  category_id VARCHAR(30) PRIMARY KEY,
  category VARCHAR(30) NOT NULL
);
SELECT * FROM Category

CREATE TABLE Subcategory (
  subcategory_id VARCHAR(30) PRIMARY KEY,
  subcategory VARCHAR(30) NOT NULL
);
SELECT * FROM Subcategory

CREATE TABLE Resources (
  cf_id INTEGER,
  contact_id INTEGER PRIMARY KEY,
  company_name VARCHAR,	
  description VARCHAR,
  goal FLOAT,
  pledged FLOAT,
  outcome VARCHAR(30),
  backers_count INTEGER,
  country VARCHAR(30),
  currency VARCHAR(30),	
  launched_date DATE,
  end_date DATE,	
  category_id VARCHAR(30) NOT NULL,
  subcategory_id VARCHAR(30) NOT NULL,
  FOREIGN KEY (category_id) REFERENCES Category(category_id),
  FOREIGN KEY (subcategory_id) REFERENCES Subcategory(subcategory_id)
);
SELECT * FROM Resources

CREATE TABLE Contacts (
  contact_id INTEGER,
  first_name VARCHAR(30),
  last_name VARCHAR(30),
  email VARCHAR,
  FOREIGN KEY (contact_id) REFERENCES Resources(contact_id)
);
SELECT * FROM Contacts



