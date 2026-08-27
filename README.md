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
import pandas as pd
data={
    'month':['jan','feb','mar','apr','may','jun','july','aug','sep','oct','nov','dec'],
    'laptop':[120,135,150,145,170,180,190,175,200,220,250,280],
    'mobile':[200,220,210,240,260,270,290,300,310,330,350,380],
    'tablet':[80,90,100,95,110,120,130,125,140,150,160,180],
    'accessorices':[150,160,170,180,190,200,210,220,230,240,260,280]

}
df=pd.DataFrame(data)
df
```

<img width="952" height="972" alt="image" src="https://github.com/user-attachments/assets/714b62d4-d239-4b37-987f-e0f68ed429f2" />

```
import matplotlib.pyplot as plt
plt.plot(df['month'],df['laptop'])
plt.title('monthly laptop sales')
plt.xlabel('month')
plt.ylabel('number of units sold')
plt.show()
```

<img width="820" height="751" alt="image" src="https://github.com/user-attachments/assets/adaa7cb8-ed66-447c-8891-dd05d70b1763" />

```
plt.plot(df['month'],df['laptop'],marker='o',label='laptop')
plt.plot(df['month'],df['mobile'],marker='o',label='mobile')
plt.title('monthly product sales')
plt.xlabel('month')
plt.ylabel('units sold')
plt.legend()
plt.grid()
plt.show()

```

<img width="945" height="966" alt="image" src="https://github.com/user-attachments/assets/b6a27550-
9d7a-4552-bb3b-200f00447144" />

```
product_sales={
    'laptop':df['laptop'].sum(),
    'mobile':df['mobile'].sum(),
    'tablet':df['tablet'].sum(),
    'accessorices':df['accessorices'].sum()
}
products=list(product_sales.keys())
sales=list(product_sales.values())
colors=['skyblue','yellow','lightgreen','pink']
plt.bar(products,sales,color=colors)
plt.title('total sales by product')
plt.xlabel('product')
plt.ylabel('total units sold')
plt.show()
```

<img width="950" height="963" alt="image" src="https://github.com/user-attachments/assets/3187567b-a372-4533-80cb-053f4493f1a7" />

```
colors = ['green', 'red', 'blue', 'yellow']
plt.barh(products, sales, color=colors)
plt.title('Total Sales by Product')
plt.xlabel('Total Units Sold')
plt.ylabel('Product')
plt.show()
```

<img width="948" height="867" alt="image" src="https://github.com/user-attachments/assets/e22f6f9a-a35d-442f-9ec1-b73a0ad91104" />

```
plt.fill_between(df['month'],df['laptop'],alpha=0.5,color="red")
plt.title('laptop sales trend')
plt.xlabel('month')
plt.ylabel('units sold')
plt.show()
```

<img width="940" height="895" alt="image" src="https://github.com/user-attachments/assets/ea8dc58d-9567-4854-8f94-cf1e8e9bbd83" />

```
plt.stackplot(
    df['month'],
    df['laptop'],
    df['mobile'],
    df['tablet'],
    df['accessorices'],
    labels=['laptop','mobile','tablet','accessorices']
)
plt.title('product sales trend')
plt.xlabel('month')
plt.ylabel('units sold')
plt.legend(loc='upper left')
plt.show()
```
<img width="947" height="957" alt="image" src="https://github.com/user-attachments/assets/4a267639-b7ea-438a-8415-a5244ae5d478" />

```
plt.bar(df['month'],df['laptop'],label='laptop')
plt.bar(df['month'],df['mobile'],bottom=df['laptop'],label='mobile')
plt.title('monthly sales by product')
plt.xlabel('month')
plt.ylabel('units sold')
plt.legend()
plt.show()
```

<img width="950" height="962" alt="image" src="https://github.com/user-attachments/assets/75d563ee-9358-4711-ba26-e57e4f017fd4" />

```
order_sales = [
    10, 12, 15, 18, 20, 22, 25, 28,
    30, 32, 35, 35, 38, 40, 42, 45,
    48, 50, 52, 55, 60, 65, 70, 75,
    80, 85, 90, 100
]

plt.hist(order_sales, bins=8)
plt.title('Distribution of Order Sales')
plt.xlabel('Units per Order')
plt.ylabel('Frequency')
plt.show()
```

<img width="948" height="971" alt="image" src="https://github.com/user-attachments/assets/c54d35fa-7ae2-4309-a5d7-15f2f048b15c" />

```
plt.hist(df['laptop'], bins=5)
plt.title('Distribution of Laptop Sales')
plt.xlabel('Number of Laptops Sold')
plt.ylabel('Frequency')
plt.show()
```

<img width="963" height="936" alt="image" src="https://github.com/user-attachments/assets/1450fa05-8d6b-485d-8d5d-ad89eafdcb89" />

```
plt.hist(df['laptop'],bins=5,alpha=0.5,label='laptop')
plt.hist(df['mobile'],bins=5,alpha=0.5,label='mobile')
plt.hist(df['tablet'],bins=5,alpha=0.5,label='tablet')
plt.title('distribution of sales by product')
plt.xlabel('units sold')
plt.ylabel('frequency')
plt.legend()
plt.show()
```

<img width="941" height="962" alt="image" src="https://github.com/user-attachments/assets/6bdc3da9-e415-49f4-b2e7-e2f1052175d7" />

```
plt.pie(
    sales,
    labels=products,
    autopct='%1.1f%%'

)
plt.title('sales distribution by product')
plt.show()
```

<img width="940" height="935" alt="image" src="https://github.com/user-attachments/assets/bc58e564-75ac-4389-bca1-19081d4e7bf2" />

```
import pandas as pd
import matplotlib.pyplot as plt

data = {
    'product': ['laptop', 'mobile', 'tablet', 'accessories'],
    'sales': [280, 380, 180, 280]
}

df = pd.DataFrame(data)

explode = [0, 0.1, 0, 0]
colors = ['gold', 'skyblue', 'lightgreen', 'orange']

plt.pie(
    df['sales'],
    labels=df['product'],
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
```

<img width="937" height="957" alt="image" src="https://github.com/user-attachments/assets/049d619b-f94a-4efd-881e-bf17adafca44" />

```
# Data to plot
labels = ['Python', 'C++', 'Ruby', 'Java']
sizes = [215, 130, 245, 210]
colors = ['gold', 'yellowgreen', 'lightcoral', 'lightskyblue']
explode = (0, 0.4, 0, 0.5)

# Plot
plt.pie(
    sizes,
    explode=explode,
    labels=labels,
    colors=colors,
    autopct='%1.1f%%',
    shadow=True
)

plt.axis('equal')
plt.show()
```

<img width="945" height="966" alt="image" src="https://github.com/user-attachments/assets/c2c60408-1ff1-4675-bc45-5d061fc9947c" />

```
import pandas as pd
import matplotlib.pyplot as plt

data_product_sales = {
    'Product': ['Laptop', 'Mobile', 'Tablet', 'Accessories'],
    'Sales': [120, 150, 180, 200]
}

df_product_sales = pd.DataFrame(data_product_sales)

df_product_sales

sales = [
    120, 135, 150, 145, 170, 180,
    190, 175, 200, 220, 250, 280,
    310, 125, 140, 155, 165, 185
]

plt.boxplot(sales)
plt.title('Distribution of Sales')
plt.ylabel('Sales')
plt.show()
```

<img width="947" height="912" alt="image" src="https://github.com/user-attachments/assets/da9c8e4c-422c-4072-b7c1-633852088bb2" />

```
laptop = [120, 135, 150, 145, 170, 180, 190, 175, 200]
mobile = [200, 220, 210, 240, 270, 290, 300, 310, 280]
tablet = [80, 90, 100, 95, 110, 120, 130, 125, 140]

plt.boxplot(
    [laptop, mobile, tablet],
    labels=['laptop', 'mobile', 'tablet']
)

plt.title('Sales Distribution by Product')
plt.xlabel('Product')
plt.ylabel('Units Sold')
plt.show()
```

<img width="947" height="967" alt="image" src="https://github.com/user-attachments/assets/17bc64f0-563a-4aff-971e-8f2518f1bd89" />

```
plt.boxplot(sales,
            showmeans=True
)
plt.title('sales distribution by product')
plt.ylabel('sales')
plt.show()
```

<img width="946" height="968" alt="image" src="https://github.com/user-attachments/assets/d2e7202e-2205-48b8-b181-ec67a2b7edb5" />

```
import pandas as pd
import matplotlib.pyplot as plt

data={
    'month':['jan','feb','mar','apr','may','jun','july','aug','sep','oct','nov','dec'],
    'laptop':[120,135,150,145,170,180,190,175,200,220,250,280],
    'mobile':[200,220,210,240,260,270,290,300,310,330,350,380],
    'tablet':[80,90,100,95,110,120,130,125,140,150,160,180],
    'accessorices':[150,160,170,180,190,200,210,220,230,240,260,280]

}
df=pd.DataFrame(data)

plt.scatter(
    df['month'],
    df['laptop'],
    color='blue',
    s=100,
    label='laptop'
)

plt.scatter(
    df['month'],
    df['mobile'],
    color='red',
    s=100,
    label='mobile'
)

plt.xlabel('month')
plt.ylabel('sales')
plt.title('laptop vs mobile monthly sales')
plt.legend()
plt.grid(True)
plt.show()
```

<img width="947" height="946" alt="image" src="https://github.com/user-attachments/assets/32122cfc-9f5e-4bc5-b673-714125a43fed" />

```
plt.scatter(
    df['month'],
    df['laptop'],
    color='blue',
    s=100,
    label='laptop'
)

plt.scatter(
    df['month'],
    df['mobile'],
    color='red',
    s=100,
    label='mobile'
)

plt.xlabel('month')
plt.ylabel('sales')
plt.title('laptop vs mobile monthly sales')
plt.legend()
plt.grid(True)
plt.show()
```

<img width="932" height="972" alt="image" src="https://github.com/user-attachments/assets/e6d74842-bb45-4d76-aa27-c838cf185eac" />

```
x_values=[0,1,2,3,4,5]
y_values=[0,1,4,9,16,25]
plt.plot(x_values,y_values)
plt.show
```

<img width="927" height="972" alt="image" src="https://github.com/user-attachments/assets/18acea42-fdb9-4c6c-adf4-768f71810b39" />

```
import matplotlib.pyplot as plt
x=[1,2,3]
y=[2,4,1]
plt.plot(x,y)
plt.xlabel('x-axis')
plt.ylabel('y-axis')
plt.title('my first graph!')
plt.show()
```

<img width="947" height="948" alt="image" src="https://github.com/user-attachments/assets/3849acaa-4905-424a-87a0-6d98e3f8c39f" />

```
x1=[1,2,3]
y1=[2,4,1]
plt.plot(x1,y1,label="line 1")
x2=[1,2,3]
y2=[4,1,3]
plt.plot(x2,y2,label="line 2")
plt.xlabel('x-axis')
plt.ylabel('y-axis')
plt.title('two or more lines on same graph!')
plt.legend()
plt.show()
```

<img width="946" height="987" alt="image" src="https://github.com/user-attachments/assets/a3037b7c-015b-4e3c-870c-217f286b788f" />

```
x=[1,2,3,4,5,6]
y=[2,4,1,5,2,6]
plt.plot(x,y,color='green',linestyle='dashed',linewidth=3,marker='o',markerfacecolor='blue',markersize=12)
plt.ylim(1,8)
plt.xlim(1,8)
plt.xlabel('x-axis')
plt.ylabel('y-axis')
plt.title('line graph')
plt.show()
```

<img width="945" height="988" alt="image" src="https://github.com/user-attachments/assets/b41858fa-fb06-44b0-ab60-723228d36a12" />

```
yield_apples=[0.895,0.91,0.919,0.926,0.929,0.931]
plt.plot(yield_apples)
```

<img width="951" height="835" alt="image" src="https://github.com/user-attachments/assets/88a621bb-2bad-4f08-ac48-dfc0a1c98eb3" />

```
years=[2010,2011,2012,2013,2014,2015]
yield_apples=[0.895,0.91,0.919,0.926,0.929,0.931]
plt.plot(years,yield_apples)
```

<img width="940" height="961" alt="image" src="https://github.com/user-attachments/assets/a3270e51-981e-402f-a753-3169873de219" />

```
import matplotlib.pyplot as plt
years=range(2000,2012)
apples=[0.895,0.91,0.919,0.926,0.929,0.931,0.934,0.936,0.937,0.9375,0.9372,0.939]
oranges=[0.962,0.941,0.930,0.923,0.918,0.908,0.907,0.904,0.901,0.898,0.9,0.896]
plt.plot(years, apples)
plt.plot(years,oranges)

plt.xlabel('year')
plt.ylabel('yield (tons per hectare)');
```

<img width="950" height="967" alt="image" src="https://github.com/user-attachments/assets/a2584429-2717-4814-9cd2-ae06b02cfa45" />

```
plt.plot(years,apples)
plt.plot(years,oranges)
plt.xlabel('years')
plt.ylabel('yield (tons per hectare)')
plt.legend(['Apples','Oranges']);
```


<img width="938" height="946" alt="image" src="https://github.com/user-attachments/assets/6d9b1e0a-9247-43d8-a5f9-c667e398423c" />

```
plt.plot(years,apples)
plt.xlabel('year')
plt.ylabel('yield (tons per hectare)');
```

<img width="942" height="827" alt="image" src="https://github.com/user-attachments/assets/b0ac8dee-bf35-45a5-8c77-67ea85ed94f4" />

```
plt.figure(figsize=(12,6))
plt.plot(years,oranges,marker='o')
plt.title("yield of Oranges (tons per hectare)");
```

<img width="945" height="938" alt="image" src="https://github.com/user-attachments/assets/6f872b23-c452-4198-83a1-9be80dbd99ca" />

```
import matplotlib.pyplot as plt

years=range(2000,2012)
apples=[0.895,0.91,0.919,0.926,0.929,0.931,0.934,0.936,0.937,0.9375,0.9372,0.939]
oranges=[0.962,0.941,0.930,0.923,0.918,0.908,0.907,0.904,0.901,0.898,0.9,0.896]

plt.plot(years, apples, marker='o')
plt.plot(years, oranges, marker='x')

plt.xlabel('Year')
plt.ylabel('Yield (tons per hectare)')

plt.title('Crop Yields in Kanto')
plt.legend(['Apples', 'Oranges'])
```

<img width="942" height="950" alt="image" src="https://github.com/user-attachments/assets/291d6875-a1ec-45b2-a3bb-5149ed9c6e03" />

```
import matplotlib.pyplot as plt
x_values=[0,1,2,3,4,5]
y_values=[0,1,4,9,16,25]
plt.scatter(x_values,y_values,s=30,color="blue")
plt.show()
```

<img width="943" height="807" alt="image" src="https://github.com/user-attachments/assets/06e5beb4-8e5d-4666-8cc0-522ee516c0a2" />

```
import matplotlib.pyplot as plt

# x-axis values
x = [1,2,3,4,5,6,7,8,9,10]

# y-axis values
y = [2,4,5,7,6,8,9,11,12,12]

# plotting points as a scatter plot
plt.scatter(x, y, label="stars", color="green", marker="*", s=30)

# x-axis label
plt.xlabel('x - axis')

# frequency label
plt.ylabel('y - axis')

# plot title
plt.title('My scatter plot!')

# showing legend
plt.legend()

# function to show the plot
plt.show()
```

<img width="932" height="882" alt="image" src="https://github.com/user-attachments/assets/712ba1c2-3777-4a08-8323-26608abfc75e" />

```
import matplotlib.pyplot as plt
import numpy as np
import pandas as pd

x = np.arange(0,10)
y = np.arange(11,21)

x
y
```

<img width="946" height="580" alt="image" src="https://github.com/user-attachments/assets/4d6726fe-7180-445a-a16d-ec745064213d" />

```
plt.scatter(x,y,c='r')
plt.xlabel('X axis')
plt.ylabel('Y axis')
plt.title('Graph in 2D')
plt.savefig('Test.png')
```

<img width="945" height="881" alt="image" src="https://github.com/user-attachments/assets/61283bbd-2f1e-402f-bd52-14a059f2c412" />

```
plt.plot(x,y,'g*',linestyle='dashed',linewidth=2,markersize=12)
plt.xlabel('x axis')
plt.ylabel('y axis')
plt.title('Graph in 2D')

```

<img width="947" height="982" alt="image" src="https://github.com/user-attachments/assets/9c4a3dcc-4e50-4375-8227-2c5587cd9b1f" />

```
plt.subplot(2,2,1)
plt.plot(x,y,'r--')
plt.subplot(2,2,2)
plt.plot(y,x,'g*--')
plt.subplot(2,2,3)
plt.plot(x,x,'bo')
plt.subplot(2,2,4)
plt.plot(y,y,'go')
```

<img width="932" height="931" alt="image" src="https://github.com/user-attachments/assets/e16a9d91-07fa-4bcf-8b8e-76f7117084ae" />

```
x=np.arange(0,4*np.pi,0.1)
y=np.sin(x)
plt.title("sine wave form")
plt.plot(x,y)
plt.show()
```

<img width="930" height="957" alt="image" src="https://github.com/user-attachments/assets/2e3b9d01-672c-41bb-bba5-e3ef451bbd0b" />

```
import matplotlib.pyplot as plt

x = [1, 2, 3, 4, 5]
y1 = [1, 3, 2, 4, 3]
y2 = [2, 4, 3, 5, 4]

plt.fill_between(x, y1, color='blue', alpha=0.5)
plt.fill_between(x, y2, color='green', alpha=0.5)
plt.title('Fill Between Example')
plt.xlabel('X-axis')
plt.ylabel('Y-axis')
plt.show()
```

<img width="937" height="962" alt="image" src="https://github.com/user-attachments/assets/f7d60e65-114e-4059-bcd0-81c921f13fec" />

```
import matplotlib.pyplot as plt

x = [1, 2, 3, 4, 5]
y1 = [1, 3, 2, 4, 3]
y2 = [2, 4, 3, 5, 4]
y3 = [3, 2, 4, 1, 5]

plt.stackplot(x, y1, y2, y3,
              labels=['Line 1', 'Line 2', 'Line 3', 'Line 4'])

plt.legend(loc='upper left')
plt.title('Stacked Line Chart')
plt.xlabel('X-axis')
plt.ylabel('Y-axis')
plt.show()
```

<img width="945" height="976" alt="image" src="https://github.com/user-attachments/assets/32bf8c2f-640c-4f32-8bbc-2c38960f65ce" />

```
import numpy as np
import matplotlib.pyplot as plt
from scipy.interpolate import make_interp_spline

x = np.array([1,2,3,4,5,6,7,8,9,10])
y = np.array([2,4,5,7,8,8,9,10,11,12])

spl = make_interp_spline(x, y)

x_smooth = np.linspace(x.min(), x.max(), 100)
y_smooth = spl(x_smooth)

plt.plot(x, y, 'o', label='data')
plt.plot(x_smooth, y_smooth, '-', label='spline')
plt.legend()
plt.show()
```

<img width="945" height="891" alt="image" src="https://github.com/user-attachments/assets/889c7a4a-4ce8-4bc8-be72-27ee34ebfbc9" />

```
import pandas as pd
import matplotlib.pyplot as plt

data={
    'month':['jan','feb','mar','apr','may','jun','july','aug','sep','oct','nov','dec'],
    'laptop':[120,135,150,145,170,180,190,175,200,220,250,280],
    'mobile':[200,220,210,240,260,270,290,300,310,330,350,380],
    'tablet':[80,90,100,95,110,120,130,125,140,150,160,180],
    'accessorices':[150,160,170,180,190,200,210,220,230,240,260,280]

}
df=pd.DataFrame(data)

product_sales={
    'laptop':df['laptop'].sum(),
    'mobile':df['mobile'].sum(),
    'tablet':df['tablet'].sum(),
    'accessorices':df['accessorices'].sum()
}
products = list(product_sales.keys())
sales = list(product_sales.values())

plt.barh(products, sales, color="yellowgreen")
plt.title('Total Sales by Product')
plt.xlabel('Total Units Sold')
plt.ylabel('Product')
plt.show()
```

<img width="942" height="847" alt="image" src="https://github.com/user-attachments/assets/4a12dcf1-85ed-4b48-afc4-43d67f781849" />

```
import matplotlib.pyplot as plt

values = [5, 6, 3, 7, 2]
names = ["A", "B", "C", "D", "E"]

plt.bar(names, values, color="green")
plt.show()
```

<img width="945" height="887" alt="image" src="https://github.com/user-attachments/assets/9a53e1ca-cc79-4d22-a99d-0c7b93f6c2e4" />

```
import matplotlib.pyplot as plt

height = [10, 24, 36, 40, 5]
names = ['one', 'two', 'three', 'four', 'five']

plt.bar(names, height, width=0.8)

plt.xlabel('X-axis')
plt.ylabel('Y-axis')
plt.title('My bar chart!')

plt.show()
```

<img width="950" height="957" alt="Screenshot 2026-08-27 182844" src="https://github.com/user-attachments/assets/464905e8-4474-47a4-96b3-e9e7ffe89496" />


```
x = [2, 8, 10]
y = [11, 16, 9]

x2 = [3, 9, 11]
y2 = [6, 15, 7]

plt.bar(x, y, color='r')
plt.bar(x2, y2, color='g')

plt.title('Bar graph')
plt.ylabel('Y axis')
plt.xlabel('X axis')

plt.show()
```
<img width="940" height="912" alt="Screenshot 2026-08-27 182906" src="https://github.com/user-attachments/assets/2da239e8-5b5e-4c87-b535-7e773420e4aa" />



```
import matplotlib.pyplot as plt

# frequencies
ages = [2, 5, 70, 40, 30, 45, 50, 45, 43, 40, 44, 60, 7, 13, 57, 18, 90, 77, 32, 21, 20, 40]

# setting the ranges and no. of intervals
range = (0, 100)
bins = 10

# plotting a histogram
plt.hist(ages, bins, range, color='green', histtype='bar', rwidth=0.8)

# x-axis label
plt.xlabel('age')

# frequency label
plt.ylabel('No. of people')

# plot title
plt.title('My histogram')

# function to show the plot
plt.show()
```

<img width="950" height="941" alt="Screenshot 2026-08-27 182935" src="https://github.com/user-attachments/assets/88e0210e-cec5-4cbd-ac0d-86af17086d23" />

```
import matplotlib.pyplot as plt

# generate fake data
x = [2,1,6,4,2,4,8,9,4,2,4,10,6,4,5,7,7,3,2,7,5,3,5,9,2,1]

# plot for a histogram
plt.hist(x, bins=10, color='blue', alpha=0.5)

plt.show()
```

<img width="920" height="932" alt="image" src="https://github.com/user-attachments/assets/72641bd7-ecdb-421a-b80b-ddc2b4fd15a8" />

```
import matplotlib.pyplot as plt
import numpy as np

np.random.seed(0)

data = np.random.normal(loc=0, scale=1, size=100)

fig, ax = plt.subplots()

ax.boxplot(data)

ax.set_xlabel('Data')
ax.set_ylabel('Values')
ax.set_title('Box Plot')

plt.show()
```

<img width="938" height="902" alt="image" src="https://github.com/user-attachments/assets/9cc7c22a-10a2-4200-851a-42235beddb2a" />

```
import matplotlib.pyplot as plt

# defining labels
activities = ['eat', 'sleep', 'work', 'play']

# portion covered by each label
slices = [3, 7, 8, 6]

# color for each label
colors = ['r', 'y', 'g', 'b']

# plotting the pie chart
plt.pie(slices, labels=activities, colors=colors,
        startangle=90, shadow=True,
        explode=(0, 0, 0.1, 0),
        radius=1.2,
        autopct='%1.1f%%')

# plotting legend
plt.legend()

# showing the plot
plt.show()
```

<img width="943" height="941" alt="image" src="https://github.com/user-attachments/assets/645e92df-ca0a-4e3b-844a-1452d484bf10" />

```
import matplotlib.pyplot as plt

# Data to plot
labels = ['Python', 'C++', 'Ruby', 'Java']
sizes = [215, 130, 245, 210]
colors = ['gold', 'yellowgreen', 'lightcoral', 'lightskyblue']
explode = (0, 0.4, 0, 0.5)

# Plot
plt.pie(sizes, explode=explode, labels=labels, colors=colors,
        autopct='%1.1f%%', shadow=True)

plt.axis('equal')

plt.show()
```

<img width="942" height="891" alt="image" src="https://github.com/user-attachments/assets/dc8d67f8-b7c6-474f-b1d5-8db515e37bfb" />



# Result:
 Include your result here
