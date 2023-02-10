# Lab 3
## Question 1
```
public class NewClass {
    public static int getLargest(int arr[], int sz) {   // Comments will give a cumulative calculation for Big O
        int iterate1 = 0;                               // 1
        int iterate2 = 0;                               // 1+1
        int largest = 0;                                // 1+1+1
        while (iterate1 < sz - 1) {                     // 1+1+1+N
            iterate2++;                                 // 1+1+1+N+1
            if (iterate2 == sz) {                       // 1+1+1+N+1+N
                iterate1++;                             // 1+1+1+N+1+N+1
                iterate2 = iterate1;                    // 1+1+1+N+1+N+1+1
                continue;                               // 1+1+1+N+1+N+1+1+1
            }
            int product = arr[iterate1 * iterate2];     // 1+1+1+N+1+N+1+1+1+1
            if (product > largest)                      // 1+1+1+N+1+N+1+1+1+1+1
                largest = product;                      // 1+1+1+N+1+N+1+1+1+1+1+1
        }
        return largest;                                 // 1+1+1+N+1+N+1+1+1+1+1+1+1
    }                                                   // 11+2N
}                                                       // T(n)=O(N)
```
<details open>
<summary>A lengthy proof</summary>
<br>
arr=[0,1,2]
sz=3

0<2
i2=1
pro=0*1

0<2
i2=2
pro=0*2

0<2
i2=3
3=3
i1=1
i2=1
pro=1*1
larg=1

1<2
i2=2
pro=1*2

1<2
i2=3
3=3
i1=2
i2=2
pro=2*2
larg=4

2<2 // FALSE

return 4
</details>

## Question 2
Place all (20) of the M&M bags on top of the scale, noting that the total weight should be 20.1g. Continuously remove bags one by one from the top of the stack until a decrease of 1.1g is noticed, identifying that the last bag removed has a weight of 1.1g.
