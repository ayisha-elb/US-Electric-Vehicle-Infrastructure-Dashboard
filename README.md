# Electric Vehicle (EV) Charging Infrastructure Dashboard

## Project Overview
<br>

This project combines API integration, PostgreSQL, and Tableau to create a dashboard showcasing information regarding electric vehicle (EV) infrastructure in the United States. All data was retrieved through the NLR AFDC API and the US Census Bureau Population API. This data was then linked to a Tableau dashboard through a PostgreSQL database. This project examines the total number of registered EVs and plug-in hybrid electric vehicles (PHEVs) per state, the total number of ports and stations per state by population density (per 100,000 people) and land area (per 1000 sq miles), the number of EVs per port and station per state, the number of EVs per fast charging ports (i.e. Level 2 and DC fast), the percent of ports that are DC fast per state, and more. This data can be used to analyze which parts of the US have gaps in EV charging infrastructure, and this information can aid in deciding where to focus future charging station projects in addition to identifying areas of congestion, and EV and PHEV usage per state. This project also shows the amount of charging stations available every year since 2001, which shows the trend in how quickly charging station infrastructure is being built. Median household income is also compared EV accessibility and port density by state.
<br>

Note: A station can have multiple ports. To compare with contemporary gas stations: a port is to a gas pump and a charging station is to a gas station.


## Tools Used

Python
Pandas
Requests
SQLAlchemy
Jupyter Notebook
PostgreSQL
Tableau
Public APIs

## Data Sources

NLR AFDC API
US Census Bureau Population API
AFDC Vehicle Registration Data
State land area reference data

## Key Metrics

Charging stations per 100,000 people
Charging ports per 100,000 people
DC fast charging ports per 100,000 people
Stations per 1,000 square miles
Ports per 1,000 square miles
DC fast charging ports per 1,000 square miles
EVs per charging station
EVs per charging port
EVs per DC fast charging port
EVs per weighted fast charging ports by score
PHEVs per charging station
PHEVs per charging port
PHEVs per DC fast charging port
Weighted fast charging ports by score per 100,000 people
Population density
Median household income
Charging speed capacity score


## Project Workflow
Extract EV charging station data from the NREL AFDC API using paginated API requests.
Clean and transform station-level data using Pandas.
Retrieve population and median household income data from the Census API.
Add EV registration and plug-in hybrid registration data.
Engineer state-level accessibility, infrastructure pressure, and density metrics.
Load cleaned datasets into PostgreSQL.
Validate the database using SQL queries.
Build Tableau dashboards to visualize state rankings and national charging station locations.


## Dashboard Features

The Tableau dashboard includes:
<br>

National maps of EV charging station and port density by state
A national map of EV density by state
State-level rankings of charging infrastructure accessibility
Metrics comparing EV demand to available charging infrastructure
Fast-charging access comparisons
Population density and income-based infrastructure analysis
<br> 

Please note the .twbx version of the dashboard is not updatable through API integration; this downloadable version was uploaded for ease of access and viewing. You must follow the instructions in this file if you want to see the live, updated dashboard.

## How to Run This Project

1. Clone the repository.
git clone <your-repo-url>
<br>

2. Install required Python packages.
!pip install -r requirements.txt
<br>

3. Create a .env file in the project folder.
***Please title your file as just ".env"***
<br>

4. Add your API keys and local PostgreSQL connection string to the .env file.

  NREL_API_KEY=your_nrel_api_key_here

  CENSUS_API_KEY=your_census_api_key_here

  DB_CONNECTION=postgresql://postgres:your_password@localhost:5432/ev_project

<br>

NLR API key signup: https://developer.nlr.gov/signup/

Census API key signup: https://api.census.gov/data/key_signup.html
<br>


5. Create a PostgreSQL database named ev_project.
<br>

6. Run the entire Jupyter notebook to extract, clean, transform, and load the data. 
<br>

7. Open Tableau and connect to the PostgreSQL database or use the exported CSV files.
<br>

## Repository Structure
ev-infrastructure-analytics (main file):  README.md,  requirements.txt,  .gitignore,  env.example,  notebooks --> ev_infrastructure_analysis.ipynb,  sql --> ev_project.sql,  images showing Tableau dashboard,  .csv backup files, .twbx (not connected to the API)
<br>

## Future Improvements

Potential future improvements include:
<br>

County-level EV infrastructure analysis
Rural vs. urban charging gap analysis
Income-based equity scoring
Charging infrastructure forecasting
Integration of EV adoption growth trends over time
