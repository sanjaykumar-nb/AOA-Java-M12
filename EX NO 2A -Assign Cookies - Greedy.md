# **EX 2A Assign Cookies using Greedy Algorithm**

## **DATE: 15-04-2026**

## **AIM:**

To write a Java program that assigns cookies to children using a greedy strategy.
Each child has a greed factor **g[i]**, and each cookie has a size **s[j]**.
A child is content if **s[j] ≥ g[i]**, and each child can receive at most one cookie.
The goal is to maximise the number of content children.

---

## **Algorithm**

1. Read the number of children and their greed values.
2. Read the number of cookies and their sizes.
3. Sort both arrays in ascending order.
4. Use two pointers to match the smallest available cookie to the least greedy child.
5. Count each successful assignment and print the total.

---

## **Program:**

```java
/*
Program to implement Assign Cookies using Greedy Algorithm
Developed by: SANJAYKUMAR N B
Register Number: 212223230189
*/
import java.util.*;

public class AssignCookies {
    
    public static int findContentChildren(int[] g, int[] s) {
        Arrays.sort(g);
        Arrays.sort(s);
        int i = 0, j = 0;

        while(i < g.length && j < s.length){
            if(s[j] >= g[i]) i++;
            j++;
        }
        return i;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int[] g = new int[n];
        for (int i = 0; i < n; i++) g[i] = sc.nextInt();

        int m = sc.nextInt();
        int[] s = new int[m];
        for (int i = 0; i < m; i++) s[i] = sc.nextInt();

        System.out.println(findContentChildren(g, s));
    }
}
```

---

## **Output:**

<img width="1031" height="402" alt="image" src="https://github.com/user-attachments/assets/7d30fdae-b8a4-4b5e-9de6-f28dded1bfae" />



## **Result:**

The program was successfully implemented and the expected output was verified.

---
