# geospatial-news-tracker-yucatan
Python automation tool that scrapes local news, analyzes security incidents, and generates interactive heatmaps with geolocation jittering.
Geospatial Security Tracker: Yucatán
Overview
This project transforms unstructured web data into geospatial intelligence. It automates the extraction of security-related news (accidents, police activity) from local media sources and visualizes them on an interactive heatmap.
Key Technical Feature: Implements a Random Jittering Algorithm to solve the problem of overlapping coordinates, allowing for precise visualization of high-density incident areas in cities like Mérida.
Tech Stack:
 -Language: Python 3.14
 -Data Extraction: BeautifulSoup4, Requests (Google News RSS scraping)
 -Geospatial Processing: Geopy (Nominatim API), Folium (Leaflet.js wrapper)
 -Data Analysis: Pandas (ETL & Cleaning)
Project Output: The tool generates an interactive HTML map where incidents are clustered dynamically.
The tool generates an interactive HTML map where incidents are clustered dynamically.
View the script: [proyecto_final_seguridad.ipynb](proyecto_final_seguridad.ipynb)
View the map: Download the .html file to view locally
How to Run
1. Clone this repository
2. Install dependencies: "bash
   pip install pandas folium geopy beautifulsoup4 requests"
3. Run the Jupyter Notebook
