# Project: Research Group Data Integrator
This script automates the enrichment of a Cuadro Maestro (Accreditation requirement) by extracting research group codes and cross-referencing them across major academic databases. It streamlines the data collection process from national and international sources into a single consolidated file.

## Core Functionality
The script follows a sequential workflow to update your research data:

1. Read: Accesses the "Cuadro Maestro" via Google Sheets/Drive.
2. Scrape & Query: Retrieves information from:
3. GrupLAC & Publindex: For national research group classifications and journal rankings.
4. Scopus & Web of Science (WoS): For global citation metrics and indexing.
5. Merge: Joins the new metadata with existing records.
6. Write: Updates the original file with the consolidated results.

## Prerequisites
1. API Credentials
To access Scopus data, you must provide your own credentials. You can obtain these from the Elsevier Developer Portal:
- Scopus API Key
- Institutional Token

2. Environment Setup (Google Colab)
The script is designed to run in a Colab environment. You will need to install the Chromium driver and Selenium components:

```
Bash
# Update and install Chromium driver
!apt update > /dev/null
!apt install chromium-chromedriver > /dev/null

# Install Selenium components
!pip3 install selenium > /dev/null
!pip install google-colab-selenium
```
# Required Libraries
The script relies on a robust stack for web scraping, data manipulation, and Google API integration:
1. Data Handling: pandas, numpy, openpyxl
2. Web Scraping: selenium, beautifulsoup4, requests
3. Google Integration: gspread, google.auth, googleapiclient
4. Utilities: re (Regex), time, random

# How to Use
1. Run the main routine cuadro_maestro().
2. Accept the authentication requests
```
python
cuadro_maestro()
```

*Note:* Because this script performs web scraping on MinCiencias platforms (GrupLAC/Publindex), it includes random delays to avoid IP blocking. Please be patient during the execution phase.
