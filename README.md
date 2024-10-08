
# Trip Scraper


The Trip Scraper project involves building a Scrapy web crawler to extract data from Trip.com. The crawler randomly selects three out of five headers—Popular Hotels in the United Kingdom, Popular Hotels Worldwide, Popular Cities in the United Kingdom, Popular Cities Worldwide, and Top Luxury 5-star Hotels. It scrapes hotel details such as the title, photos, rating, latitude, longitude, room type, price, and city. The scraped data is then stored in a PostgreSQL database using SQLAlchemy.



## Table of Contents
1. [Project Overview](#Project-Overview)
2. [Features](#Features)
3. [Project Structure](#Project-Structure)
4. [Installation](#Installation)
5. [Configuration](#Configuration)
6. [Database Setup](#Database-Setup)
7. [Data Model](#Data-Model)
8. [Running the Scraper](#Running-the-Scraper)
9. [Dependencies](#Dependencies)


## Project Overview
The Trip Scraper project is designed to gather detailed information about hotels in various locations. It utilizes the Scrapy framework for web scraping and stores the collected data in a PostgreSQL database. The main focus of the scraper is on extracting hotel information such as:

- hotelId
- hotelName 
- description
- latitude 
- longitude 
- rating 
- amenities 
- images 
- address 
- cityName 

## Features
- Scrapes hotel data from multiple locations.
- Stores data in a PostgreSQL database using SQLAlchemy.
- Extracts images and saves them locally.
- Configurable settings for scraping and database connection

## Project Structure
```
trip_scraper/
├── scrapy.cfg             
├── requirements.txt        
├── .gitignore              
├── README.md              
├── .env.sample                     
├── trip_scraper/            
│   ├── __init__.py
│   ├── items.py            
│   ├── middlewares.py       
│   ├── pipelines.py         
│   ├── settings.py         
│   ├── spiders/             
│   │   ├── __init__.py
│   │   └── trip_spider.py   
│   ├── models/              
│       ├── __init__.py
│       └── hotel.py                        
│      
│            
├── images/                  

````

## Installation
### Prerequisites
- Python 3.8+
- PostgreSQL


1. Clone the repository:

``` bash
git clone https://github.com/samayunPathan/scrapy-assignment-w3.git
```
  Go to directory 
``` bash
cd scrapy-assignment-w3
```

2. Create and activate a virtual environment:
```bash
python3 -m venv venv # On Windows use `python -m venv venv`
```
```bash
source venv/bin/activate  # On Windows use `venv\Scripts\activate`
```


3. Install the dependencies:

``` bash 
pip install -r requirements.txt
```



## Database Setup
Create postgresql database in your system . Also create .env file in your project directory and place DATABASE_URI. When project run automatically create table in database. 

```bash 
DATABASE_URL = "postgresql://username:password@localhost:port/database_name"
```


## Running the Scraper
To run the scraper and start collecting hotel data, use the following command:

``` bash 
scrapy crawl trip_spider
```

## Data Model

The Hotel model in trip_scraper/models/hotel.py defines the structure of the data being scraped and stored:

- hotelId
- hotelName 
- description
- lat
- lon
- rating 
- amenities 
- images 
- address 
- cityName 

## Dependencies
The project dependencies are listed in the requirements.txt file. They include:

- scrapy 
- sqlalchemy
- psycopg2-binary
- python-dotenv

