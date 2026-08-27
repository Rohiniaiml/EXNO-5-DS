# EXNO-5-DS-DATA VISUALIZATION USING MATPLOT LIBRARY

# Aim:
  To Perform Data Visualization using matplot python library for the given datas.

# EXPLANATION:
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

# Algorithm:
STEP 1:Include the necessary Library.

STEP 2:Read the given Data.

STEP 3:Apply data visualization techniques to identify the patterns of the data.

STEP 4:Apply the various data visualization tools wherever necessary.

STEP 5:Include Necessary parameters in each functions.

# Coding and Output:
```
import pandas as pd


data = {
    'Month': ['jan', 'feb', 'mar', 'apr', 'jun'],
    'Laptop': [150, 165, 170, 185, 200],
    'Mobiles': [200, 300, 400, 500, 600],
    'Tabs': [100, 200, 300, 400, 500],
    'Accessories': [80, 90, 100, 110, 120]
}
df = pd.DataFrame(data)
print(df)

import matplotlib.pyplot as plt
plt.plot(df['Month'], df['Mobiles'])
plt.title('Monthly Mobiles Sales')
plt.xlabel('Month')
plt.ylabel('Number of Units Sold')
plt.show()


product_sales = {
    'Laptop': df['Laptop'].sum(),
    'Mobiles': df['Mobiles'].sum(),
    'Tabs': df['Tabs'].sum(),
    'Accessories': df['Accessories'].sum()
}
products = list(product_sales.keys())
sales = list(product_sales.values())
colors = ['skyblue', 'yellow', 'lightgreen', 'pink']
plt.barh(products, sales, color=colors)
plt.title('Total Sales by Product')
plt.xlabel('Product')
plt.ylabel('Total Units Sold')
plt.show()

plt.bar(df['Month'], df['Laptop'], label='Laptop')
plt.bar(df['Month'], df['Mobiles'],
        bottom=df['Laptop'], label='Mobiles')
plt.title('Monthly Sales by Product')
plt.xlabel('Month')
plt.ylabel('Units Sold')
plt.legend()
plt.show()

plt.fill_between(df['Month'], df['Laptop'], alpha=0.5, color='red')
plt.title('Laptop Sales Trend')
plt.xlabel('Month')
plt.ylabel('Units Sold')
plt.show()


plt.stackplot(
    df['Month'],
    df['Laptop'],
    df['Mobiles'],
    df['Tabs'],
    df['Accessories'],
    labels=['Laptop', 'Mobiles', 'Tabs', 'Accessories']
)
plt.title('Monthly Product Sales')
plt.xlabel('Month')
plt.ylabel('Units Sold')
plt.legend(loc='upper left')
plt.show()

plt.hist(order_sales,bins=8)
plt.title('Distribution of order sales')
plt.xlabel('units per orders')
plt.ylabel('Frequency')
plt.show()
plt.hist(df['Laptop'], bins=5)
plt.title('Distribution of Laptop Sales')
plt.xlabel('Number of Laptops Sold')
plt.ylabel('Frequency')
plt.show()
plt.hist(df['Laptop' ], bins=5, alpha=0.5, label='Laptop')
plt.hist(df['Mobiles'], bins=5, alpha=0.5, label='Mobile')
plt.hist(df['Tabs'], bins=5, alpha=0.5, label='Tablet')

plt. title('Distribution of Product Sales')
plt.xlabel('Units Sold')
plt.ylabel('Frequency')

plt.legend()
plt.show()
plt.pie(
    sales,
    labels=products,
    autopct='%1.1f%%'
)
plt.title('Product Sales Distribution')
plt.show()
import pandas as pd
import matplotlib.pyplot as plt
data = {
'Product': ['Laptop', 'Mobiles', 'Tabs', 'Accessories'],
'Sales': [280, 380, 180, 280]
}
df = pd.DataFrame(data)
explode = [0, 0.1, 0, 0]
colors = ['gold', 'skyblue', 'lightgreen', 'orange']
plt.pie(
    df['Sales'],
    labels=df['Product'],
    colors=colors,
    autopct='%1.1f%%',
    explode=explode,
    startangle=90,
    shadow=True,
    textprops={'fontsize': 11},
    wedgeprops={'width': 0.8}
)
plt.title('Product Sales Distribution')
plt.axis('equal')
plt.show()
labels = 'Python', 'C++', 'Ruby', 'Java'
sizes = [215, 130, 245, 210]
colors = ['gold', 'yellowgreen', 'lightcoral', 'lightskyblue']
explode = (0, 0.4, 0, 0.5)
plt.pie(sizes, explode=explode, labels=labels, colors=colors,
autopct='%1.1f%%', shadow=True)
plt.axis('equal')
plt. show()
import pandas as pd
import matplotlib.pyplot as plt
data = {
    'Product': ['Laptop', 'Mobiles', 'Tabs', 'Accessories'],
    'Sales': [120, 150, 180, 200]
}
df = pd.DataFrame(data)
df
sales = [120, 135, 150, 145, 170, 180,
190, 175, 200, 220, 250, 280,
310, 125, 140, 155, 165, 185]
plt.boxplot(sales)
plt.title('Distribution of Sales')
plt.ylabel('Sales')
plt.show()
plt.boxplot(sales)
plt.title('Sales Distribution with outlier')
plt.ylabel('Sales')
plt.show()
laptop = [120, 135, 158, 145, 178, 180, 198, 175, 200]
mobiles = [200, 220, 210, 240, 260, 270, 298, 300, 310]
tabs = [80, 90, 180, 95, 118, 128, 138, 125, 140]
plt.boxplot(
    [laptop, mobiles, tabs],
    labels=['Laptop', 'Mobiles', 'Tabs']
)
plt.title('Sales Distribution by Product')
plt.xlabel('Product')
plt.ylabel('Units Sold')
plt.show()

plt.boxplot(
    [laptop, mobiles, tabs],
    labels=['Laptop', 'Mobilez', 'Tabs'],
    vert=False
)
plt.title('Sales Distribution by Product')
plt.xlabel('Units Sold')
plt.show()
plt.boxplot(
    sales,
    showmeans=True
)
plt.title('Sales Distribution')
plt.ylabel('Sales')
plt.show()
import pandas as pd

data = {
    'Month': ['jan', 'feb', 'mar', 'apr', 'jun'],
    'Laptop': [150, 165, 170, 185, 200],
    'Mobiles': [200, 300, 400, 500, 600],
    'Tabs': [100, 200, 300, 400, 500],
    'Accessories': [80, 90, 100, 110, 120]
}
df = pd.DataFrame(data)

plt.scatter(df['Laptop'], df['Mobiles'])
for i in range(len(df)):
  plt.annotate(
      df['Month'][i],
       (df['Laptop'][i], df['Mobiles'][i])
  )

plt.title('Laptop Sales vs Mobile Sales')
plt.xlabel('Laptop Sales')
plt.ylabel('Mobile Sales')

plt.show()
plt.scatter(
    df['Month'],
    df['Laptop'],
       color='blue',
       s=100,
       label='Laptop'
)
plt.scatter(
    df['Month'],
    df['Mobiles'],
       color='red',
       s=100,
       label='pobile'
)
plt.xlabel('Month')
plt.ylabel('Sales')
plt.title('Leptop vs Mobile Monthly Sales')
plt.legend()
plt.grid(True)
plt.show()
```
<img width="643" height="157" alt="image" src="https://github.com/user-attachments/assets/f2d10330-98f8-4397-a044-a8be09749bca" />
<img width="937" height="568" alt="image" src="https://github.com/user-attachments/assets/88c96a5d-e429-469c-96d6-2521f871ab85" />
<img width="1080" height="576" alt="image" src="https://github.com/user-attachments/assets/c6246070-d296-461b-90d7-80cea6d914bf" />
<img width="1078" height="567" alt="image" src="https://github.com/user-attachments/assets/f7a7aaaf-533b-40b5-8a55-1db9074e91e6" />
<img width="1080" height="572" alt="image" src="https://github.com/user-attachments/assets/664ef462-cf79-4671-8f2a-484b0f5a35bc" />

<img width="897" height="573" alt="image" src="https://github.com/user-attachments/assets/efbbcb8b-b714-4991-b668-1c1a60181078" />
<img width="928" height="573" alt="image" src="https://github.com/user-attachments/assets/60525994-5c15-4874-972d-4efaa6541bad" />
<img width="928" height="573" alt="image" src="https://github.com/user-attachments/assets/be3723a6-b327-4056-b2d5-ded164727fc8" />
<img width="949" height="564" alt="image" src="https://github.com/user-attachments/assets/7c762262-033f-49aa-a366-41fe0cb50537" />
<img width="850" height="533" alt="image" src="https://github.com/user-attachments/assets/7c79799d-e329-47a2-af44-93fcc63d42e1" />
<img width="1065" height="529" alt="image" src="https://github.com/user-attachments/assets/81e03cba-0816-4837-bf01-41fc656fc6bc" />
<img width="1020" height="523" alt="image" src="https://github.com/user-attachments/assets/25dd613e-665b-4ed4-8162-b603e83134ab" />
<img width="418" height="220" alt="image" src="https://github.com/user-attachments/assets/d1d448c9-2e2d-47e2-be53-c98f0de58e4b" />
<img width="1100" height="601" alt="image" src="https://github.com/user-attachments/assets/70b612cc-82bb-4d64-9ecc-9761bedf86ec" />
<img width="953" height="564" alt="image" src="https://github.com/user-attachments/assets/4f0174b7-d0c6-499e-a49b-940547a70733" />
<img width="1057" height="573" alt="image" src="https://github.com/user-attachments/assets/5c25c4f7-a767-4af0-bb18-897a968d430d" />
<img width="996" height="604" alt="image" src="https://github.com/user-attachments/assets/86590237-5992-4958-8842-7257657ecbab" />
<img width="1120" height="595" alt="image" src="https://github.com/user-attachments/assets/7854ffb0-4140-4a86-b991-2df1c579c2f9" />
<img width="1067" height="587" alt="image" src="https://github.com/user-attachments/assets/68ee7bd3-d61f-4272-8818-e2e97d2ac79a" />
<img width="1047" height="592" alt="image" src="https://github.com/user-attachments/assets/02a240f8-81a3-4f1b-aee2-d30a8c3aa1f7" />

# Result:
 Include your result here
