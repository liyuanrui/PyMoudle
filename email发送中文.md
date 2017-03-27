
### 发送中文邮件
```
import smtplib
from email.header import Header
from email.mime.text import MIMEText



msg=MIMEText(u'老司机','plain','utf-8')
msg['From']=Header(u'LR<tdwwlr@163.com>','utf-8')
msg['To']=Header(u'272352297@qq.com','utf-8')
msg['Subject']=Header(u'这是标题,快开车','utf-8')

smtp=smtplib.SMTP()
smtp.connect('smtp.163.com')
smtp.login('tdwwlr','123456')

smtp.sendmail('tdwwlr@163.com','272352297@qq.com',msg.as_string())
```