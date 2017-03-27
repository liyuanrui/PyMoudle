
```
>>>datetime.datetime.today()     显示当前时间
>>>datetime.datetime.now()       显示当前时间
>>>datetime.date(2016,9,12)      生成指定日期时间，不含时间
>>>datetime.datetime(2016,9,12)  生成指定日期时间，含时间
>>>
>>>间隔天数
>>>now1=datetime.date(2016,9,24)
>>>now2=datetime.date(2016,9,20)
>>>print (now1-now2).days
>>>
>>>格式化时间
>>>now1.strftime('%Y-%m-%d')
>>>
>>>天数相加
>>>a=datetime.timedelta(days=4)
>>>b=datetime.date.today()
>>>c=b+a
>>>
>>>
```
