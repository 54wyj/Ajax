# Ajax
原生Ajax的学习笔记
- 表单：数据的提交
action : 数据提交的地址，默认是当前页面
method : 数据提交的方式，默认是get方式
1.get 字符串类型，把数据名称和数据值用=连接，如果有多个的话，那么他会把多个数据组合用&进行连接，然后把数据放到url?后面传到指定页面
      url长度限制的原因，不要通过get方式传递过多的数据。
2.post 多类型，通过请求头传递，理论上上传大小无限制，
enctype : 提交的数据格式，默认application/x-www-form-urlencoded
