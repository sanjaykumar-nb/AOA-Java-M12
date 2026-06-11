# **EX 2E – Longest Palindromic Substring using Manacher’s Algorithm**

## **DATE: 16-04-2026**

## **AIM:**

To write a Java program to find the **Longest Palindromic Substring** in a given string **using Manacher’s Algorithm**.

---

## **Algorithm**

1. Convert the input string by inserting `#` between characters to handle even-length palindromes.
2. Maintain an array `P[]` to store the radius (half-length) of palindromes around each centre.
3. Use two variables:

   * **C** → current center
   * **R** → right boundary of the current palindrome
4. For every character:

   * Mirror the index across the centre and update value of `P[i]`
   * Expand around the centre to update palindrome radius
   * If the palindrome goes beyond R, update C and R
5. Find the maximum radius in `P[]` and extract the longest palindromic substring from the original string.

---

## **Program**

```JAVA
/*
Program to find Longest Palindromic Substring using Manacher's Algorithm
Developed by: SANJAYKUMAR N B
Register Number: 212223230189
*/

import java.util.Scanner;

public class Manacher {

    public static String longestPalindrome(String s) {
        if (s == null || s.length() == 0) return "";

        String t = preprocess(s);
        int n = t.length();
        int[] P = new int[n];

        int C = 0;
        int R = 0;

        for (int i = 1; i < n - 1; i++) {
            int mirror = 2 * C - i;

            if (i < R)
                P[i] = Math.min(R - i, P[mirror]);

            while (t.charAt(i + (1 + P[i])) == t.charAt(i - (1 + P[i]))) {
                P[i]++;
            }

            if (i + P[i] > R) {
                C = i;
                R = i + P[i];
            }
        }

        int maxLen = 0;
        int centerIndex = 0;
        for (int i = 1; i < n - 1; i++) {
            if (P[i] > maxLen) {
                maxLen = P[i];
                centerIndex = i;
            }
        }

        int start = (centerIndex - maxLen) / 2;
        return s.substring(start, start + maxLen);
    }

    private static String preprocess(String s) {
        StringBuilder sb = new StringBuilder();
        sb.append("^");
        for (char c : s.toCharArray()) {
            sb.append("#").append(c);
        }
        sb.append("#$");
        return sb.toString();
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        String input = scanner.nextLine();

        String result = longestPalindrome(input);
        System.out.println("Longest Palindromic Substring: " + result);

        scanner.close();
    }
}
```

---

## **Output:**

<img width="1213" height="259" alt="image" src="https://github.com/user-attachments/assets/49175af7-a47c-4db1-a64a-c646ecaec7e6" />


---

## **Result:**

The program to find the **Longest Palindromic Substring using Manacher’s Algorithm** was successfully executed, and the output was verified.

