
### 1、安装pip2pi
```
pip install pip2pi==0.7.0rc1
```

### 2、建立存放pip包的目录
```
mkdir pypi
```

### 3、配置要同步的源
```
mkdir ~/.pip
vi ~/.pip/pip.conf

[global]
index-url = http://pypi.douban.com/simple
```

### 4、单个软件包同步
```
pip2tgz pypi name==version
比如 pip2tgz pypi xpinyin==0.5.4
```

### 5、批量同步
```
pip2tgz pypi -r ./requirements.txt

wsgiref==0.1.2
xlrd==0.9.4
xlwt==1.0.0
```

### 6、同步完成后建立索引
```
dir2pi pypi
```

### 客户端使用
```
pip install xpinyin -i http://192.168.9.59:8000/simple --trusted-host
```

### 常用参数
```
--index-url=http://pypi.douban.com --trusted-host
```
