# Collection
> 含义: 表示一组对象，是对象的集合

1. Collection： 定义了存取一组对象的方法，其子类接口Set和List分别定义了实现方式
* Set ： 无序不可重复，重复即被覆盖
> HashSet，底层实现是HashMap 实现的，即数组加链表结构

> TreeSet
* List: 有序可重复
* ArrayList：底层实现是数组，所以查询快，修改，插入，删除慢
* LinkedList:  底层实现是链表，查询慢，其他快
* Vector: 线程安全的，效率低

2. Map : 键值对，键值不可重复
> Map 的实现类 HashMap, TreeMap， HashTable【线程安全】