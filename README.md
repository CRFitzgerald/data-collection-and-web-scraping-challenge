# data-collection-and-web-scraping-challenge

This challenge focuses on web scraping for data analysis. By identifying HTML elements on the two webpages, I was able to use automated browsing and HTML parsing to extract data. Once extracted, I converted to Pandas DataFrames for analysis.

### Tools Used
* Splinter
* Beautiful Soup
* Python
* Pandas
* Matplotlib

## Part 1 - Use Automated Browsing to Scrape Titles and Preview Text

The code for Part 1 is in the jupyter notebook titled part_1_mars_news.ipynb.

1. I levereaged Splinter to to start an automated browsing session on the Mars news website. I inspected the page to identify relevant elements.
2. I created a Beautiful Soup object (called mars-soup, *chef's kiss*), to extract text elements from the site.
3. I created a Python list to contain dictionaries of the scraping results. Each dictionary has two keys: "title" and "preview." The list is printed in the notebook.
4. The browser session is quit.

## Part 2 - Use Automated Browsing to Scrape Mars Weather Data from a Table

The code for Part 2 is in the jupyter notebook titled part_2_mars_weather.

1. I levereaged Splinter to to start an automated browsing session on the Mars temperature website. I inspected the page to identify table elements.
2. I created a Beautiful Soup object (once again called mars-soup), to extract data from the table rows.
3. Using a for-loop, I put the data from the rows into an empty list called "table." I created a Pandas DataFrame from the "table" list as well as a list of column names.
4. I checked the datatypes and they were all initially object. I used pd.to_datetime to convert the "terrestrial_date" column values to Datetime. I used .astype to convert the "sol," "ls," and "month" columns to Integer and "min_temp," "pressure" to Float.
5. I confirmed afterward that the datatypes had been changed using a dtypes query.

### Part 2 Analysis
1. I used .nunique() to find there are 12 months on Mars.
2. I used .max() to find there are 1977 Martian days' worth of data.
3. The coldest month at Curiosity's location on Mars is the third month with minimum temperatures averaging -83.307292 C. The hottest month is the eight month with minimum temperature averaging -68.382979 C.
4. The month with the lowest atmospheric pressure in Curiosity's location on Mars is the sixth month with pressure averaging 745.054422. The ninth month is highest with pressure averaging 913.305970.
5. I plotted a linechart with Pandas Plotting to compare earth dates with minimum temperatures. The temperature peaks look to be at around 125 days, 750days, 1425 days, which averages about 650 "earth days" apart.

I exported the dataframe to a CSV called mars_temp_data.csv.
