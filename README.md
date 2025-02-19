# Tokopedia Seblak Sales
## Background
Seblak is a popular dish among Indonesians, it is frequently discussed on social media, leading to the assumption that interest in seblak products is high. Amid this trend, dropshipping on e-commerce platforms like Tokopedia has become a viable business model requiring minimal investment in production.

However, before starting a dropshipping business for seblak, it is crucial to analyze sales trends on Tokopedia to determine whether there is genuine interest in the product. This includes examining factors such as sales volume, product ratings, and pricing.

This project aims to sharpen my data analysis skills, which are essential for making informed decisions in a business model like dropshipping. While direct access to Tokopedia’s sales data is unavailable, web scraping techniques can be employed to gather publicly accessible data on the platform. This data can then be analyzed to understand trends and evaluate the market potential of seblak on Tokopedia.

**The codes and other details of this project can be seen in the `EDA_Seblak_Indonesian.ipynb` file**

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

## Analysis

Before conducting the analysis, it is necessary to describe relevant questions regarding seblak sales:
- `What`: Is seblak the right product in a dropship business scheme?

- `Why`: Why is this analysis important to do before starting a dropship business?

- `Who`: Who can be the target market for this product?

- `Where`: Where is the ideal place for seblak products to be sold, considering production prices?

- `When`: When will this data be taken and analyzed?

- `How`: How do customers perceive seblak products on Tokopedia?

### 1. Statistic Descriptions of product price, amount sold, and product rating
Analyze the distribution of data for the product price, quantity sold, and product rating 

![image](https://github.com/user-attachments/assets/91b3b84e-5098-4d10-963e-e00aae72e6b3)

**Product price**:
- The average price is greater than the median. There are several prices with extreme values ​​that pull the average price upwards
- The standard deviation of `22548.20` is very high, there are significant price fluctuations in the dataset
- Skewness is `4.58`, including highly skewed. The price distribution is highly skewed to the right, meaning that most of the price data has low values

**Amount Sold**:
- The average number of sales is much larger than the median. There are some extreme values ​​that pull the average number of sales upwards
- The standard deviation of `1217.75` is very high, indicating quite extreme variation in the number of sales
- Skewness is `5.24`, highly skewed. The distribution of the number of sales is highly skewed to the right, meaning that most sales have low numbers

**Product Rating**
- The majority of products have very high ratings, close to 5
- The median is close to the mean, indicating a fairly consistent distribution of high ratings, which is around 4.9
- The standard deviation is `0.17`, indicating very low variability in ratings. Most ratings are very close to the mean
- Skewness is `-3.09`, which is highly skewed. The distribution of ratings is highly skewed to the left, meaning that most sales have high ratings (close to 5)

### 2. What is the maximum and minimum profit that can be obtained from selling Seblak in Tokopedia?
Even though the data is skewed, the data will be considered normally distributed with a confidence level of 95%.

**Minimum Profit**: 
### 7071490
**Maximum Profit**: 
### 11038932
**Average Profit**
### 9055211

With 95% confidence, monthly income from selling seblak will be between Rp7,071,490 and Rp11,038,932

### 3. Can the sales area, whether inside or outside Jabodetabek, affect the product price?
The hypothesis that needs to be analyzed is:

H0: price of goods in Jabodetabek = price of goods outside Jabodetabek

H1: price of goods in Jabodetabek! = price of goods outside Jabodetabek

Using Two-Sample Independent Test, the result is:

- The `t-statistic` value is -1.538, indicating that the price difference between seblak in Jabodetabek and outside Jabodetabek is relatively small
- The `p-value` value is 0.124, meaning it is greater than the significance level of 0.05. So H0 is accepted and it is concluded that the price of goods in Jabodetabek and outside Jabodetabek is the same.

### 4. Can the price amount affect the rating obtained for the product?
Similar to the process of determining the upper bound and lower bound, the data will be considered as normally distributed data, so the Pearson correlation test is used.

The hypotheses that need to be analyzed are:

H0: There is no relationship between product price and product rating

H1: There is a relationship between product price and the number of product ratings

The results are:
- Pearson correlation is `0.007`. Because it is close to 0, it shows that product price and product rating do not have a linear relationship. Customers do not tend to give higher or lower ratings based on product price.
- The p-value obtained is `0.84` which is much greater than the significance level of `0.05`. Hypothesis 0 fails to be rejected, there is no significant relationship between price and product rating









