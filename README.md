# Amazon-Web-Scraper-Project

## 📌 Overview

This project is a Python-based web scraper that extracts the **product title** and **price** from an Amazon product page and stores the data in a CSV file.
It is designed to run automatically every 24 hours to help track price changes over time.

## ⚙️ Technologies Used

* Python
* BeautifulSoup
* Requests
* Pandas
* CSV
* Datetime

## 📂 How It Works

1. Sends a request to the Amazon product page using headers.
2. Parses the HTML content using BeautifulSoup.
3. Extracts:
   * Product Title
   * Product Price
4. Stores the data along with the current date in a CSV file.
5. Repeats the process every 24 hours using a loop.

### Sample Format:

| Title        | Price | Date       |
| ------------ | ----- | ---------- |
| Product Name | ₹XXX  | YYYY-MM-DD |

## 🚀 Installation & Setup

### 1. Install Required Libraries

```bash
pip install beautifulsoup4 requests pandas
```

## 🔄 Automation

The script uses:

```python
time.sleep(86400)
```

To run every 24 hours and continuously update the dataset.

---

## ⚠️ Important Notes

* Amazon may block requests if too many requests are sent.
* The price class (`a-color-price`) may not always work because Amazon changes its HTML structure.
* Some products may return `"Not Found"` if elements are not detected.
* This project is intended for **learning purposes only**.

---

## ❗ Limitations

* Does not handle dynamic content (JavaScript-loaded prices).
* No alert system for price drops.
* Relies on static HTML structure.

---


---

## 👩‍💻 Author

Ankitha S
BBA Aviation Management | Aspiring Data Analyst
