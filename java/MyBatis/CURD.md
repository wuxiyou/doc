#参数输入
1. 输入参数：parameterType
> 类型为 简单类型(8个基本类型+String)
~~~
#{任意值}  会预处理， 自动给String类型加上 '',防止sql注入

${value}, 只能是具体值,原样输出,适合动态sql，需手动加 '' value 是固定的
eg: select * from user order by ${value} desc

~~~

> 类型为对象
~~~
#{属性名}
${属性名}
~~~


#返回参数类型
1. 简单类型(8个基本类型+String)
2. 返回对象<javaBeen>
> resultType[javaBean, HashMap, List]

> resultMap[当数据库的字段跟实体类的属性不一致：类型，名字]
>> 字段名跟属性名不一致
>>> resultMap

>>> resultType+HashMap
~~~

~~~


#输入为属性，集合，数组
~~~
动态sql

输入参数为数组时：
<where>
    关键字是array
</where>
~~~

#关联查询
1. 一对一


2. foreach 的主要用在构建 in 条件中
~~~
foreach元素的属性主要有item，index，collection，open，separator，close。

　　(1) item：表示集合中每一个元素进行迭代时的别名，

　　(2) index：指定一个名字，用于表示在迭代过程中，每次迭代到的位置，

　　(3) open：表示该语句以什么开始，

　　(4) separator：表示在每次进行迭代之间以什么符号作为分隔符，

　　(5) close：表示以什么结束，

　　(6) collection：属性是在使用foreach的时候最关键的也是最容易出错的，该属性是必须指定的，但是在不同情况下，该属性的值是不一样的，主要有一下3种情况： 

　　　　①如果传入的是单参数且参数类型是一个List的时候，collection属性值为list .

　　　　②如果传入的是单参数且参数类型是一个array数组的时候，collection的属性值为array .

　　　　③如果传入的参数是多个的时候，我们就需要把它们封装成一个Map了，当然单参数也可以封装成map，实际上如果你在传入参数的时候，在MyBatis里面也是会把它封装成一个Map的，map的key就是参数名，所以这个时候collection属性值就是传入的List或array对象在自己封装的map里面的key.
~~~

#延时加载[懒加载，按需加载 也就是 分步加载]
~~~
1. 一对多的情况下， 先查询主表，再查询关联表
~~~