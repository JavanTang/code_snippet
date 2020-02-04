```python
# panda导入数据: 读取csv数据, 数据清洗, 转化独热码
column_names = ['MPG','Cylinders','Displacement','Horsepower','Weight',
                'Acceleration', 'Model Year', 'Origin']
raw_dataset = pd.read_csv(dataset_path(数据路径), names=column_names,
                      na_values = "?", comment='\t',
                      sep=" ", skipinitialspace=True)

dataset = raw_dataset.copy()
dataset.tail()

# 数据清洗
dataset.isna().sum()
dataset = dataset.dropna() # 清理这些na值的数据

# 转化独热码
"Origin" 列实际代表分类，而不仅仅是一个数字。所以把它转换为独热码（one-hot）：

origin = dataset.pop('Origin')

dataset['USA'] = (origin == 1)*1.0
dataset['Europe'] = (origin == 2)*1.0
dataset['Japan'] = (origin == 3)*1.0
dataset.tail()


```



