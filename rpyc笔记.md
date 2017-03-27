
### server:
```
from rpyc import Service
from rpyc.utils.server import ThreadedServer
class Test(Service):
    def exposed_test(self):
        return 'hello world'
s=ThreadedServer(Test,port=1024,auto_register=False)
s.start()
```

### client:
```
import rpyc
c=rpyc.connect('192.168.1.75',1024)
print c.root.test()
c.close()
```
