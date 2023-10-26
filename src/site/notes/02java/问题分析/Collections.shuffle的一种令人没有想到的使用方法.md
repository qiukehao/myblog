---
{"dg-publish":true,"permalink":"/02java//collections-shuffle/","dgPassFrontmatter":true}
---

```java
public class W1随机点名器 {
    public static void main(String[] args) {
        ArrayList<String> list = new ArrayList<>();
        Collections.addAll(list, "范闲", "范建", "范统", "杜子腾", "杜琦燕", "宋合泛", "侯笼藤", "朱益群", "朱穆朗玛峰", "袁明媛");
        // 思路一：
        Random r = new Random();
		System.out.println("随机点到的是");
		int n = r.nextInt(list.size());
		System.out.println(list.get(n));
        System.out.println("点名结束");
        // 思路二 打乱集合,在获取第一个
        Collections.shuffle(list);
        System.out.println(list.get(0));
		System.out.println("点名结束");
		
        input.close();
    }
}
```

我们在进行随机抽取元素的时候如果你的元素并不要求有序性, 我们可以通过这个 shuffle 来进行打乱集合之后在对这个数组进行抽取.