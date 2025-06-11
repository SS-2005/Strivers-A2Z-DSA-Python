# Strivers-A2Z-DSA-Python

---
## Introduction:

🚀 My journey through Striver’s A2Z DSA Sheet using Python | Personal solutions, logic-first approach (No AI used)

This repository contains my personal solutions to the [Striver’s A2Z DSA Sheet](https://takeuforward.org/strivers-a2z-dsa-course/strivers-a2z-dsa-course-sheet-2/) using Python 🐍.<br>
I'm solving the Striver’s A2Z DSA Sheet using Python 🐍 — one day at a time. All solutions are written with my own logic, no ChatGPT or AI tools. This repo is to track my consistency and help others looking for clean, beginner-friendly Python DSA implementations.

---
## 🔗 Credits

- 🧑‍💻 **LinkedIn:** [Take U Forword](https://www.linkedin.com/company/takeuforward/)
- 📚 **Hosted on:** [Take U Forward](https://takeuforward.org/strivers-a2z-dsa-course/strivers-a2z-dsa-course-sheet-2/)

---
## Problems :

`Pre-requisite: Basic Python understanding`

### I) Easy Problems:

1) Check Palindrome

[LeetCode](https://leetcode.com/problems/palindrome-number/description/)

```
def isPalindrome(self, x):
    x = str(x)
    y = x[::-1]
    if x == y:
        return True
    else:
        return False
```

2) GCD

```
def gcd(n1, n2):
    d1 = []
    d2 = []
    for i in range(1, n1 + 1):
        if n1 % i == 0:
            d1.append(i)
    for i in range(1, n2 + 1):
        if n2 % i == 0:
            d2.append(i)
    c = list(set(d1) & set(d2))
    gcd = max(c)
    return gcd
```

3) Armstrong Numbers

[LeetCode](https://leetcode.com/problems/armstrong-number/description/)

```
def armstrong(n):
    s = str(n)
    if n >= 0:
        ns = s[:]
        d = len(ns)
    else:
        ns = s[1:]
        d = len(ns)
    f = 0
    for i in ns:
        f = f + pow(int(i), d)
    if n == f:
        return True
    else:
        return False
```

4) Print all Divisors

```
def div(n):
    d = []
    for i in range(1, n + 1):
        if n % i == 0:
            d.append(i)
    return d
```

5) Check for Prime

```
def IsPrime(n):
    divs = div(n)
    if divs == [1, n] or n == 1:
        return True
    else:
        return False
```
6) Recurssion:

A function which calls it self until a base condition is satiesfied is known as `Reccursion`. A base condition is a cruitial part of a recursive funtion else the function will run infinitely

Problems on Recurssion

* Print name N times using recursion:
```
def print_name(n,name):
    if n == 1:
        print(s)
    else:
        print("name")
        print_name(n-1,name)
```

* 	Print 1 to N using recursion:
```
def print1ton(n):
    if n == 1:
        print(n)
    else:
        print1ton(n-1)
        print(n)
```

* Print N to 1 using recursion:
```
def printnto1(n):
    if n == 1:
        print(n)
    else:
        print(n)
        printnto1(n-1)
```

* Sum of first N numbers:
```
def sumR(n):
    if n==0:
        return 0
    else:
        s= n + sumR(n-1)
    return s
```

* Factorial of N numbers:
```
def factR(n):
    if n==0:
        return 1
    else:
        s= n * factR(n-1)
    return s
```

7) Reverse an Array In-Place:
```
def reva(arr,n):
    i=0
    j=n-1
    for _ in range(n//2):
        arr[i],arr[j]=arr[j],arr[i]
        i=i+1
        j=j-1
    return arr

```

8) Sum of Fibonacci Number Series:
[leetcode](https://leetcode.com/problems/fibonacci-number/description/)
```
def f(n):
    if n==0:
        return 0
    elif n==1:
        return 1
    else:
        return f(n-1)+f(n-2)
```




### II) Medium Problems:

* **Hashing:**
Hashing is a technique used to map data (keys) to a fixed-size value (called hash code or hash value) using a hash function. It allows for fast data access, insertion, and deletion often in constant time O(1).
  
1) Check if a string is palindrome or not with Certain conditions:
[Leetcoode](https://leetcode.com/problems/valid-palindrome/description/)
```
    def pal(s):
        import re
        s=re.sub(r'[^a-zA-Z0-9]', '', s).lower()
        s=s.lower()
        r=s[::-1]
        return s==r
```

2) Find the highest/lowest frequency element:
[Leetcode](https://leetcode.com/problems/frequency-of-the-most-frequent-element/description/)
```
class Solution(object):
    def maxFrequency(self, nums, k):
        """
        :type nums: List[int]
        :type k: int
        :rtype: int
        """
        nums.sort()
        left = 0
        total = 0
        max_freq = 0
        for right in range(len(nums)):
                # total operations needed to bring all numbers in window [left...right] up to nums[right]
            total += (nums[right] - nums[right - 1]) * (right - left)

            # If total operations exceed k, shrink the window from the left
            while total > k:
                total -= nums[right] - nums[left]
                left += 1

            # Update max frequency
            max_freq = max(max_freq, right - left + 1)

        return max_freq
```


### III) Hard Probles:

`Note : Will Update within 24 Hours`

---
## 📌 License

fell free to use, modify, and share with attribution.

Connect with me on my [LinkedIn](www.linkedin.com/in/sahilshaikh110205)
