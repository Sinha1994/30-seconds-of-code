---
title: Square root
tags: math
expertise: beginner
firstSeen: 2022-07-10T07:09:33+0000
---

Find the square root of any number using binary search approach.

- Handling base case for `n=0` and `n=1` before starting the loop.
- Declare two variables, `start` and `end` to run the loop until `start<=end`.
- Declare variable `ans` to hold the answer and variable `mid` to find middle value.
- If power of `mid` is equal to n then return `mid` as square root of n
- In each iteration checks if the square of `mid` is less then or equal to `n` if yes update `start` for larger value and store `mid` in `ans`.
- Otherwise update `end` for smaller value in the range.
- At the end of loop return value of `ans` as square root.

```js
const squareRoot = n => {
    if(n === 0 || n === 1)
    return n;
    let start=1,end=n,ans=0;
    while(start<=end){
        const mid = Math.floor((start+end)/2);
        if(mid*mid === n){
            return mid;
        }
        if(mid*mid <= n){
            start=mid+1;
            ans = mid;
        } else {
            end = mid-1;
        }
    }
    return ans;
}
```

```js
squareRoot(4); // 2
squareRoot(10); //3
squareRoot(2147395600); // 46340
```