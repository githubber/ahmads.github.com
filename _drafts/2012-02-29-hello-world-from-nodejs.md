---
title :  أهلا بالعالم، من Node.js
layout: post
---
### ما هي Node.js؟

هي منصة لكتابة تطبيقات الخوادم (Servers) بلغة JavaScript.

### لماذا Node.js؟

تتميز Node.js بأنها غير متزامنة (Asynchronous I/O) أي أن المعالجة لا
تتوقف على حساب الإدخال والإخراج. وهي (event-driven)

### من أين أيدأ؟


### أهلُا بالعالم

{% highlight javascript %}
console.log("Hello World");
{% endhighlight %}
كان هذا سهلًا و.. حسنًا مملًا

### أهلًا بالعالم، من HTTP
{% highlight javascript %}
// طلب http moudle  
var http = require('http');  

// Configure our HTTP server to respond with Hello World to all requests.
var server = http.createServer(function (request, response) {
	response.writeHead(200, {"Content-Type": "text/plain"});
	response.end("Hello World\n");
});

// Listen on port 8000, IP defaults to 127.0.0.1
server.listen(8000);

// Put a friendly message on the terminal
console.log("Server running at http://127.0.0.1:8000/");
{% endhighlight %}