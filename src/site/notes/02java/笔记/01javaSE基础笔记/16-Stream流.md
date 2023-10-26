---
{"dg-publish":true,"permalink":"/02java//01java-se/16-stream/","dgPassFrontmatter":true}
---

# Stream

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202308041622189.png)

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202308041623850.png)

处理方法就是
1. 获取流
2. 中间处理
3. 流的终结

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202308041625556.png)

1. filter是限制条件
2. foreach是进行遍历


## 常见数据类型获取Stream的方法
### list
```java
        List<String> list = new ArrayList<>();
        Collections.addAll(list,"刘德华","古天乐","德玛西亚","艾欧尼亚","德云色");
        Stream<String> stream = list.stream();
        stream.filter(s->s.contains("德")).forEach(System.out::println);
```

### set
```java
Set<String> set = new HashSet<>();  
Collections.addAll(set,"刘德华","古天乐","德玛西亚","艾欧尼亚","德云色");  
Stream<String> stream1 = set.stream();  
stream1.filter(s->s.length()==3).forEach(System.out::println);
```

### map
```java
Map<String, Double> map = new HashMap<>();  
map.put("古力娜扎",172.3);  
map.put("迪丽热巴",168.3);  
map.put("马尔扎哈",166.3);  
map.put("卡尔扎巴",168.3);  
//由于map集合不属于collection,所以我们不能直接使用这个Stream流  
Set<String> set1 = map.keySet();  
Stream<String> stream2 = set1.stream();  
Collection<Double> values = map.values();  
Stream<Double> stream3 = values.stream();
Set<Map.Entry<String, Double>> entries = map.entrySet();  
Stream<Map.Entry<String, Double>> stream4 = entries.stream();  
stream4.filter(s->s.getKey().contains("巴")).forEach(s-> System.out.println(s));
```

### 数组
```java
String[] views = {"五台山","玄武湖","故宫","蔡明园","夫子庙","灵隐寺","西湖"};  
Stream<String> stream5 = Arrays.stream(views);  
Stream<String> views1 = Stream.of(views);
```

## 常见的中间方法

间方法指的是调用完成后会返回新的Stream流，可以继续使用(支持链式编程)

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202308041649649.png)


比较难以理解的是
sort
对于我们重写的这个sort方法,当我们简略缩写的时候我们
`stream.filter(s->s>30).sorted((Double o1, Double o2)-> (int)(o2-o1)).forEach(s-> System.out.println(s));`

这个return是不在使用的

distinct,如果是我们自己自定义的对象,如果我们向去除重复的元素我们可以通过重写对象中的equals和hashcode方法来进行书写代码

map
map就是让这个流变成它给出的元素的流,比如说一个对象流我们只需要用其中一个属性值,那么我们就可以用这个

## 常用的终结方法
![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202308041805513.png)

max和min都可以重写匿名内部类
最后这个返回的是optionnal类型的对象,因此我们并不能直接获取,我们要在其后面再加入这个get来实现
```java
        Student student = students.stream().min(((o1, o2) -> o2.getAge() - o1.getAge())).get();
        System.out.println(student);
```

**收集Stream流：就是把Stream流操作后的结果转回到集合或者数组中去返回。**

就是我们处理的结果,传递到这个集合和数组容器之中去

Stream流：方便操作集合/数组的手段；   集合/数组：才是开发中的目的。

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202308041811288.png)

```java
List<Student> collect = students.stream().filter(s -> s.getAge() > 30).collect(Collectors.toList());  
System.out.println(collect);
```

![image.png](https://qkh-markdown-1316031240.cos.ap-nanjing.myqcloud.com/obsidian/202308041812016.png)
## 流的注意事项
流只能收集一次,不能重复使用