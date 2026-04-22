#Amazon Web Scraper project

from bs4 import BeautifulSoup
import requests

URL = "https://www.amazon.in/dp/1590594487"

headers = {
    "User-Agent": "Mozilla/5.0",
    "Accept-Language": "en-US,en;q=0.9"
}

page = requests.get(URL, headers=headers)
soup = BeautifulSoup(page.content, "html.parser")

# Title
title_tag = soup.find(id="productTitle")
title = title_tag.get_text().strip() if title_tag else "Not Found"

# Price
price_tag = soup.find("span", class_="a-color-price")
price = price_tag.get_text().strip() if price_tag else "Not Found"

print(title)
print(price)

import datetime
today = datetime.date.today()
print(today)

# Save clean data

import csv
header = ['Title', 'Price', 'Date']
data = [title, price, today]

with open('AmazonWebScraperDataset.csv', 'w', newline='', encoding='utf-8-sig') as f:
    writer = csv.writer(f)
    writer.writerow(header)
    writer.writerow(data)

#To read the data
import pandas as pd
df = pd.read_csv(r"C:\Users\PI\Documents\python_learning\AmazonWebScraperDataset.csv")
print(df)

#Create a function and paste the above code into it

def check_price():
    try:
        URL = "https://www.amazon.in/dp/1590594487"

        headers = {
            "User-Agent": "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 Chrome/120.0.0.0 Safari/537.36",
            "Accept-Language": "en-US,en;q=0.9"
        }

        page = requests.get(URL, headers=headers)
        soup = BeautifulSoup(page.content, "html.parser")

        # Extract Title
        title_tag = soup.find(id="productTitle")
        title = title_tag.get_text().strip() if title_tag else "Not Found"

        # Extract Price
        price_tag = soup.find("span", class_="a-color-price")
        price = price_tag.get_text().strip() if price_tag else "Not Found"

        # Date
        today = datetime.date.today()

        # Data row
        data = [title, price, today]

        # Append to CSV
        with open('AmazonWebScraperDataset.csv', 'a+', newline='', encoding='utf-8-sig') as f:
            writer = csv.writer(f)
            writer.writerow(data)

        print("Saved:", data)

    except Exception as e:
        print("Error:", e)

"""
# Create CSV file with header (RUN ONLY ONCE)

with open('AmazonWebScraperDataset.csv', 'w', newline='', encoding='utf-8-sig') as f:
    writer = csv.writer(f)
    writer.writerow(['Title', 'Price', 'Date'])
"""

# Run daily
while True:
    check_price()
    time.sleep(86400)   # 24 hours
