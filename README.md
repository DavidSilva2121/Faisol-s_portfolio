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

- [Download Dashboard (.pbix)](Spotify_PowerBI.pbix)
- [View Dashboard PDF](Spotify_PowerBI.pdf)
 


## 🚀 How to Use

1. Clone the repository:
   `bash
   git clone https://github.com/<your-username>/<your-repo-name>.git

GitHub (https://github.com/)
GitHub · Build and ship software on a single, collaborative platform
Join the world's most widely adopted, AI-powered developer platform where millions of developers, businesses, and the largest open source community build software that advances humanity.
