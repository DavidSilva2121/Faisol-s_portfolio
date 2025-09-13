# Faisol-s_portfolio 
 Project 1: 🎵 Spotify Streaming History – Power BI Dashboard
 **Overview**
This project explores a User's personal Spotify streaming history and visualizes insights through an interactive Power BI dashboard.  
The dashboard integrates Spotify artist images and album covers with slicers, giving a visually rich and dynamic exploration of listening habits.

## ⚙️ Data Pipeline
Data Source:  
   Exported streaming history from Spotify (Spotify_history.xlsx) through Maven Analytics.
Data Enrichment:  
   - Used the Spotify Web API via Python to fetch:  
     - Artist profile images → stored in artist_images_updated.xlsx  
     - Album cover images → stored in album_images.xlsx  
Power BI Dashboard:  
   - Connected enriched datasets  
   - Built relationships between artists, albums, and streams  
   - Created slicers for artist/album selection with images  
   - Designed KPIs and charts for trends, top artists, and albums  

## 📊 Dashboard Features

- 🎤 Artist Slicer – select an artist and see their image + stats  
- 💿 Album Slicer – filter by albums with dynamic cover art  
- ⏳ Trends Over Time – visualize listening habits weekly/monthly  
- 📈 KPIs – Total streams, top artist, top albums, tracks released  
- 🖼️ Dynamic Images – artist profile pictures and album covers change with slicer selection  

## 🛠️ Tools & Technologies

- Power BI → dashboard & visualization  
- Python → API calls & Excel updates  
  - Libraries: pandas, requests, openpyxl  
- Spotify Web API → images & metadata  
- GitHub → version control & project sharing  

## 📥 Files

- [Download Dashboard (.pbix)](SPOTIFY%20X.pbix)
- [View Dashboard PDF](SPOTIFY%20X.pdf)




# PROJECT 2: 🦠 COVID-19 Power BI Dashboard

## 📌 Project Overview
This project is a **Power BI dashboard** that analyzes the **global impact of COVID-19** in terms of **cases, deaths, hospitalizations, testing, and vaccinations**.  
The dashboard provides interactive insights across continents and countries, with a focus on **Europe** and **Asia**.

## 📊 Datasets Used (All data gotten from World Health Organization)
1. **CovidDeaths.csv**
   - Key columns:
     - `iso_code`, `continent`, `location`, `date`, `population`
     - `total_cases`, `new_cases`, `total_deaths`, `new_deaths`
     - `hosp_patients`, `icu_patients`, `hosp_patients_per_million`, `icu_patients_per_million`
     - `aged_65_older` (share of population over 65 years)
   
2. **CovidVaccinations.xlsx**
   - Key columns:
     - `location`, `date`
     - `total_vaccinations`, `people_vaccinated`, `people_fully_vaccinated`
     - `new_vaccinations`
     - `total_vaccinations_per_hundred`, `people_vaccinated_per_hundred`, `people_fully_vaccinated_per_hundred`
     - `positive_rate`, `tests_per_case`


## 🛠️ Data Preparation
1. Imported **CovidDeaths.csv** and **CovidVaccinations.xlsx** into Power BI.
2. Ensured `date` was of type *Date* and `population` was numeric.
3. Cleaned null values:
   - Removed aggregate rows (e.g., `location = "Europe"`, `"Asia"`, `"World"`).
   - Fixed missing continent values by mapping each country to its continent.
4. Created relationships:
   - Linked **CovidDeaths** and **CovidVaccinations** on `location` and `date`.

## 🧮 DAX Measures
Key measures created:
dax
-Mortality / Death Rate
Death Rate = DIVIDE(SUM(CovidDeaths[total_deaths]), SUM(CovidDeaths[total_cases]))
-- Vaccination Rate (at least 1 dose)
Vaccination Rate = DIVIDE(SUM(CovidVaccinations[people_vaccinated]), SUM(CovidDeaths[population]))
-- Fully Vaccinated Rate
Fully Vaccinated Rate = DIVIDE(SUM(CovidVaccinations[people_fully_vaccinated]), SUM(CovidDeaths[population]))
-- Average Daily Deaths
Average Daily Deaths = 
AVERAGEX(
    FILTER(CovidDeaths, NOT(ISBLANK(CovidDeaths[new_deaths]))),
    CovidDeaths[new_deaths]
)

-- Total New Cases (Continent not blank)
Total New Cases (Valid Continent) = 
CALCULATE(
    SUM(CovidDeaths[new_cases]),
    NOT(ISBLANK(CovidDeaths[continent]))
)
``
## 📂 Project Files
📊 [Covid.pbix](./Covid.pbix) — Power BI dashboard file (open with Power BI Desktop)  
📄 [Covid.pdf](./Covid.pdf) — Exported PDF snapshot of the dashboard





## 💡 Key Insights

* Elderly Populations: Countries with higher % of population aged 65+ experienced higher death rates.
* Testing: Many African countries had low testing rates, suggesting underreporting.
* Vaccinations: Europe and North America had significantly higher vaccination rates compared to Africa.
* Waves: Clear peaks in cases and deaths visible around April 2021 and January 2021.
