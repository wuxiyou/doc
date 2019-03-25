# maven 环境搭建
> 含义：依赖管理工具

> 下载安装包 解压，配置系统环境变量

> mvn 的目录结构
~~~
    src
        -main
            -java
                -package
        -test
            -java
                -package
                
~~~
> mvn 项目初始化命令  mvn compile

> mvn 项目打包命令    mvn package

> mvn test 测试

> mvn clean 清除已打包的jar包

> mvn install 将jar 安装到本地仓库

> 创建目录的两种方式
>> mvn archetype:generate
>> mvn archetype:generate -DgroupId=组织名,公司网址的反写+项目名 -DartifactId=项目名称 -Dversion=版本号 -Dpackage=代码所在的报名

# maven 镜像仓库
> 国内镜像仓库地址: http://maven.net.cn/content/groups/pulibc

> 阿里云仓库地址： http://maven.aliyun.com/nexus/content/groups/public

> 本地仓库调整《默认是在C盘的》

>>  标签 localRepos



#pom.xml 常用元素介绍
1. dependencies -> dependency
#打包
> mvn clean install -Dmaven.test.skip=true