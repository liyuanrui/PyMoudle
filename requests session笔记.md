
### session
```
import requests
s=requests.session()
login_data={'username':'lr','userpass':'123456'}
headers={}

#登录
s.post('https://wodemo.com/login',data=login_data)
h=s.get('https://wodemo.com')
print h.text
```