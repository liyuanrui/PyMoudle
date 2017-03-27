
需要安装python-dateutil库
```
>>>from dateutil.relativedelta import relativedelta
>>>import datetime
>>>
>>>now=datetime.date(2016,9,12)
>>>print now+relativedelta(months=1)
>>>print now+relativedelta(years=1)
>>>print now+relativedelta(days=1)
>>>
>>>
```