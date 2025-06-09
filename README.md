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

* Easy Problems:
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

`Note : Will Update within 24 Hours`

---
## 📌 License

fell free to use, modify, and share with attribution.

Connect with me on my [LinkedIn](www.linkedin.com/in/sahilshaikh110205)
