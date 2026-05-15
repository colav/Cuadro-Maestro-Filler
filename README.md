## Project: Research Group Data Integrator
This script automates the enrichment of a Cuadro Maestro (Master Spreadsheet) by extracting research group codes and cross-referencing them across major academic databases. It streamlines the data collection process from national and international sources into a single consolidated file.

Core Functionality
The script follows a sequential workflow to update your research data:

Read: Accesses the "Cuadro Maestro" via Google Sheets/Drive.

Scrape & Query: Retrieves information from:

GrupLAC & Publindex: For national research group classifications and journal rankings.

Scopus & Web of Science (WoS): For global citation metrics and indexing.

Merge: Joins the new metadata with existing records.

Write: Updates the original file with the consolidated results.

Prerequisites
1. API Credentials
To access Scopus data, you must provide your own credentials. You can obtain these from the Elsevier Developer Portal.

Scopus API Key

Institutional Token

2. Environment Setup (Google Colab)
The script is designed to run in a Colab environment. You will need to install the Chromium driver and Selenium components:

Bash
# Update and install Chromium driver
!apt update > /dev/null
!apt install chromium-chromedriver > /dev/null

# Install Selenium components
!pip3 install selenium > /dev/null
!pip install google-colab-selenium
Required Libraries
The script relies on a robust stack for web scraping, data manipulation, and Google API integration:

Data Handling: pandas, numpy, openpyxl

Web Scraping: selenium, beautifulsoup4, requests

Google Integration: gspread, google.auth, googleapiclient

Utilities: re (Regex), time, random

# How to Use
1. Run the main routine cuadro_maestro().
2. Accept the authentication requests

Configuration: Input your Scopus API keys and the file ID/name of your Cuadro Maestro when prompted.

Execution: Run the processing cells. The script will use a headless Chrome browser to navigate GrupLAC and Publindex.

Verification: Once the script finishes, the "Cuadro Maestro" will be updated with the latest metrics and indexing info.

Note: Because this script performs web scraping on MinCiencias platforms (GrupLAC/Publindex), it includes random delays to avoid IP blocking. Please be patient during the execution phase.
