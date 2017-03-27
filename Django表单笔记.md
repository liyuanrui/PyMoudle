
### 设计表单
```
from django import forms

class RegisterForm(forms.Form):
    username=forms.CharField(label='用户名')    
    email=forms.EmailField(label='电子邮箱')
    password1=forms.CharField(label='密码',widget=forms.PasswordInput())
    password2=forms.CharField(label='确认密码',widget=forms.PasswordInput())
```

### 传表单到模版
```
def register(request):
    if request.method='POST':
        a=1
    else:
        form=RegisterForm()
        return render(request,'register.py',{'form':form})
```

### 模版显示
```
<form method="POST" action="/register">
{% for i in form %}
{{i.label}}<br />{{i}}<br />
{% endfor %}
<input type="submit" name="submit" value="注册" />
</form>
```
用for来循环传过来的表单，i.label显示表单的label，这样做的好处是显示的好看，一行一行的

### 接收post
```
def register(request):
    if request.method=='POST':
        form=RegisterForm(request.POST)
        if form.is_valid():
            username=form.cleaned_data['username']
            email=form.cleaned_data['email']
            password1=form.cleaned_data['password1']
            password2=form.cleaned_data['password2']
```
