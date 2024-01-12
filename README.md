# Python Project Showcase

This space is dedicated to showcasing a collection of projects where I've used various **Python libraries** to *handle data, clean datasets, conduct exploratory data analysis (EDA), and create insightful visualizations*. 

## File Population 

I took the official website of *Peru Merco Empresas 2023*, a business monitor of corporate reputation that shows the top 100 best companies in Peru to populate a CSV file with the most relevant data in order to make use of data from web.

📘 **Libraries/Packages Used:**
- Beautiful Soup
- Requests
- Pandas

✍️ **Code Example:**

```python
from bs4 import BeautifulSoup
import requests 
url = 'https://www.merco.info/pe/ranking-merco-empresas'
page = requests.get(url)
soup = BeautifulSoup(page.text, 'html')
```

```python
titulos = table.find_all('th')
titulos_tabla = [cabecera.text.strip() for cabecera in titulos]
print(titulos_tabla)
```

## Data Cleaning

I used a dummy file directory of well-known movie characters to remove duplicates, unnecessary columns, blanks and non-numeric data; split columns and replace data.

📘 **Libraries/Packages Used:**
- Pandas

 ✍️ **Code Example:**
 
```python
df = df.drop_duplicates()
df
df = df.drop(columns = 'Not_Useful_Column')
df
```

```python
df['Phone_Number'] = df['Phone_Number'].replace('[^0-9]', '', regex=True)
df
```

```python
df[['Street', 'City', 'Zipcode']] = df['Address'].str.split(',', expand=True)
df.drop(columns=['Address'], inplace=True)
df
```

## Exploratory Data Analysis (EDA)

I worked with a file of actual world population data by country from the 1970s to 2022, as well as each country's area, density and growth rate in which I could see that the continent with the highest population growth rate is Asia and the lowest is Oceania.

📘 **Libraries/Packages Used:**
- Pandas
- Seaborn
- Matplotlib.pyplot

✍️ **Code Example:**

```python
pd.set_option('display.float_format', lambda x: '%.2f' % x)
#Change decimal format

```

```python
plt.figure(figsize=(8, 5))
sns.heatmap(correlation_matrix, annot=True, cmap='coolwarm', fmt=".2f", linewidths=.5)
plt.title('Correlation Matrix')
plt.show()
```

## Vistualizations

To explore the visualization options I used a fictitious data file of the popularity of different ice cream flavors. 
In this small project I built line charts, bar charts, stacked bar charts, scatter plots, histogram, boxplot, area charts and pie charts. 

📘 **Libraries/Packages Used:**
- Pandas
- Numpy
- Matplotlib.pyplot

✍️ **Code Example:**

```python
df.plot(kind='line', title = 'Ice cream ratings', xlabel = 'Daily ratings', ylabel = 'Scores')
```

```python
df.plot.scatter(x  = 'Texture Rating', y = 'Overall Rating', s = 250, c = 'green')
```
  

Feel free to explore each project by navigating into their respective directories. If you find any issues or have suggestions for improvement, please feel free to open an issue or submit a pull request. Contributions are highly welcome.

Thanks for reading 💙
