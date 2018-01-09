pip freeze>requirements

# Tutorial 1

pip install django
pip install djangorestframework
pip install pygments
pip install httpie


# Tutorial 4

## 使用API进行身份验证
因为我们现在有一组API的权限，如果我们要编辑任何片段，我们需要验证我们的请求。我们还没有__设置任何身份验证类__，所以默认值现在被应用，哪些是`SessionAuthentication`和 `BasicAuthentication`。 

添加权限验证后，非owner(自己创建的对象)不再有  PUT, DELETE 方法。

admin/admin123
hello/hello123

http -a admin:admin123 http://127.0.0.1:8000/snippets/
http -a hello:hello123 http://127.0.0.1:8000/snippets/

http POST http://127.0.0.1:8000/snippets/ code="print 789"
http -a admin:admin123 POST http://127.0.0.1:8000/snippets/ code="print 789"
http -a hello:hello123 POST http://127.0.0.1:8000/snippets/ code="print hello3"
