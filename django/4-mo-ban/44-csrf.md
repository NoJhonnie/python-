##CSRF
CSRF全称cross site request forgery，伪造跨站请求。在网站上存在利用链接、表单或JavaScript等，登陆过的留在浏览器中的用户信息实施跨站攻击。而CSRF的防止在django中也有应用：
* 1.在setting.py中启用csrf的中间件
* 2.在csrf.html中添加标签
```
<body>
{% csrf_token %}
</body>
```
这个时候就能实现跨站请求被拒绝了。
而对于我们需要的视图不需要保护时，我们可以使用装饰器csrf_exempt
```
from django.views.decorators.csrf import csrf_exempt

@csrf_exempt
def csrf2(request):
    return render(request,'booktest/csrf2.html')
```
csrf的保护原理实质上是在本地浏览器中添加cookie信息，从而实现保护，但该方法并不完全安全。