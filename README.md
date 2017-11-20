Design_part
使用handler实现用户的权限登录
运用Spring Boot+mybatis
运用jdk动态代理，即java spring的AOP原理实现用户权限。
几张数据库表如下：
uer：
id name password salt headurl
ticket表：
id userid ticket expires status

User Dao：
分析用户就查找，更新，insert 操作然后写入相应的@insert sql语句。 
ticket Dao
考虑到用户设置过期时间，所以要一个更新操作，产生用户ticket的insert操作
Ticket 字符串是存在与cookies里面的，到时候用 HttpServletResponse response 就可将带有ticket的cookie 加入到浏览器cookie中
权限登录：
继承的是HandlerInterceptor，实现三个方法。 咱们用hostholder即一个localthread来储存一个用户。这样这个用户的状态就被记录下来了。之后可以调用这个用户来实现
权限登陆
