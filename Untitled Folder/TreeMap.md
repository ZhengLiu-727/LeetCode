## TreeMap 的构建



如果不指定自定义的比较器Comparator，那么插入的对象必须实现Comparable接口，元素按照实现此接口的compareTo()方法去排序。如果指定了自定义的比较器Comparator，优先使用Comparator去对元素进行排序。比较规则决定了元素是否可以重复，以及元素的排序结果

```java
TreeMap<Integer, String> treemap = new TreeMap<>();

// populating tree map
treemap.put(2, "two");
treemap.put(1, "one");
treemap.put(3, "three");
treemap.put(4, "six");
treemap.put(5, "five");

System.out.println("Value is: "+ treemap.floorKey(4));//输出小于等于4对最大对key
System.out.println("Value is: "+ treemap.floorEntry(2));//输出小于等于2对最大key=value
System.out.println("Value is: "+ treemap.firstEntry());//输出最小对key=value

Value is: 4

Value is: 2=two

Value is: 1=one
```





```java
//最小的
firstKey()

//最大的
lastKey()

//大于等于这个key的第一个元素，可以想成天花板及以上
ceilingEntry(k key);

//大于等于这个key的键值
ceilingKey(k key);

//小于等于这个key的第一个元素，可以想成地板及以下
ceilingEntry(k key);

//大于这个键值的元素
higherEntry

//大于这个key的键
higherKey

//返回集合中的第一个元素
firstEntry

//返回最后一个
lastEntry
```



### containsKey()

时间复杂度 $ O(logN) $

### put()

时间复杂度 $ O(logN) $

### get()

时间复杂度 $ O(logN) $

### remove()

时间复杂度 $ O(logN) $

Object firstKey()

它返回树映射中当前的第一个（最少）键。

Object lastKey()

它返回树映射中当前的最后一个（最大）键。

Object ceilingKey(Object key)

返回大于或等于给定键的最小键，如果没有这样的键则返回null。

Object higherKey(Object key)

返回严格大于指定键的最小键。