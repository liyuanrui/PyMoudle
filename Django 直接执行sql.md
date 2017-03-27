```
from django.db import connection

cu=connection.cursor()

connection.connection.commit()
```

django每执行一次就会关闭连接，所以每次都要制定cu