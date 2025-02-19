# Tokopedia Seblak Sales
## Background
Seblak is a popular dish among Indonesians, it is frequently discussed on social media, leading to the assumption that interest in seblak products is high. Amid this trend, dropshipping on e-commerce platforms like Tokopedia has become a viable business model requiring minimal investment in production.

However, before starting a dropshipping business for seblak, it is crucial to analyze sales trends on Tokopedia to determine whether there is genuine interest in the product. This includes examining factors such as sales volume, product ratings, and pricing.

This project aims to sharpen my data analysis skills, which are essential for making informed decisions in a business model like dropshipping. While direct access to Tokopedia’s sales data is unavailable, web scraping techniques can be employed to gather publicly accessible data on the platform. This data can then be analyzed to understand trends and evaluate the market potential of seblak on Tokopedia.

## Objective
- Gather sales data for seblak from Tokopedia through web scraping, including details such as product names, prices, sales volume, seller locations, and ratings.
- Analyze the factors that influence customer interest in the product.
- Provide business insights based on the data analysis to determine whether seblak is a suitable product for a dropshipping business on Tokopedia.

## Web Scrapping
This is the Web Scrapping process, done by Selenium and BeautifulSoup:

- Taken the page displayed by Tokopedia after entering the keyword seblak into the search engine
- The data taken is the product name, product price, seller name, seller's city of origin, and product rating
- Taken only the first 10 pages

The Web Scrapping process

![webscrapping](https://github.com/user-attachments/assets/2f33db9d-1b23-4806-82bb-7adcaefc082f)

## Data Processing
The data is received but it's still dirty with several issues:

- Because there are several new stores, some data that do not have many sales and product ratings are taken. The data rows for these stores were removed.
- The product price, sum of sales, and product rating columns still have the wrong type, namely String. This is because the data numbers still contain accessories such as `Rp`, `.`, `+`, `rb`, and `terjual` signs. The product price and many sales were changed to `Integer`, while the product rating becomes `Float`.
- Because the product name and store name are input from the user, there are potentials for human error, it is necessary to remove whitespace.

Here's a preview of the cleaned data.

![image](https://github.com/user-attachments/assets/e2a7f1d4-1737-493e-8686-f274b765612b)



