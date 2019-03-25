> 参考链接:https://segmentfault.com/a/1190000011633180
> 
1. 备份之前的版本
~~~
cp -P /usr/local/php  /usr/local/php70
~~~

2. 查看php70的配置
~~~
php -i | grep configure
替换之前获得的configure 命令
php -i | grep configure | sed -e "s/Configure Command => //; s/' //g"
~~~
3. 开始安装php

4. 填坑【升级，配置当然和以前一样就好】
~~~
cp /usr/local/php70/etc/php.ini /usr/local/php/etc/php.ini
cp /usr/local/php70/etc/php-fpm.conf /usr/local/php/etc/php-fpm.conf
cp /usr/local/php70/etc/php-fpm.d/www.conf /usr/local/php/etc/php-fpm.d/www.conf
~~~

5.扩展的坑
~~~
查看安装了哪些扩展
#  /usr/local/php/bin/php-config --extension-dir
#  ls /usr/local/php7/lib/php/extensions/no-debug-non-zts-20160303
~~~

