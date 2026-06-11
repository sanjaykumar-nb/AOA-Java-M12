# **EX 2D – Pattern Matching using Naive Approach**

## **DATE: 16-04-2026**

## **AIM:**

To write a Java program using the **Naive Pattern Matching** technique to find all occurrences of a pattern in a given text.

## **Given:**

A text string of length **n** and a pattern string of length **m**, where **n > m**.
The task is to print all positions where the pattern occurs in the text.

### **Example:**

* **Input:**
  text = "THIS IS A TEST TEXT"
  pattern = "TEST"
  **Output:** Pattern found at index 10

* **Input:**
  text = "AABAACAADAABAABA"
  pattern = "AABA"
  **Output:**
  Pattern found at index 0
  Pattern found at index 9
  Pattern found at index 12

---

## **Algorithm**

1. Read the text string and the pattern string.
2. Find the lengths of the text (**n**) and pattern (**m**).
3. Loop from index `0` to `n - m`.
4. For each position, compare characters of text and pattern one by one.
5. If all characters match, print the index where the pattern starts.

---

## **Program:**

```java
/*
Program to implement Naive Pattern Matching
Developed by: SANJAYKUMAR N B
Register Number: 212223230189
*/

import java.util.Scanner;

public class NaivePatternSearch {

    static void search(String text, String pattern){
        int n = text.length();
        int m = pattern.length();

        for(int i = 0; i <= n - m; i++){
            int j;
            for(j = 0; j < m; j++){
                if(text.charAt(i + j) != pattern.charAt(j)){
                    break;
                }
            }
            if(j == m){
                System.out.println("Pattern found at index " + i);
            }
        }
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        String text = scanner.nextLine();
        String pattern = scanner.nextLine();

        search(text, pattern);

        scanner.close();
    }
}
```

---

## **Output:**

<img width="1183" height="304" alt="image" src="https://github.com/user-attachments/assets/c4a3cdcc-80fb-43b0-a41e-1050bc74351c" />


---

## **Result:**

The program for **Naive Pattern Matching** was successfully executed, and the expected output was obtained.
