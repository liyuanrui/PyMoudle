
### 程序文件test.py
```
from fabric.api import cd,run,env
from fabric.colors import *

env.hosts=['pi@127.0.0.1:22']
env.password='rpyc1234'
#env.passwords={'pi@127.0.0.1:22':'rpyc1234'}

def hello(i):
    print 'hello %s'%i

def t():
    run('pwd')
    run('cd lr')
    run('pwd')
    print green('ok')
```

### shell调用
```
$ fab -f test.py hello:lr
$ fab -f test.py t
```