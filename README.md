# aiqiyi-Java-Algorithm
## 爱奇艺2018年Java算法自编写
### 题目：括号匹配深度
1.空串"是一个合法的括号匹配序列
2.如果"X"和"Y”都是合法的括号匹配序列,"Y"也是一- 个合法的括号匹配序列
3.如果"X"是一个合法的括号匹配序列那么"(X)"也是一一个合法的括号匹配序列
4.每个合法的括号序列都可以由以上规则生成。
例如: ""，")","()()" "((()))"都是合法的括号序列对于一个合法的括号序列我们又有
以下定义它的深度:
1.空串"的深度是0
2.如果字符串"X"的深度匙x,字符串"Y"的深度是y,那么字符串"XY"的深度为
max(x,y)
3.如果"X"的深度是x,那么 字符串"(X)"的深度是x+1
列如: "000"的深度是1, "((()))"的深度是3。牛牛现在给你一个合法的括号序列,需
要你计算出其深度。

**可以把其直接理解成四种情况**

1.先遇到"("，再遇到"("。count+1

2.先遇到"("，再遇到")"。count不变

3.先遇到")"，再遇到"("。count不变

4.先遇到")"，再遇到")"。count不变

**注意设立条件只有先遇到左括号，程序才会开始计数，否则count一直保持0**
直接上代码：

package com.example.listviewtest;

import java.util.Scanner;

public class test5 {

    public static void main(String[] args)//2017年爱奇艺java题
    {
        int p=1;
        while(p ==1){
            int count = 0;
            Scanner scanner = new Scanner(System.in);
            System.out.print("请您输入内容:");
            String contents=scanner.nextLine(); //输入整型
            char a[] = contents.toCharArray();
            if(a[0] == '(')//第一个必须是左括号，否则直接失效
            {
                count++;
                for (int i = 1 ;i<a.length;i++)
                {
                    if(a[i-1]=='('&&a[i]=='(')//前一个是左括号，如果本次也为左括号计数加一，其他三种情况都不计数
                    {
                        count++;
                    }
                }

            }
            System.out.println(count);
            System.out.println(contents);
        }
    }
}
