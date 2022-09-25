# 编写路由

----

路由是浏览器输入url，在Django服务器响应url的转发中心。路由都写在urls文件里，它将浏览器输入的url映射到相应的业务处理逻辑也就是视图。简单的urls编写方法

## <project_name>/<project_name>/urls.py中

```python
from <app_name> import view
urlpatterns=[
	path('admin',admin.site.urls),
	path('<route_name>/',view.<app_name>)
]
```

## <prject_name>/<app_name>/view.py中

```python
from django.shortcuts import render #
def <app_name>():
	return render(request,'<html_name>.html')
```

# 修改setting

----

![setting中TEMPLATES](https://img-blog.csdnimg.cn/20190730154519177.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dvaml1Y2FvbmVu,size_16,color_FFFFFF,t_70)

# 编写html

----

## mkdir templates

## 在templates中编写<html_name>.html

# 静态文件

----

## mkdir static

## static 创建css和js文件夹 并放入静态css和js

## 对setting做修改

```python
STATIC_URL='/static/'
STATICFILES_DIRS=[
	os.path.join(BASE_DIR,'static')
]
```

