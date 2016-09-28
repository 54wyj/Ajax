# Ajax
原生Ajax的学习笔记
- 表单：数据的提交
action : 数据提交的地址，默认是当前页面
method : 数据提交的方式，默认是get方式
1.get 字符串类型，把数据名称和数据值用=连接，如果有多个的话，那么他会把多个数据组合用&进行连接，然后把数据放到url?后面传到指定页面
      url长度限制的原因，不要通过get方式传递过多的数据。
2.post 多类型，通过请求头传递，理论上上传大小无限制，
enctype : 提交的数据格式，默认application/x-www-form-urlencoded

window.onload = function() {
	var oBtn = document.getElementById('btn');
	oBtn.onclick = function() {
		//打开浏览器
		/*
			1.创建一个ajax对象
				ie6以下new ActiveXObject('Microsoft.XMLHTTP')
		*/
		var xhr = null;
		/*if (window.XMLHttpRequest) {
			xhr = new XMLHttpRequest();
		} else {
			xhr = new ActiveXObject('Microsoft.XMLHTTP');
		}*/
		try {
			xhr = new XMLHttpRequest();
		} catch (e) {
			xhr = new ActiveXObject('Microsoft.XMLHTTP');
		}
		
		//alert( xhr.readyState );
		//在地址栏输入地址
		/*
			open方法
			参数
				1.打开方式
				2.地址
				3.是否异步
					异步:非阻塞 前面的代码不会影响后面代码的执行
					同步:阻塞 前面的代码会影响后面代码的执行
		*/
		xhr.open('get','1.txt',true);
		//提交 发送请求
		//alert(1);
		xhr.send();
		//alert( xhr.readyState );
		//alert(1)
		//alert( xhr.responseText );
		//等待服务器返回内容
		/*
			readyState : ajax工作状态
			responseText : ajax请求返回的内容就被存放到这个属性下面
			on readystate change : 当readyState改变的时候触发
			status : 服务器状态，http状态码
		*/
		xhr.onreadystatechange = function() {
			if ( xhr.readyState == 4 ) {
				if ( xhr.status == 200 ) {
					alert( xhr.responseText );
				} else {
					alert('出错了,Err：' + xhr.status);
				}
			}
		}
	}
