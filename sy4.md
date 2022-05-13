# 实验4 Jupyter Notebook实践

## 简单尝试


```python
print("黄浩好帅！！")
```

    黄浩好帅！！
    


```python
import numpy as np
def square(x):
    return x*x
```


```python
x = np.random.randint(1,10)
y = square(x)
print("x = %d ,y = %d " %(x,y))
```

    x = 4 ,y = 16 
    

## 简单的例子：选择排序算法

定义selection_sort函数实现排序算法


```python
def selection_sort(arr):
    for i in range(len(arr)-1):
        min_index=i
        for j in range(i+1,len(arr)):
             if(arr[min_index]>arr[j]):
                    min_index=j    #找到最小值的索引
        temp=arr[min_index]
        arr[min_index]=arr[i]
        arr[i]=temp
        
    print(arr);
```

test函数测试，调用selection_sort函数进行排序


```python
array = [3,5,9,4,11,15,46,1]
print(array)
selection_sort(array)
```

    [3, 5, 9, 4, 11, 15, 46, 1]
    [1, 3, 4, 5, 9, 11, 15, 46]
    

## 世界500强数据分析

### 设置

导入相关工具库


```python
%matplotlib inline
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
```

加载数据库


```python
df = pd.read_csv('fortune500.csv')
```

### 检查数据集


```python
df.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Year</th>
      <th>Rank</th>
      <th>Company</th>
      <th>Revenue (in millions)</th>
      <th>Profit (in millions)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1955</td>
      <td>1</td>
      <td>General Motors</td>
      <td>9823.5</td>
      <td>806</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1955</td>
      <td>2</td>
      <td>Exxon Mobil</td>
      <td>5661.4</td>
      <td>584.8</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1955</td>
      <td>3</td>
      <td>U.S. Steel</td>
      <td>3250.4</td>
      <td>195.4</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1955</td>
      <td>4</td>
      <td>General Electric</td>
      <td>2959.1</td>
      <td>212.6</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1955</td>
      <td>5</td>
      <td>Esmark</td>
      <td>2510.8</td>
      <td>19.1</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.tail()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Year</th>
      <th>Rank</th>
      <th>Company</th>
      <th>Revenue (in millions)</th>
      <th>Profit (in millions)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>25495</th>
      <td>2005</td>
      <td>496</td>
      <td>Wm. Wrigley Jr.</td>
      <td>3648.6</td>
      <td>493</td>
    </tr>
    <tr>
      <th>25496</th>
      <td>2005</td>
      <td>497</td>
      <td>Peabody Energy</td>
      <td>3631.6</td>
      <td>175.4</td>
    </tr>
    <tr>
      <th>25497</th>
      <td>2005</td>
      <td>498</td>
      <td>Wendy's International</td>
      <td>3630.4</td>
      <td>57.8</td>
    </tr>
    <tr>
      <th>25498</th>
      <td>2005</td>
      <td>499</td>
      <td>Kindred Healthcare</td>
      <td>3616.6</td>
      <td>70.6</td>
    </tr>
    <tr>
      <th>25499</th>
      <td>2005</td>
      <td>500</td>
      <td>Cincinnati Financial</td>
      <td>3614.0</td>
      <td>584</td>
    </tr>
  </tbody>
</table>
</div>



对数据属性列进行重命名，以便在后续访问


```python
df.columns = ['year', 'rank', 'company', 'revenue', 'profit']
```

检查数据条目是否加载完整


```python
len(df)
```




    25500



检查属性列的类型


```python
df.dtypes
```




    year         int64
    rank         int64
    company     object
    revenue    float64
    profit      object
    dtype: object



利用正则表达式进行检查


```python
non_numberic_profits = df.profit.str.contains('[^0-9.-]')
df.loc[non_numberic_profits].head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>year</th>
      <th>rank</th>
      <th>company</th>
      <th>revenue</th>
      <th>profit</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>228</th>
      <td>1955</td>
      <td>229</td>
      <td>Norton</td>
      <td>135.0</td>
      <td>N.A.</td>
    </tr>
    <tr>
      <th>290</th>
      <td>1955</td>
      <td>291</td>
      <td>Schlitz Brewing</td>
      <td>100.0</td>
      <td>N.A.</td>
    </tr>
    <tr>
      <th>294</th>
      <td>1955</td>
      <td>295</td>
      <td>Pacific Vegetable Oil</td>
      <td>97.9</td>
      <td>N.A.</td>
    </tr>
    <tr>
      <th>296</th>
      <td>1955</td>
      <td>297</td>
      <td>Liebmann Breweries</td>
      <td>96.0</td>
      <td>N.A.</td>
    </tr>
    <tr>
      <th>352</th>
      <td>1955</td>
      <td>353</td>
      <td>Minneapolis-Moline</td>
      <td>77.4</td>
      <td>N.A.</td>
    </tr>
  </tbody>
</table>
</div>



统计有多少字符串数据


```python
len(df.profit[non_numberic_profits])
```




    369



利用直方图显示按照年份的分布情况


```python
bin_sizes, _, _ = plt.hist(df.year[non_numberic_profits], bins=range(1955, 2006))
```


    
![png](https://github.com/ddandll/xmsj3/blob/main/%E5%AE%9E%E9%AA%8C4/output_30_0.png?raw=true)
    


可见，单独年份这样的记录数都少于25条，即少于4%的比例。这在可以接受的范围内，因此删除这些记录。


```python
df = df.loc[~non_numberic_profits]
df.profit = df.profit.apply(pd.to_numeric)
```

再次检查数据记录的条目数。


```python
len(df)
```




    25131



以年分组绘制平均利润和收入。首先定义变量和方法。


```python
df.dtypes
```




    year         int64
    rank         int64
    company     object
    revenue    float64
    profit     float64
    dtype: object



可见，上述操作已经达到清洗无效数据记录的效果。

### 使用matplotlib进行绘图

以年分组绘制平均利润和收入。首先定义变量和方法。


```python
group_by_year = df.loc[:, ['year', 'revenue', 'profit']].groupby('year')
avgs = group_by_year.mean()
x = avgs.index
y1 = avgs.profit
def plot(x, y, ax, title, y_label):
    ax.set_title(title)
    ax.set_ylabel(y_label)
    ax.plot(x, y)
    ax.margins(x=0, y=0)
```

开始绘图


```python
fig, ax = plt.subplots()
plot(x, y1, ax, 'Increase in mean Fortune 500 company profits from 1955 to 2005', 'Profit (millions)')
```


    
![png](https://github.com/ddandll/xmsj3/blob/main/%E5%AE%9E%E9%AA%8C4/output_42_0.png?raw=true)
    


收入曲线


```python
y2 = avgs.revenue
fig, ax = plt.subplots()
plot(x, y2, ax, 'Increase in mean Fortune 500 company revenues from 1955 to 2005', 'Revenue (millions)')
```


    
![png](https://github.com/ddandll/xmsj3/blob/main/%E5%AE%9E%E9%AA%8C4/output_44_0.png?raw=true)
    


公司收入曲线并没有出现急剧下降，可能是由于财务会计的处理。对数据结果进行标准差处理。


```python
def plot_with_std(x, y, stds, ax, title, y_label):
    ax.fill_between(x, y - stds, y + stds, alpha=0.2)
    plot(x, y, ax, title, y_label)
fig, (ax1, ax2) = plt.subplots(ncols=2)
title = 'Increase in mean and std Fortune 500 company %s from 1955 to 2005'
stds1 = group_by_year.std().profit.values
stds2 = group_by_year.std().revenue.values
plot_with_std(x, y1.values, stds1, ax1, title % 'profits', 'Profit (millions)')
plot_with_std(x, y2.values, stds2, ax2, title % 'revenues', 'Revenue (millions)')
fig.set_size_inches(14, 4)
fig.tight_layout()
```


    
![png](https://github.com/ddandll/xmsj3/blob/main/%E5%AE%9E%E9%AA%8C4/output_46_0.png?raw=true)
    


## Jupyter Notebook 扩展工具

Anaconda Navigator中启动命令行终端

![3](https://github.com/ddandll/xmsj3/blob/main/%E5%AE%9E%E9%AA%8C4/3.png?raw=true)

在终端中一次输入4条命令，等待完成

pip install jupyter_contrib_nbextensions

jupyter contrib nbextension install --user

pip install jupyter_nbextensions_configurator

jupyter nbextensions_configurator enable --user

完成后，重启Jupyter Notebook，可看到

![2](https://github.com/ddandll/xmsj3/blob/main/%E5%AE%9E%E9%AA%8C4/2.png?raw=true)

点击Nbextensions标签，勾选Hinterland：

![1](https://github.com/ddandll/xmsj3/blob/main/%E5%AE%9E%E9%AA%8C4/1.png?raw=true)

接下来可以在notebook进行验证，Tab健可以补全或者选择代码。
