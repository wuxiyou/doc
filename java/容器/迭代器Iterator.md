#Iterator 接口定义了如下方法
1. boolean hasNext(): 判断是否有元素没有被遍历
2. Object Next(): 返回游标当前位置的元素并将游标移动到下一个位置
3. void remove(): 删除游标左边的元素，在next()之后，该操作只能执行一次

~~~
Set<String> set = new HashSet();
Iterator iterator = set.iterator();
while(iterator.hasNext()) {
    String str = iterator.next();
    System.out.println(str);
}

#for 方式
for(Iterator iterator = set.iterator();iterator.hasNext();) {
    String str = iterator.next();
    System.out.println(str);
}
~~~