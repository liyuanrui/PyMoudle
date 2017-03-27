
### 在models.py里新建数据库
```
from django.db import models
class Talkuser(models.Model):
    username=models.CharField('用户名',max_length=30)
    password=models.CharField('密码',max_length=30)
```

### 在models.py里设置后台
```
from django.contrib import admin
class TalkuserAdmin(admin.ModelAdmin):
    list_display=('username','password')

admin.site.register(Talkuser,TalkuserAdmin)
```

### 不用django中数据库的query api，像连接其他数据库那样用execute操作
```
from django.db import connection
cu.connection.cursor()
```

