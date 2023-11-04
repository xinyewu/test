# Spring Boot整合Freemarker（基础）

1.添加依赖

```java
<!--freemarker-->
<dependency>
  <groupId>org.springframework.boot</groupId>
  <artifactId>spring-boot-starter-freemarker</artifactId>
</dependency>
```

2.添加配置文件

```java
#freemarker
  freemarker:
    #模板后缀
    suffix: .ftl
    #文档类型
    content-type: text/html
    #页面编码
    charset: UTF-8
    #页面缓存  关闭
    cache: false
      #模板加载路径
#      template-load-path: classpath:/templates/
```

3. 编写测试类

```java
@Controller
public class TestController {
    @RequestMapping("/freemarker")
    public String index(Map<String,Object>map) {
        map.put("name","ls");
        return "freemarker";
    }
```

4.在resources目录下，建立templates目录，创建以freemarker开头 .ftl结尾的文件

![image-20231104185942805](C:\Users\xinye\AppData\Roaming\Typora\typora-user-images\image-20231104185942805.png)

5.文件写对应的显示内容

```htaccess
你好，${name}
```

6.成功

![image-20231104190028389](C:\Users\xinye\AppData\Roaming\Typora\typora-user-images\image-20231104190028389.png)

7.freemarker结合页面语法，语法需要自己去了解

------



# Spring Boot 整合Thymeleaf（基础）

1.导入依赖

```java
<!--Thymeleaf-->
<dependency>
  <groupId>org.springframework.boot</groupId>
  <artifactId>spring-boot-starter-thymeleaf</artifactId>
</dependency>
```

2.添加配置文件

```java
#Thymeleaf
  thymeleaf:
    #后缀
    suffix: .html
    mode: HTML5
    #页面编码
    charset: UTF-8
    #页面缓存  关闭
    cache: false
      #模板加载路径
#      template-load-path: classpath:/templates/
```

3.编写测试类

```java
@RequestMapping("/thymeleaf")
public String list(Model model){
  model.addAttribute("hello","hello thymeleaf");
  return "thymeleaf";
}
```

4.在resources目录下，建立templates目录，创建以thymeleaf开头 .html结尾的文件

![img](file:///C:\Users\xinye\AppData\Local\Temp\ksohtml704\wps1.jpg) 

5.在thymeleaf.html中写freemarker简单语句 

![img](file:///C:\Users\xinye\AppData\Local\Temp\ksohtml704\wps2.jpg) 

6.成功

![img](file:///C:\Users\xinye\AppData\Local\Temp\ksohtml704\wps3.jpg) 

 

7.thymeleaf结合页面语法，需要自己去了解

