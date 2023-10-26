---
{"dg-publish":true,"permalink":"/05leecode//offer15/","dgPassFrontmatter":true}
---


```java
package heima_study.day3;

import java.util.Scanner;

public class 替换空格剑指offer {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        String  s = input.nextLine();
        String temp = replaceSpace(s);
        System.out.println(temp);
        input.close();
    }
    public static String replaceSpace(String s) {
        //char[] ch = s.toCharArray();
        StringBuilder sb = new StringBuilder();
        /* for(int i=0;i<length;i++){
            if(ch[i]==' '){
                ch[i]='%20';  //%20不是一个字符//长度不能变化的情况下,肯定是用集合了
            }
        } */
        for(int i=0;i<s.length();i++){
            if(s.charAt(i)==' '){
                sb.append("20%");
            }else{
                sb.append(s.charAt(i));
            }
        }
        return sb.toString();
    }
}

```