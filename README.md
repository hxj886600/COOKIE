## 使用方法 

1.新添加一个会话 cookie： 

~~~
$.cookie('the_cookie', 'the_value');
~~~
注：当没有指明 cookie有效时间时，所创建的cookie有效期默认到用户关闭浏览器为止，所以被称为 

“会话cookie（session cookie）”。 

2.创建一个cookie并设置有效时间为 7天: 

~~~
$.cookie('the_cookie', 'the_value', { expires: 7 });
~~~
注：当指明了cookie有效时间时，所创建的cookie被称为“持久 cookie （persistent cookie）”。 

3.创建一个cookie并设置 cookie的有效路径： 

~~~
$.cookie('the_cookie', 'the_value', { expires: 7, path: '/' });
~~~
注：在默认情况下，只有设置 cookie的网页才能读取该 cookie。如果想让一个页面读取另一个页面设 

置的cookie，必须设置cookie的路径。cookie的路径用于设置能够读取 cookie的顶级目录。将这 

个路径设置为网站的根目录，可以让所有网页都能互相读取 cookie （一般不要这样设置，防止出现冲突） 。 

4.读取cookie： 
~~~
$.cookie('the_cookie'); // cookie存在 => 'the_value' 
$.cookie('not_existing'); // cookie不存在 => null
~~~
5.删除cookie，通过传递null作为cookie的值即可： 

~~~
$.cookie('the_cookie', null);
~~~
1).expires: 365 

定义cookie的有效时间，值可以是一个数字（从创建cookie时算起，以天为单位）或一个Date 对 

象。如果省略，那么创建的cookie是会话cookie，将在用户退出浏览器时被删除。 

2).path: '/' 

默认情况：只有设置cookie的网页才能读取该cookie。 

定义cookie的有效路径。默认情况下， 该参数的值为创建 cookie 的网页所在路径（标准浏览器的行为） 。 

如果你想在整个网站中访问这个cookie需要这样设置有效路径：path: '/'。如果你想删除一个定义 

了有效路径的 cookie，你需要在调用函数时包含这个路径:$.cookie('the_cookie', null, 

{ path: '/' });。 domain: 'example.com' 

默认值：创建 cookie的网页所拥有的域名。 

3).secure: true 

默认值：false。如果为true，cookie的传输需要使用安全协议（HTTPS）。 

4).raw: true 

默认值：false。 

默认情况下，读取和写入 cookie 的时候自动进行编码和解码（使用encodeURIComponent 编码， 

decodeURIComponent 解码）。要关闭这个功能设置 raw: true 即可。