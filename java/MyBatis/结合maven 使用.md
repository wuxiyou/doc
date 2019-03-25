1. 配置pom.xml
~~~
<dependency>
      <groupId>org.mybatis</groupId>
      <artifactId>mybatis</artifactId>
      <version>3.4.4</version>
    </dependency>
    
    #指定数据库
    <dependency>
          <groupId>mysql</groupId>
          <artifactId>mysql-connector-java</artifactId>
          <version>5.1.39</version>
        </dependency>
~~~

2.配置全局加载文件
~~~
在main 目录下 创建 resource 文件夹 将其设置为全局目录
【intelliJ->选中目录右击->Mark Diretory as -> Source Root】

添加mybatis 配置文件
创建conf.xml 此文件的目的是加载 数据链接信息和 映射文件
结构说明：
<configuration>
    <!--加载properties 结尾的文件 如数据配置信息等文件-->
    <properties  resource = "" />  
    <!-- 全局配置信息标签 -->
    <settings>
        <!--设置日志监测-->
        <setting name="logImpl" value="LOG4J"/>
    </settings>
    <!-- 环境变量配置 包含数据库连接信息 -->
    <environments>
    </environments>
    
    
    <mappers>
        <!--逐个加载映射文件-->
        <mapper  resource= "" />
        
        <!-- 批量加载映射文件 -->
        <package name="dao"/>
    </mappers>
    
</configuration>

配置数据链接信息

创建db.propeties 文件 以键值对方式 设置链接信息

~~~

3.每个表基本映射成一个mapper 文件

4.#{} 和 ${} 的区别
~~~
#{} 
1. 是一个占位符,sql 语句会进行预处理操作
   eg： select * from user where id = ${id}
2. 如果传入参数是 8种基本数据类型 + string 类型, 会自动给 传入参数加上 双引号
3. 当传入参数是对象时，#{属性名} 大括号必须是属性名

${} sql 语句不会进行预处理操作

1. 如果传入参数是 8种基本数据类型 + string 时 需手动加上引号，大括号里面固定 #{value}
2. 当传入参数为 对象时， ${属性名} 大括号里面 必须是属性名

~~~

5.传入参数区分
~~~
1. 8种基本类型 + string
2. 对象
3. HashMap

当传入参数是 HashMap 时 ${键名}或 #{键名}
~~~

6.返回参数
~~~
1. void
2. 对象
3. HashMap
~~~

7.关联查询
~~~
1. 一对一
2. 一对多
3. 多对多
~~~


8.延时查询【分步查询】