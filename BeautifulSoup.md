
### 1、实例化
```
from bs4 import BeautifulSoup
s=BeautifulSoup('http://lr.cool','parser')
```

### 2、输出标签中属性
```
print s.a
print s.a['href']
```

### 3、搜索
```
s.find_all('p',class_='class',id='id',text='textttttt')
```
