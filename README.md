# GIPSI: Geospatial Intelligence Pipeline for Security Incidents

**An automated ETL pipeline that scrapes, structures, and visualizes real-time security data in Yucatán with historical persistence.**

## Project Overview
**GIPSI** (Geospatial Intelligence Pipeline: Security Incidents) is a Python-based tool designed to transform unstructured journalistic text into actionable geospatial intelligence. Unlike simple scrapers, GIPSI implements a **Data Persistence Engine**, allowing the system to accumulate incident data over time rather than just showing a daily snapshot.

It solves the "location ambiguity" problem in news by using a **Hierarchical Geocoding Strategy**, prioritizing specific neighborhoods (e.g., *Juan Pablo II*, *Altabrisa*) before defaulting to municipal centers.

##  Key Technical Features
* ** Data Persistence Engine:** Merges new scraping results with a local CSV database (`base_datos_seguridad_acumulada.csv`), handling deduplication automatically.
* ** Hierarchical Geocoding:** Custom logic that attempts to resolve precise neighborhood locations first, falling back to municipality centroids only when necessary.
* ** Stochastic Jittering:** Implements a coordinate noise algorithm to prevent marker overlap in high-density areas (e.g., distinct incidents on the same highway).
* ** GIS Interoperability:** Exports processed data to standard **GeoJSON** format (`security_incidents.geojson`), making it compatible with professional GIS software like QGIS or ArcGIS.

## Tech Stack
* **Core:** Python 3.14
* **ETL & Database:** Pandas (DataFrames, CSV persistence, Merging logic)
* **Web Scraping:** BeautifulSoup4, Requests (Targeting Google News RSS)
* **Geospatial:** Geopy (Nominatim API), Folium (Leaflet.js mapping), GeoJSON
* **Environment:** Jupyter Notebook / VS Code

## Repository Structure
| File | Description |
| :--- | :--- |
| `GIPSI.ipynb` | **Main Pipeline.** Contains the ETL, Geocoding, and Visualization logic. |
| `index.html` | **Interactive Map.** The final visual output (Download to view). |
| `base_datos_...csv` | **The Memory.** Persistent database containing historical records. |
| `security_...geojson` | **GIS Data.** Standard vector file for external GIS tools. |

## How to Run
1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/W-code-04/geospatial-news-tracker-yucatan.git](https://github.com/W-code-04/geospatial-news-tracker-yucatan.git)
    ```
2.  **Install dependencies:**
    ```bash
    pip install pandas folium geopy beautifulsoup4 requests
    ```
3.  **Run the Pipeline:**
    Open `GIPSI.ipynb` in Jupyter/VS Code and run all cells. The script will:
    * Fetch new data.
    * Update the CSV database.
    * Regenerate the `index.html` map.

## Visualization Preview
* **View the Notebook:** [Click here to render GIPSI.ipynb on nbviewer](https://nbviewer.org/github/W-code-04/geospatial-news-tracker-yucatan/blob/main/GIPSI.ipynb)
* *Note: GitHub does not render interactive maps natively. Please use nbviewer or download the HTML file.*

---
*Developed by William Canché | 2025*
