# **EX 2B Minimum Jumps to Reach End using Greedy Algorithm**

## **DATE: 15-04-2026**

## **AIM:**

To write a Java program that finds the minimum number of jumps required to reach the last index of an array.
Each element in the array represents the maximum number of steps you can move forward from that index.

---

## **Algorithm**

1. Read the number of elements and store them in an array.
2. Handle base conditions:

   * If array length is 1 → 0 jumps.
   * If the first element is 0 → cannot move → return -1.
3. Initialise **jumps = 0**, **end = 0**, and **farthest = 0**.
4. Traverse the array and at each index update the farthest reachable index.
5. When the current index reaches the end of the current jump range, increase jump count.
6. If at any point farthest reaches or crosses the last index, return the jump count.
7. Print the minimum jumps needed.

---

## **Program:**

```JAVA
/*
Program to implement Minimum Jumps to Reach End using Greedy Algorithm
Developed by: SANJAYKUMAR N B
Register Number: 212223230189
*/
import java.util.Scanner;

public class MinJumpToEnd {

    public static int minimumJumps(int[] array) {
        int n = array.length;
        if (n <= 1) return 0;
        if (array[0] == 0) return -1;

        int jumps = 0, end = 0, farthest = 0;

        for (int i = 0; i < n - 1; i++) {
            farthest = Math.max(farthest, i + array[i]);

            if (i == end) {
                jumps++;
                end = farthest;
                if (end >= n - 1) return jumps;
            }
        }
        return -1;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int[] nums = new int[n];

        for (int i = 0; i < n; i++) {
            nums[i] = sc.nextInt();
        }

        System.out.println("Minimum jumps to reach last index: " + minimumJumps(nums));
    }
}
```

---

## **Output:**

<img width="1056" height="353" alt="image" src="https://github.com/user-attachments/assets/d3dce493-e9dd-42de-8c52-53e2181933a8" />


## **Result:**

The program was successfully implemented and the expected output was verified.

---
