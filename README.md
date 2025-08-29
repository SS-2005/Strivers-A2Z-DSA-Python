# Strivers-A2Z-DSA-Python

---

## Introduction:


🚀 My journey through Striver’s A2Z DSA Sheet using Python | Personal solutions, logic-first approach (No AI used)

This repository contains my personal solutions to the [Striver’s A2Z DSA Sheet](https://takeuforward.org/strivers-a2z-dsa-course/strivers-a2z-dsa-course-sheet-2/) using Python 🐍.

<br>
I'm solving the Striver’s A2Z DSA Sheet using Python  — one day at a time. All solutions are written with my own logic, no ChatGPT or AI tools

This repo is to track my consistency and help others looking for clean, beginner-friendly Python DSA implementations

---
## 🔗 Credits

- 🧑‍💻 **LinkedIn:** [Take U Forword](https://www.linkedin.com/company/takeuforward/)


- 📚 **Hosted on:** [Take U Forward](https://takeuforward.org/strivers-a2z-dsa-course/strivers-a2z-dsa-course-sheet-2/)

---

## Problems :

`Pre-requisite: Basic Python understanding, OOP's and Programming methodology.`

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
def print_name(n, name):
    if n == 0:
        return
    print_name(n - 1, name)  
    print(name)              
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

8) Sum of Fibonacci Number Series.
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

#### 9)Sorting Techniques:
<br>

#### **Selection Sort** :
  
Selection Sort is a simple comparison-based sorting algorithm. It divides the list into two parts:

  * The sorted part at the beginning.

  * The unsorted part at the end

It repeatedly selects the smallest (or largest) element from the unsorted part and swaps it with the first element in the unsorted part, growing the sorted part by one element each time.

Complexities :
| Case    | Complexity |
| ------- | ---------- |
| Best    | O(n²)      |
| Average | O(n²)      |
| Worst   | O(n²)      |

Code in python
```
def sel(arr):
    for i in range(len(arr)):
        m=i
        for j in range(i+1,len(arr)):
            if arr[j]<arr[m]:
                m=j
        arr[i],arr[m]=arr[m],arr[i]
    return arr
```

🧮 Space Complexity:

* O(1) (in-place sorting, only swaps elements)

✅ Pros:

 * Simple to understand and implement
    
 * No additional memory required
    
 * Good for small datasets


❌ Cons:

 * Inefficient for large lists
    
 * Always takes O(n²) time
    
 * More swaps compared to Insertion Sort


💡 Use Cases:

 * When simplicity is more important than performance
    
 * Sorting very small arrays

#### Insertion Sort:

Insertion Sort is a simple comparison-based sorting algorithm.
It builds the sorted list one item at a time, by repeatedly inserting the current element into its correct position in the already-sorted part of the array.

Code:
```
def ins(arr):
    for i in range(1, len(arr)):
        key = arr[i]
        j = i - 1
        while j >= 0 and arr[j] > key:
            arr[j + 1] = arr[j]
            j -= 1
        arr[j + 1] = key
    return arr

```

📈 Time Complexity:
| Case            | Comparisons | Shifts   | Time  |
| --------------- | ----------- | -------- | ----- |
| Best (sorted)   | n-1         | 0        | O(n)  |
| Average         | \~n²/4      | \~n²/4   | O(n²) |
| Worst (reverse) | n(n-1)/2    | n(n-1)/2 | O(n²) |

🧮 Space Complexity
 * O(1) auxiliary space
    (In-place sorting, no extra arrays used)

⚙️ Stability: ✅ Stable
(Preserves the relative order of equal elements)

🧠 Adaptive Nature:✅ Adaptive
(Performs better if the input is already or nearly sorted)

✅ Advantages.

 * Very simple and intuitive
    
 * Efficient for small datasets
    
 * Adaptive: fast for nearly sorted data
    
 * In-place and stable
    
 * Works well when insertion cost is low

❌ Disadvantages.

 * Inefficient for large datasets
 * O(n²) time complexity in worst case
<br>

#### **Bubble sort:**

🔹 Introduction:
Bubble Sort is a simple comparison-based sorting algorithm. It works by repeatedly swapping adjacent elements if they are in the wrong order. It continues this process until the array is sorted

✅ Advantages:

 *  Very simple to implement
 * Stable sorting algorithm
 *  Works well on nearly sorted arrays
 * No extra memory needed (in-place)

❌ Disadvantages:

 * Very slow for large datasets
 * Inefficient compared to other O(n²) sorts like insertion sort.

Code:
```
def bub(arr):
    n = len(arr)
    for i in range(n):
        swapped = False
        for j in range(0, n - i - 1):
            if arr[j] > arr[j + 1]:
                arr[j], arr[j + 1] = arr[j + 1], arr[j]
                swapped = True
        if not swapped:
            break
    return arr
```

⏱️ Time and Space Complexity:

 * Time (Best Case): O(n) — when array is already sorted
 * Time (Average/Worst Case): O(n²)
 * Space: O(1) — no extra memory used

<br>
    
#### **Merge sort:**
  
🔹 Introduction:
Merge Sort is a divide-and-conquer algorithm. It divides the array into halves, recursively sorts them, and then merges the sorted halves to produce the final sorted array

✅ Advantages:

 * Always O(n log n) time complexity
 * Very stable and predictable performance
 * Stable sort — maintains the order of equal elements

❌ Disadvantages:

 * Requires additional memory (not in-place)
 * Slightly slower than quicksort in practice due to overhead
 * Recursive — can consume more stack space

Code:
```
def merge(arr):
    if len(arr) > 1:
        mid = len(arr) // 2
        left = arr[:mid]
        right = arr[mid:]

        merge_sort(left)
        merge_sort(right)

        i = j = k = 0
        while i < len(left) and j < len(right):
            if left[i] < right[j]:
                arr[k] = left[i]
                i += 1
            else:
                arr[k] = right[j]
                j += 1
            k += 1
        while i < len(left):
            arr[k] = left[i]
            i += 1
            k += 1
        while j < len(right):
            arr[k] = right[j]
            j += 1
            k += 1
    return arr

```

⏱️ Time and Space Complexity:

 * Time (Best, Average, Worst Case): O(n log n)
 * Space: O(n) — due to extra arrays for merging

#### Quick Sort:

🔹 Introduction:
Quick Sort is a divide-and-conquer algorithm. It picks a pivot element, partitions the array around the pivot so that elements less than pivot come before, and greater ones after. It then recursively sorts the sub-arrays.

✅ Advantages:

 * Very fast in practice
 * Efficient on large datasets
 * In-place sorting (no additional space)
 * Widely used in system-level sorting functions

❌ Disadvantages:

 * Not stable by default.
 * Worst-case performance is O(n²)
 * Recursive; risk of stack overflow on large arrays (without optimization)

Python Code:
```
def quick(arr):
    if len(arr) <= 1:
        return arr
    pivot = arr[0]
    less = [x for x in arr[1:] if x <= pivot]
    greater = [x for x in arr[1:] if x > pivot]
    return quick_sort(less) + [pivot] + quick_sort(greater)
```

⏱️ Time and Space Complexity:

 * Time (Best and Average Case): O(n log n)
 * Time (Worst Case): O(n²) — when pivot is always the smallest/largest
 * Space: O(log n) — due to recursion stack (for in-place version)

10) Largest Element in an Array

Code:
```
def large(arr):
    arr.sort()
    return arr[len(arr)-1]
```

11) Second Largest Element in an Array without sorting.

Code:
```
def SL(arr):
    for i in range(len(arr)):
        for j in range(len(arr)):
            if arr[i]>arr[j]:
                max1=arr[i]
                max2=arr[j]
    return max2
```

12) Check if the array is sorted.

Code:
```
def IsSorted(arr):
    return arr==sorted(arr)
```

13) Remove duplicates from Sorted array.

Code:
```
def RD(arr):
    return sorted(set(arr))
```

14) Left Rotate an array by one place<br>
[Leetcode](https://leetcode.com/problems/rotate-array/)

Code:
```
class Solution:
    def rotate(self, nums: List[int], k: int) -> None:
        """
        Do not return anything, modify nums in-place instead.
        """
        if len(nums)<k:
            for i in range(k):
                nums.insert(0,nums[len(nums)-1])
                del(nums[len(nums)-1])
                nums[:]=nums
        else:
            nums[:]=nums[len(nums)-k:]+nums[:len(nums)-k]
```
15) Move Zeros to end
[Leetcode](https://leetcode.com/problems/move-zeroes/description/)

Code:
```
class Solution:
    def moveZeroes(self, nums: List[int]) -> None:
        """
        Do not return anything, modify nums in-place instead.
        """
        Pos=[]
        for i in range(len(nums)):
            if nums[i]==0:
                Pos.append(i)
        for i in sorted(Pos,reverse=True):
            del nums[i]
        for i in range(len(Pos)):
            nums.append(0)
        nums[:]=nums
```

16) Linear Search

Code:
```
def LS(nums,x):
    for i in range(len(nums)):
        if nums[i]==x:
            return i
    return -1

```

17) Find the Union

Code:
```
class Solution:
    def unionArray(self, nums1, nums2):
        return set(nums1+nums2)
```

18) Find missing number in an array

[Leetcode](https://leetcode.com/problems/missing-number/description/)

Code:
```
class Solution:
    def missingNumber(self, nums: List[int]) -> int:
        n=len(nums)
        all=[i for i in range(0,n+1)]
        for a in all:
            if a not in nums:
                return a
```

19) Maximum Consecutive Ones

[Leetcode](https://leetcode.com/problems/max-consecutive-ones/)

Code:
```
class Solution:
    def findMaxConsecutiveOnes(self, nums: List[int]) -> int:
        m,c=0,0
        for i in range(len(nums)):
            if nums[i]==1:
                c+=1
            else:
                c=0
            if c>m:
                m=c
        return m
```
20) Kadane's Algorithm, maximum subarray sum

[Leetcode](https://leetcode.com/problems/maximum-subarray/description/)

Code:
```
class Solution:
    def maxSubArray(self, nums: List[int]) -> int:
        cs=ms=nums[0]
        for i in range(1,len(nums)):
            cs=max(nums[i],cs+nums[i])
            ms=max(ms,cs)
        return ms
```

21) Sell and Buy Stock

[Leetcode](https://leetcode.com/problems/best-time-to-buy-and-sell-stock/description/)
Code:
```
class Solution:
    def maxProfit(self, prices: List[int]) -> int:
        profit=0
        mini=prices[0]
        for i in range(1,len(prices)):
            cost=prices[i]-mini
            profit=max(profit,cost)
            mini=min(mini,prices[i])
        return profit

```

22) Leaders in an Array problem

Code:
```
class Solution:
    def leaders(self, nums):
        leads=[]
        mini=nums[len(nums)-1]
        leads.append(mini)
        for i in range(len(nums)-2,-1,-1):
            if nums[i]>mini:
                leads.append(nums[i])
                mini=max(nums[i],mini)
        return leads[::-1]
```

23) Implement Lower Bound:

Code:
```
class Solution:
    def lowerBound(self, nums, x):
        st,end=0,len(nums)-1
        index=len(nums)
        while st<=end:
            mid=(st+end)//2
            if nums[mid]>=x:
                index=mid
                end=mid-1
            else:
                st=mid+1
        return index
```



24) Implement Upper Bound

Code:
```
class Solution:
    def upperBound(self, nums, x):
        st,end=0,len(nums)-1
        index=len(nums)
        while st<=end:
            mid=(st+end)//2
            if nums[mid]>x:
                index=mid
                end=mid-1
            else:
                st=mid+1
        return index
```

25) Search Insert Position:  
[Leetcode](https://leetcode.com/problems/search-insert-position/description/)

Code:
```
class Solution(object):
    def searchInsert(self, nums, target):
        """
        :type nums: List[int]
        :type target: int
        :rtype: int
        """
        st=0
        end=len(nums)-1
        while st<=end:
            mid=(st+end)//2
            if target==nums[mid]:
                return mid
            elif target>nums[mid]:
                st=mid+1
            elif target<nums[mid]:
                end=mid-1
        return st
```

26) Floor/Ceil in Given Sorted Array.

Code:
```
class Solution:
    def getFloorAndCeil(self, nums, x):
        st,end=0,len(nums)-1
        floor,ceil=-1,-1
        while st<=end:
            mid=(st+end)//2
            if nums[mid]<x:
                floor=nums[mid]
                st=mid+1
            elif x<nums[mid]:
                ceil=nums[mid]
                end=mid-1
            elif nums[mid]==x:
                return x,x
        return floor,ceil
```

27) Find the first or last occurrence of a given number in a sorted array:

[Leetcode](https://leetcode.com/problems/find-first-and-last-position-of-element-in-sorted-array/description/)


Code:
```
class Solution(object):
    def searchRange(self, nums, target):
        """
        :type nums: List[int]
        :type target: int
        :rtype: List[int]
        """
        return [self.binarysearch(nums,target,True),self.binarysearch(nums,target,False)]

    def binarysearch(self,nums,target,First):
        st=0
        end=len(nums)-1
        result=-1
        while st<=end:
            mid=(st+end)//2
            if target>nums[mid]:
                st=mid+1
            elif target<nums[mid]:
                end=mid-1
            elif target==nums[mid]:
                result=mid
                if First:
                    end=mid-1
                else:
                    st=mid+1
        return result
```

28) Reverse Integer

[Leetcode](https://leetcode.com/problems/reverse-integer/description/)

Code:
```
class Solution(object):
    def reverse(self, no):
        """
        :type no: int
        :rtype: int
        """
        s=str(no)
        if no > 0:
            rev=s[::-1].lstrip('0')
            f=int(rev)
        elif no==0:
            return 0
        else:
            t=s[len(s):0:-1]
            rev=int(t)
            f=-rev
        # in specific range or not
        if f > 2**31 - 1 or f < -2**31:
            return 0
        return f
```

29) Find the row with maximum number of 1's

[Link](https://takeuforward.org/plus/dsa/problems/find-row-with-maximum-1's)

Code:
```
def lowerBound(arr, n, x):
    low = 0
    high = n - 1
    ans = n

    while low <= high:
        mid = (low + high) // 2
        # maybe an answer
        if arr[mid] >= x:
            ans = mid
            # look for smaller index on the left
            high = mid - 1
        else:
            low = mid + 1  # look on the right
    return ans


def rowWithMax1s(matrix, n, m):
    cnt_max = 0
    index = -1

    # traverse the rows:
    for i in range(n):
        # get the number of 1's:
        cnt_ones = m - lowerBound(matrix[i], m, 1)
        if cnt_ones > cnt_max:
            cnt_max = cnt_ones
            index = i
    return index
```


30) Remove outermost Paranthesis.

[Leetcode](https://leetcode.com/problems/remove-outermost-parentheses/)

Code:
```
class Solution(object):
    def removeOuterParentheses(self, s):
        result = []
        balance = 0

        for char in s:
            if char == '(':
                if balance > 0:
                    result.append(char)
                balance += 1
            else:  
                balance -= 1
                if balance > 0:
                    result.append(char)

        return ''.join(result)

```

31) Largest Odd Number in String

[Leetcode](https://leetcode.com/problems/largest-odd-number-in-string/description/)

Code:
```
class Solution(object):
    def largestOddNumber(self, num):
        """
        :type num: str
        :rtype: str
        """
        for i in range(len(num) - 1, -1, -1):
            if int(num[i]) % 2 == 1:
                return num[:i + 1]
        return ""

```

32) Longest Common Prefix

[leetcode](https://leetcode.com/problems/longest-common-prefix/description/)

Code:
```
class Solution(object):
    def longestCommonPrefix(self, strs):
        """
        :type strs: List[str]
        :rtype: str
        """
        if not strs:  # agar list empty hai
            return ""
        
        prefix = strs[0]  # pehle string ko prefix maan lo
        
        for s in strs[1:]:
            # Jab tak current string prefix se start nahi hota, prefix ko chhota karo
            while not s.startswith(prefix):
                prefix = prefix[:-1]
                if not prefix:
                    return ""
        
        return prefix

```


<br>

---

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
* Patterns Problem:

All Problems Link : [Easy to hard (With Solutions)](https://takeuforward.org/strivers-a2z-dsa-course/must-do-pattern-problems-before-starting-dsa/)

1<br>
1 2 <br>
1 2 3<br>

[Link](https://www.naukri.com/code360/problems/n-triangles_6573689)

Code:
```
def nTriangle(n:int) ->None:
    # Write your solution here.
    for i in range(n+1):
        for j in range(i):
            print("{} ".format(j+1),end="")
        print()
    pass
```
<br>

--

1<br>
2 2 <br>
3 3 3<br>

[Link](https://www.naukri.com/code360/problems/triangle_6573690)

Code:
```
def triangle( n:int) ->None:
    # Write your solution here.
    for i in range(1,n+1):
        for j in range(i):
            print("{} ".format(i),end="")
        print()
    pass
```

--

Pattern
```
  *
 ***
*****
```

[Link](https://www.naukri.com/code360/problems/star-triangle_6573671)

Code:
```
def nStarTriangle(n: int) -> None:
    # Write your code here.
    space=n-1
    star=1
    for i in range(n):
        #space
        for j in range(space):
            print(" ",end="")
        space-=1

        #star
        for j in range(star):
            print("*",end="")
        star+=2

        #next line
        print() 

    pass
```

--

```
Pattern
*****
 ***
  *
```

[Link](https://www.naukri.com/code360/problems/reverse-star-triangle_6573685)

Code:
```
def nStarTriangle(n: int) -> None:
    # Write your code here.

    #star value
    star=1
    #to determine star value
    for j in range(n-1):
        star+=2
    
    #space value
    space=0

    #pattern
    for i in range(n):
        #space
        for j in range(space):
            print(" ",end="")
        space=space+1

        for j in range(star):
            print("*",end="")
        star-=2

        #next line
        print()
    pass
```

--

```
Pattern
1             1
1 2         2 1
1 2 3     3 2 1
1 2 3 4 4 3 2 1
```

[Link](https://www.naukri.com/code360/problems/number-crown_6581894)

Code:
```
def numberCrown(n: int) -> None:
    # Write your solution here.
    space=2*n-2
    for i in range(1,n+1):
        for j in range(1,i+1):
            print(f"{j} ",end="")
        
        for sp in range(space):
            print("  ",end="")
        space-=2

        for j in range(i,0,-1):
            print(f"{j} ",end="")
        
        print()
```

--


A 

A B 

A B C 


[Link](https://bit.ly/3GyWCYs)

Code:
```
def nLetterTriangle(n: int) -> None:
    # Write your solution here.
    for i in range(1,n+1):
        for j in range(i):
            print(f"{chr(65+j)} ",end="")
        print()

```

--


  A
    
A B A


[Link](https://bit.ly/3jJ7CcR)

Code:
```
def alphaHill(n: int):
    # Write your solution from here.
    space=n-1
    for i in range(n):
        #space
        for sp in range(space):
            print(" ",end="")
        space-=1

        #char increasing to A
        for ch in range(0,i+1):
            print(f"{chr(65+ch)} ",end="")

        #char decreasing to A
        for ch in range(i-1,-1,-1):
            print(f"{chr(65+ch)} ",end="")

        #next line
        print()
```

--


C

C B 

C B A

[Link](https://bit.ly/3Z3scot)

Code:
```
def alphaTriangle(n: int):
    # Write your solution here.
    for i in range(1,n+1):
        for j in range(i):
            print(f"{chr(65+n-1-j)} ",end="") 
        print() 
```

--

```
Pattern
* * * * * * 

* *     * * 

*         * 

*         * 

* *     * * 

* * * * * * 
```

[Link](https://takeuforward.org/pattern/pattern-19-symmetric-void-pattern/)

Code:
```
def symmetry(N: int):
    star=N
    space=0
    r_star=N
    r_space=0
    for i in range(N):
        for s in range(star):
            print("* ",end="")
        star-=1

        for s in range(space):
            print("  ",end="")
        space+=1

        for s in range(r_space):
            print("  ",end="")
        r_space+=1

        for s in range(r_star):
            print("* ",end="")
        r_star-=1

        print()

    star=1
    space=N-1
    r_star=1
    r_space=N-1
    for i in range(N):
        for s in range(star):
            print("* ",end="")
        star+=1

        for s in range(space):
            print("  ",end="")
        space-=1

        for s in range(r_space):
            print("  ",end="")
        r_space-=1

        for s in range(r_star):
            print("* ",end="")
        r_star+=1

        print()
```

--


```
Pattern
*****
*   *
*   *
*   *
*****
```

[Link](https://bit.ly/3vBpdpy)

Code:
```
def getStarPattern(n: int) -> None:
    # Write your solution here.
    for i in range(n):
        for j in range(n):
            if i==0 or i==n-1 or j==0 or j==n-1:
                print("*",end="")
            else:
                print(" ",end="")
        print()
```

--

```
Pattern
4444444
4333334
4322234
4321234
4322234
4333334
4444444
```

[Link](https://bit.ly/3vtRNJJ)

Code:
```
def getNumberPattern(n: int) -> None:
    # Write your solution here.
    size=2*n-1
    for i in range(size):
        for j in range(size):
            value=n-min(i,j,size-1-i,size-1-j)
            print(value,end="")
        print() #next line
```

-

3) Find the number that appears once, and other numbers twice

[Leetcode](https://leetcode.com/problems/single-number/description/)

Code:
```
class Solution:
    def singleNumber(self, nums: List[int]) -> int:
        d={}
        c=1
        for i in nums:
            if i in d.keys():
                d[i]=d[i]+1
            else:
                d[i]=c
        for x,y in d.items():
            if y==1:
                return x
            
```

4) 	Longest subarray with given sum K(positives) 

[Problem Link](https://takeuforward.org/plus/dsa/problems/longest-subarray-with-sum-k)

Code:
```
def lsa(nums,k):
    n=len(nums)
    l=0
    for i in range(n):
        sum=0
        for j in range(i,n):
            sum+=nums[j]
            if sum==k:
                l=max(l,j-i+1)
    return l
```

5) 2Sum Problem

[Leetcode](https://leetcode.com/problems/two-sum/description/)

Code:
```
class Solution(object):
    def twoSum(self, nums, target):
        """
        :type nums: List[int]
        :type target: int
        :rtype: List[int]
        """
        for i in range(len(nums)-1):
            for j in range(len(nums)-1,-1,-1):
                if i!=j:
                    if nums[i]+nums[j]==target:
                        return[i,j]
```

6) Sort an array of 0's 1's and 2's

[Leetcode](https://leetcode.com/problems/sort-colors/)

Code:
```
class Solution:
    def sortColors(self, nums: List[int]) -> None:
        """
        Do not return anything, modify nums in-place instead.
        """
        nums.sort()
```

7) Majority Element (>n/2 times) 

[Leetcode](https://leetcode.com/problems/majority-element/)

Code:
```
class Solution:
    def majorityElement(self, nums: List[int]) -> int:
        d={}
        c=1
        for num in nums:
            if num not in d.keys():
                d[num]=c
            else:
                d[num]+=1
        return max(d,key=d.get)
```

8) Print subarray with maximum subarray sum

Code:
```
def maxSubArray(nums):
    cs=ms=nums[0]
    for i in range(1,len(nums)):
        if nums[i]>cs+nums[i]:
            cs=nums[i]
            temp=i
        else:
            cs+=nums[i]
        if cs>ms:
            ms=cs
            start=temp
            end=i

    print("Max",ms)
    print("Subarray",nums[start:end+1])
    return ms
```

9) Rearrange the array in alternating positive and negative items

[Leetcode](https://leetcode.com/problems/rearrange-array-elements-by-sign/description/)

Code:
```
class Solution:
    def rearrangeArray(self, nums: List[int]) -> List[int]:
        pos,neg,r=[],[],[]
        for num in nums:
            if num>0:
                pos.append(num)
            else:
                neg.append(num)
        for i in range(len(nums)//2):
            r.append(pos[i])
            r.append(neg[i])
        return r
```

10) Next Permutation

[Leetcode](https://leetcode.com/problems/next-permutation/description/)

Code:
```
class Solution:
    def nextPermutation(self, nums: List[int]) -> None:
        index = -1
        for i in range(len(nums) - 2, -1, -1):
            if nums[i] < nums[i + 1]:
                index = i
                break
        if index == -1:
            nums.reverse()
            return
        for i in range(len(nums) - 1, index, -1):
            if nums[i] > nums[index]:
                nums[i], nums[index] = nums[index], nums[i]
                break
        nums[index + 1:] = reversed(nums[index + 1:])

```
11) Longest Consecutive Sequence in an Array

[Leetcode](https://leetcode.com/problems/longest-consecutive-sequence/editorial/)

Code:
```
class Solution:
    def longestConsecutive(self, nums):
        nums.sort()
        l=1
        cl=0
        start=nums[0]
        for i in range(1,len(nums)):
            if nums[i]==start+1:
                l+=1
                start=start+1
            elif nums[i]==start:
                pass
            else:
                cl=max(cl,l)
                l=1
                start=nums[i]
        l=max(cl,l)
        return l
```

12) Set Matrix Zeros

[Leetcode](https://leetcode.com/problems/set-matrix-zeroes/description/)

Code:
```
class Solution:
    def setZeroes(self, matrix: List[List[int]]) -> None:
        """
        Do not return anything, modify matrix in-place instead.
        """
        row,col=[],[]
        #finding pos of zero
        for i in range(len(matrix)):
            for j in range(len(matrix[0])):
                if matrix[i][j]==0:
                    row.append(i)
                    col.append(j)
        #setting row/col to 0
        for i in row:
            for j in range(len(matrix[0])):
                matrix[i][j]=0
        for i in range(len(matrix)):
            for j in col:
                matrix[i][j]=0
        matrix[:]=matrix
```

13) Rotate Matrix by 90 degrees

[Leetcode](https://leetcode.com/problems/rotate-image/description/)

Code:
```
class Solution:
    def rotate(self, matrix: List[List[int]]) -> None:
        """
        Do not return anything, modify matrix in-place instead.
        """
        ans=[[0]* len(matrix) for _ in range(len(matrix))]
        for i in range(len(matrix)):
            for j in range(len(matrix[0])):
                ans[j][len(matrix)-1-i]=matrix[i][j]
        matrix[:]=ans
```

14) Print the matrix in spiral manner

[Leetcode](https://leetcode.com/problems/spiral-matrix/description/)

Code:
```
class Solution:
    def spiralOrder(self, matrix: List[List[int]]) -> List[int]:
        n = len(matrix)
        m = len(matrix[0])
        left, right = 0, m - 1
        top, bottom = 0, n - 1
        ans = []
        
        while top <= bottom and left <= right:
            # top row
            for i in range(left, right + 1):
                ans.append(matrix[top][i])
            top += 1
            
            # right column
            for i in range(top, bottom + 1):
                ans.append(matrix[i][right])
            right -= 1
            
            if top <= bottom:
                # bottom row (reverse)
                for i in range(right, left - 1, -1):
                    ans.append(matrix[bottom][i])
                bottom -= 1
            
            if left <= right:
                # left column (reverse)
                for i in range(bottom, top - 1, -1):
                    ans.append(matrix[i][left])
                left += 1
        
        return ans
```

15) Count subarrays with given sum

[Leetcode](https://leetcode.com/problems/subarray-sum-equals-k/description/)

Code:

```
from collections import defaultdict

class Solution:
    def subarraySum(self, nums, k):
        prefix_sums = defaultdict(int)  # Stores frequency of each prefix sum
        prefix_sums[0] = 1              # Base case: one way to have a sum = 0 before starting

        current_sum = 0  # To store the sum of elements from index 0 to i
        count = 0        # To count valid subarrays

        for num in nums:
            current_sum += num   # Step 1: Update the running prefix sum

            # Step 2: Check if there's a prefix_sum such that current_sum - prefix_sum == k
            if (current_sum - k) in prefix_sums:
                count += prefix_sums[current_sum - k]
                # This means there are `prefix_sums[current_sum - k]` subarrays ending here with sum = k

            # Step 3: Update the map with the current prefix_sum
            prefix_sums[current_sum] += 1

        return count
```

16) Pascal's Triangle

[Leetcode](https://leetcode.com/problems/pascals-triangle/description/)

Code:
```
class Solution:
    def generate(self, numRows):
        result = []

        for row_num in range(numRows):
            row = [1] * (row_num + 1)  # Start with all 1s

            for j in range(1, row_num):
                # Use previous row to compute current row's inner elements
                row[j] = result[row_num - 1][j - 1] + result[row_num - 1][j]

            result.append(row)

        return result
```

17) Majority Element (n/3 times)

[Leetcode](https://leetcode.com/problems/majority-element-ii/description/)

Code:
```
class Solution(object):
    def majorityElement(self, nums):
        """
        :type nums: List[int]
        :rtype: List[int]
        """
        from collections import defaultdict

        count = defaultdict(int)
        for num in nums:
            count[num] += 1

        result = []
        n = len(nums)
        for num, freq in count.items():
            if freq > n // 3:
                result.append(num)

        return result
```

18) 3-Sum Problem

[Leetcode](https://leetcode.com/problems/3sum/description/)

Code:
```
class Solution:
    def threeSum(self, nums):
        nums.sort()
        res = []

        for i in range(len(nums)):
            # Skip duplicate elements
            if i > 0 and nums[i] == nums[i - 1]:
                continue

            left, right = i + 1, len(nums) - 1

            while left < right:
                total = nums[i] + nums[left] + nums[right]

                if total == 0:
                    res.append([nums[i], nums[left], nums[right]])

                    # Skip duplicates for left and right
                    while left < right and nums[left] == nums[left + 1]:
                        left += 1
                    while left < right and nums[right] == nums[right - 1]:
                        right -= 1

                    left += 1
                    right -= 1

                elif total < 0:
                    left += 1  # Need bigger sum
                else:
                    right -= 1  # Need smaller sum

        return res
```

19) 4-Sum Problem.

[Leetcode](https://leetcode.com/problems/4sum/description/)

Code:
```
class Solution:
    def fourSum(self, nums, target):
        nums.sort()
        n = len(nums)
        res = []

        for i in range(n):
            if i > 0 and nums[i] == nums[i - 1]:
                continue  # Skip duplicates for i

            for j in range(i + 1, n):
                if j > i + 1 and nums[j] == nums[j - 1]:
                    continue  # Skip duplicates for j

                left = j + 1
                right = n - 1

                while left < right:
                    total = nums[i] + nums[j] + nums[left] + nums[right]

                    if total == target:
                        res.append([nums[i], nums[j], nums[left], nums[right]])

                        # Skip duplicates for left and right
                        while left < right and nums[left] == nums[left + 1]:
                            left += 1
                        while left < right and nums[right] == nums[right - 1]:
                            right -= 1

                        left += 1
                        right -= 1

                    elif total < target:
                        left += 1
                    else:
                        right -= 1

        return res
```

20) Merge Overlapping Subintervals

[Leetcode](https://leetcode.com/problems/merge-intervals/description/)

Code:
```
class Solution(object):
    def merge(self, intervals):
        """
        :type intervals: List[List[int]]
        :rtype: List[List[int]]
        """
        if not intervals:
            return []
        intervals.sort()
        st=intervals[0]
        ans=[]
        for i in range(1,len(intervals)):
            if st[1] >= intervals[i][0]:
                st[1]=max(st[1],intervals[i][1])
            else:
                ans.append(st)
                st=intervals[i]
        ans.append(st)
        return ans
```

21) Merge two sorted arrays without extra space

[Leetcode](https://leetcode.com/problems/merge-sorted-array/description/)

Code:
```
class Solution(object):
    def merge(self, nums1, m, nums2, n):
        """
        Do not return anything, modify nums1 in-place instead.
        """
        trimmed = nums1[:m]
        merged = trimmed + nums2
        merged.sort()
        for i in range(m + n):
            nums1[i] = merged[i]
```
22) Binary Search to find X in sorted array

[Leetcode](https://leetcode.com/problems/binary-search/description/)

Code:
```
class Solution(object):
    def search(self, nums, target):
        """
        :type nums: List[int]
        :type target: int
        :rtype: int
        """
        st=0
        end=len(nums)-1
        while st<=end:
            mid=(st+end)//2
            if target==nums[mid]:
                return mid
            elif target>nums[mid]:
                st=mid+1
            else:
                end=mid-1
        return -1
```

23) Search Insert Position

[Leetcode](https://leetcode.com/problems/search-insert-position/description/)

Code:
```
class Solution(object):
    def searchInsert(self, nums, target):
        """
        :type nums: List[int]
        :type target: int
        :rtype: int
        """
        st=0
        end=len(nums)-1
        while st<=end:
            mid=(st+end)//2
            if target==nums[mid]:
                return mid
            elif target>nums[mid]:
                st=mid+1
            elif target<nums[mid]:
                end=mid-1
        return st
```

24) Find the first or last occurrence of a given number in a sorted array

[Leetcode](https://leetcode.com/problems/find-first-and-last-position-of-element-in-sorted-array/description/)

Code:
```
class Solution(object):
    def searchRange(self, nums, target):
        """
        :type nums: List[int]
        :type target: int
        :rtype: List[int]
        """
        return [self.binarysearch(nums,target,True),self.binarysearch(nums,target,False)]
    def binarysearch(self,nums,target,First):
        st=0
        end=len(nums)-1
        result=-1
        while st<=end:
            mid=(st+end)//2
            if target>nums[mid]:
                st=mid+1
            elif target<nums[mid]:
                end=mid-1
            elif target==nums[mid]:
                result=mid
                if First:
                    end=mid-1
                else:
                    st=mid+1
        return result
```

25) Search in Rotated Sorted Array I

[Leetcode](https://leetcode.com/problems/search-in-rotated-sorted-array/description/)

Code:
```
class Solution(object):
    def search(self, nums, target):
        left, right = 0, len(nums) - 1
        
        while left <= right:
            mid = (left + right) // 2
            
            if nums[mid] == target:
                return mid

            # Check if the left half is sorted
            if nums[left] <= nums[mid]:
                if nums[left] <= target < nums[mid]:
                    right = mid - 1
                else:
                    left = mid + 1
            # Otherwise, the right half is sorted
            else:
                if nums[mid] < target <= nums[right]:
                    left = mid + 1
                else:
                    right = mid - 1
                    
        return -1

```

26) Search in Rotated Sorted Array II

[Leetcode](https://leetcode.com/problems/search-in-rotated-sorted-array-ii/description/)

Code:
```
class Solution(object):
    def search(self, nums, target):
        st, end = 0, len(nums) - 1
        while st <= end:
            mid = (st + end) // 2
            if nums[mid] == target:
                return True

            # If we can't be sure about the sorted part due to duplicates
            if nums[st] == nums[mid] == nums[end]:
                st += 1
                end -= 1
            # Left half is sorted
            elif nums[st] <= nums[mid]:
                if nums[st] <= target < nums[mid]:
                    end = mid - 1
                else:
                    st = mid + 1
            # Right half is sorted
            else:
                if nums[mid] < target <= nums[end]:
                    st = mid + 1
                else:
                    end = mid - 1
        return False

```

27) Find minimum in Rotated Sorted Array

[Leetcode](https://leetcode.com/problems/find-minimum-in-rotated-sorted-array/)

Code:
```
def findMin(self, nums):
    st, end = 0, len(nums) - 1
        
    while st < end:
        mid = (st + end) // 2
            
        # If mid element is greater than end, the min is in right half
        if nums[mid] > nums[end]:
            st = mid + 1
        else:
            # Min could be at mid or in left half
            end = mid
                
        # Loop ends when st == end, which is the index of the minimum
    return nums[st]
```

Extension of above problem:

Find out how many times has an array been rotated

Code:
```
class Solution:
    def findKRoation(self, nums):
        st, end = 0, len(nums) - 1

        while st < end:
            mid = (st + end) // 2

            # If mid element is greater than end, the min is in right half
            if nums[mid] > nums[end]:
                st = mid + 1
            else:
                # Min could be at mid or in left half
                end = mid

        # Loop ends when st == end, which is the index of the minimum
        return st
```

28) Single element in a Sorted Array

[Leetcode](https://leetcode.com/problems/single-element-in-a-sorted-array/description/)

Code:
```
    def singleNonDuplicate(self, nums):
        st, end = 0, len(nums) - 1
        while st < end:
            mid = (st + end) // 2
            
            # Ensure mid is even for correct pairing
            if mid % 2 == 1:
                mid -= 1
            
            if nums[mid] == nums[mid + 1]:
                st = mid + 2  # move right
            else:
                end = mid  # move left
        
        return nums[st]
```

29) Find peak element

[Leetcode](https://leetcode.com/problems/find-peak-element/description/)

Code:
```
class Solution(object):
    def findPeakElement(self, nums):
        left, right = 0, len(nums) - 1

        while left < right:
            mid = (left + right) // 2
            if nums[mid] < nums[mid + 1]:
                left = mid + 1  # Peak is in the right half
            else:
                right = mid  # Peak is in the left half or at mid

        return left  # or right, both are same here
```

30) Search a 2D Matrix

[Leetcode](https://leetcode.com/problems/search-a-2d-matrix/description/)

Code:

```
class Solution(object):
    def searchMatrix(self, matrix, target):
        if not matrix or not matrix[0]:
            return False

        m, n = len(matrix), len(matrix[0])
        low, high = 0, m * n - 1

        while low <= high:
            mid = (low + high) // 2
            row = mid // n
            col = mid % n
            mid_val = matrix[row][col]

            if mid_val == target:
                return True
            elif mid_val < target:
                low = mid + 1
            else:
                high = mid - 1

        return False
```

31) Count occurrences of a number in a sorted array with duplicates

Code:
```
def o(nums,k):
    def f(nums,k,first):
        st,end=0,len(nums)-1
        ans=-1
        while st<=end:
            mid=(st+end)//2
            if nums[mid]==k:
                ans=mid
                if first:
                    end=mid-1
                else:
                    st=mid+1
            elif nums[mid]<k:
                st=mid+1
            elif nums[mid]>k:
                end=mid-1
        return ans

    s=f(nums,k,True)
    e=f(nums,k,False)
    if s==-1 or e==-1:
        return 0
    else:
        return len(nums[s:e+1])

    
o([0,1,2,3,3,3,4,4,4,4,4,4,4,4,4,9],4)
9
o([1, 2, 3, 5, 6], 4)
0
```
---

32) Find square root of a number in log n

Code:
```
def sq(n):
    low,high=1,n
    ans=1
    while low<=high:
        mid=(low+high)//2
        if mid*mid <= n:
            ans=max(ans,mid)
            low=high+1
        else:
            high=mid-1
    return ans
```

33) Find the Nth root of a number using binary search

Code:
```
def val(root,num,n):
    val=1
    for i in range(root):
        val*=num
        if val>n:
            return 2
    if val==n:
        return 1
    
    return 0

def nroot(root,n):
    low,high=1,n
    while low<=high:
        mid=(low+high)//2
        if val(root,mid,n)== 1:
            return mid
        elif val(root,mid,n)==0:
            low=mid+1
        elif val(root,mid,n)==2:
            high=mid-1
    return -1
```

34) Koko Eating Bananas

[Leetcode link](https://leetcode.com/problems/koko-eating-bananas/description/)

Code:
```
import math

def eat(nums,hour):
    total_hrs=0
    for i in nums:
        total_hrs+=math.ceil(i/hour)
    return total_hrs

def koko_eat(piles,h):
    st=1
    end=max(piles)
    ans=end
    while st<=end:
        mid=(st+end)//2
        if eat(piles,mid)<=h:
            ans=min(mid,ans)
            end=mid-1
        elif eat(piles,mid)>h:
            st=mid+1
    return ans

koko_eat(piles = [3,6,7,11], h = 8)
4
koko_eat(piles = [30,11,23,4,20], h = 5)
30
koko_eat(piles = [30,11,23,4,20], h = 6)
23


class Solution:
    def minEatingSpeed(self, piles, h):
        left, right = 1, max(piles)

        while left < right:
            k = (left + right) // 2
            total_hours = sum((pile + k - 1) // k for pile in piles)

            if total_hours > h:
                left = k + 1  # Too slow
            else:
                right = k     # Try slower

        return left
```


35) Minimum Number of Days to Make m Bouquets

[Leetcode](https://leetcode.com/problems/minimum-number-of-days-to-make-m-bouquets/)

Helper Function Code:
```
#helper function
def can_make(self,nums,m,k,day):
    counter=0
    made=0
    for num in nums:
        if num <= day:
            counter+=1
            if counter >= k:
                made+=1
                counter=0
        else:
            counter=0
        return made>=m

```

Brute Force Solution:
```
#Linear Search Technique (Brute Force)
    def place(Nums,K):
        Nums.sort()
        low,high=Nums[0],Nums[len(Nums)-1]
        if K==2:
            return high-low
        for i in range(1,high-low+1):
            if can_place(Nums,i,K):
                continue
            else:
                return i-1
```

Code (BS):
```
class Solution(object):
    #binary search
    def minDays(self, bloomDay, m, k):
        if m*k > len(bloomDay):
            return -1
        low=min(bloomDay)
        high=max(bloomDay)
        while low<=high:
            mid=(low+high)//2
            if self.can_make(bloomDay,m,k,mid):
                high=mid-1
            else:
                low=mid+1
        return low
```


36) Smallest Divisor Given a threshold

[Leetcode](https://leetcode.com/problems/find-the-smallest-divisor-given-a-threshold/)

Code:

```
    #helper function
    def poss(arr,div,th):
        import math
        c_th=0
        for num in arr:
            c_th+=math.ceil(num/div)
        return c_th<=th

    #Brute Force
    def ls(arr,th):
        mini=max(arr)
        for i in range(min(arr),max(arr)):
            if poss(arr,i,th):
                mini=min(mini,i)
        return mini

    #binary search
    def bs(arr,th):
        low=min(arr)
        high=max(arr)
        while low<=high:
            mid=(low+high)//2
            if poss(arr,mid,th):
                high=mid-1
            else:
                low=mid+1
        return low
```


37) Capacity to shift N pacakages in D days

[Leetcode](https://leetcode.com/problems/capacity-to-ship-packages-within-d-days/)

Code:
```
class Solution(object):
    def shipWithinDays(self, weights, days):
        def ship_day(wt, cap):
            day, load = 1, 0
            for w in wt:
                if load + w > cap:
                    day += 1
                    load = w
                else:
                    load += w
            return day

        low = max(weights)
        high = sum(weights)
        
        while low < high:
            mid = (low + high) // 2
            if ship_day(weights, mid) <= days:
                high = mid
            else:
                low = mid + 1
        return low

    #linear search
    def ls(wt,days):
        for i in range(max(wt),sum(wt)):
            if ship_day(wt,i)==days:
                return i
        return -1
```

38) Kth Missing Positive Number

[LeetCode](https://leetcode.com/problems/kth-missing-positive-number/description/)

Code:
```
class Solution(object):
    def findKthPositive(self, arr, k):
        """
        :type arr: List[int]
        :type k: int
        :rtype: int
        """
        missing = []
        i = 1
        arr_set = set(arr)  # Faster lookup
        while len(missing) < k:
            if i not in arr_set:
                missing.append(i)
            i += 1
        return missing[-1]
```

39) Search a 2D Matrix II

[Leetcode](https://leetcode.com/problems/search-a-2d-matrix-ii/description/)

Code:
```
class Solution(object):
    def searchMatrix(self, matrix, target):
        """
        :type matrix: List[List[int]]
        :type target: int
        :rtype: bool
        """
        if not matrix or not matrix[0]:
            return False
        
        rows = len(matrix)
        cols = len(matrix[0])
        
        # Start from the top-right corner
        row = 0
        col = cols - 1
        
        while row < rows and col >= 0:
            current = matrix[row][col]
            if current == target:
                return True
            elif current > target:
                col -= 1  # move left
            else:
                row += 1  # move down
        
        return False

```

40) Find Peak Element (2D Matrix)

[Link](https://leetcode.com/problems/find-a-peak-element-ii/description/)

Code:
```
class Solution(object):
    def findPeakGrid(self, mat):
        """
        :type mat: List[List[int]]
        :rtype: List[int]
        """
        m, n = len(mat), len(mat[0])
        left, right = 0, n - 1

        while left <= right:
            mid_col = (left + right) // 2

            # Find the row with the max element in mid_col
            max_row = 0
            for i in range(m):
                if mat[i][mid_col] > mat[max_row][mid_col]:
                    max_row = i

            # Get left and right neighbors safely
            left_val = mat[max_row][mid_col - 1] if mid_col - 1 >= 0 else -1
            right_val = mat[max_row][mid_col + 1] if mid_col + 1 < n else -1
            current = mat[max_row][mid_col]

            if current > left_val and current > right_val:
                return [max_row, mid_col]
            elif left_val > current:
                right = mid_col - 1
            else:
                left = mid_col + 1

```

41) Reverse Words in a String.

[leetcode](https://leetcode.com/problems/reverse-words-in-a-string/)

Code:
```
class Solution(object):
    def reverseWords(self, s):
        """
        :type s: str
        :rtype: str
        """
        words = s.split()
        # Step 2: Reverse the list of words
        reversed_words = words[::-1]
        # Step 3: Join the reversed list into a single string with a space
        result = ' '.join(reversed_words)
        return result
        
```


42) Isomorphic Strings

[Leetcode](https://leetcode.com/problems/isomorphic-strings/description/)

Code:
```
def isIsomorphic(s: str, t: str) -> bool:
    if len(s) != len(t):
        return False

    map_s_t = {}
    map_t_s = {}

    for ch_s, ch_t in zip(s, t):
        # Check mapping from s to t
        if ch_s in map_s_t:
            if map_s_t[ch_s] != ch_t:
                return False
        else:
            map_s_t[ch_s] = ch_t

        # Check mapping from t to s
        if ch_t in map_t_s:
            if map_t_s[ch_t] != ch_s:
                return False
        else:
            map_t_s[ch_t] = ch_s

    return True
```

43) Valid Anagram

[leetcode](https://leetcode.com/problems/valid-anagram/description/)

Code:
```
class Solution(object):
    def isAnagram(self, s, t):
        """
        :type s: str
        :type t: str
        :rtype: bool
        """
        if len(s) != len(t):
            return False
        
        count = [0] * 26  # 26 lowercase letters
        
        for ch1, ch2 in zip(s, t):
            count[ord(ch1) - ord('a')] += 1
            count[ord(ch2) - ord('a')] -= 1
        
        return all(c == 0 for c in count)
```


44) Sort Characters By Frequency

[leetcode](https://leetcode.com/problems/sort-characters-by-frequency/description/)

Code:
```
class Solution(object):
    def frequencySort(self, s):
        """
        :type s: str
        :rtype: str
        """
        # Step 1: Count frequency of each character
        freq_map = {}
        for char in s:
            freq_map[char] = freq_map.get(char, 0) + 1
        
        # Step 2: Sort characters based on frequency (descending)
        # sorted returns list of tuples (char, frequency)
        sorted_chars = sorted(freq_map.items(), key=lambda x: x[1], reverse=True)
        
        # Step 3: Build result string
        result = []
        for char, freq in sorted_chars:
            result.append(char * freq)  # repeat char 'freq' times
        
        return "".join(result)

```

45) Maximum Nesting Depth of Paranthesis

[Leetcode](https://leetcode.com/problems/maximum-nesting-depth-of-the-parentheses/description/)

Code:
```
class Solution(object):
    def maxDepth(self, s):
        """
        :type s: str
        :rtype: int
        """
        current_depth = 0
        max_depth = 0
        
        for char in s:
            if char == '(':
                current_depth += 1
                max_depth = max(max_depth, current_depth)
            elif char == ')':
                current_depth -= 1
        
        return max_depth

```


46) Roman to Integer

[leetcode](https://leetcode.com/problems/roman-to-integer/description/)

Code:
```
class Solution(object):
    def romanToInt(self, s):
        """
        :type s: str
        :rtype: int
        """
        values = {
            'I': 1, 'V': 5, 'X': 10, 'L': 50,
            'C': 100, 'D': 500, 'M': 1000
        }
        total = 0
        for i in range(len(s)):
            # If current value is less than next value → subtract
            if i + 1 < len(s) and values[s[i]] < values[s[i + 1]]:
                total -= values[s[i]]
            else:
                total += values[s[i]]
        return total
```


47) String to Integer (atoi)

[Leetcode](https://leetcode.com/problems/string-to-integer-atoi/)

Code:
```
class Solution(object):
    def myAtoi(self, s):
        """
        :type s: str
        :rtype: int
        """
        # Step 1: Remove leading whitespace
        s = s.lstrip()
        if not s:
            return 0
        
        # Step 2: Check for sign
        sign = 1
        index = 0
        if s[0] == '-':
            sign = -1
            index += 1
        elif s[0] == '+':
            index += 1
        
        # Step 3: Read digits
        num = 0
        while index < len(s) and s[index].isdigit():
            num = num * 10 + int(s[index])
            index += 1
        
        # Step 4: Apply sign
        num *= sign
        
        # Step 5: Clamp to 32-bit signed integer range
        INT_MIN = -2**31
        INT_MAX = 2**31 - 1
        if num < INT_MIN:
            return INT_MIN
        if num > INT_MAX:
            return INT_MAX
        
        return num

```

48) Longest Palindromic Substring

[Leetcode](https://leetcode.com/problems/longest-palindromic-substring/description/)

Code:
```
class Solution(object):
    def longestPalindrome(self, s):
        """
        :type s: str
        :rtype: str
        """
        if not s or len(s) < 1:
            return ""

        start, end = 0, 0

        def expandAroundCenter(left, right):
            while left >= 0 and right < len(s) and s[left] == s[right]:
                left -= 1
                right += 1
            return left + 1, right - 1  # return valid bounds

        for i in range(len(s)):
            # Odd-length palindrome
            l1, r1 = expandAroundCenter(i, i)
            # Even-length palindrome
            l2, r2 = expandAroundCenter(i, i + 1)

            # Pick the longer one
            if r1 - l1 > end - start:
                start, end = l1, r1
            if r2 - l2 > end - start:
                start, end = l2, r2

        return s[start:end + 1]

```


49) Sum of Beauty of All Substrings

[leetcode](https://leetcode.com/problems/sum-of-beauty-of-all-substrings/description/)


Code:
```
class Solution(object):
    def beautySum(self, s):
        """
        :type s: str
        :rtype: int
        """
        n = len(s)
        total_beauty = 0

        # Iterate over all starting points
        for i in range(n):
            freq = [0] * 26  # frequency of each character
            # Expand substring from i to j
            for j in range(i, n):
                freq[ord(s[j]) - ord('a')] += 1

                max_freq = 0
                min_freq = float('inf')

                # Find max and min freq among non-zero counts
                for f in freq:
                    if f > 0:
                        max_freq = max(max_freq, f)
                        min_freq = min(min_freq, f)

                total_beauty += (max_freq - min_freq)

        return total_beauty

```


### III) Hard Probles:

1) Maximum Product Subarray

[Leetcode](https://leetcode.com/problems/maximum-product-subarray/description/)

Code:
```
class Solution(object):
    def maxProduct(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """

        if not nums:
            return 0

        max_prod = min_prod = result = nums[0]

        for num in nums[1:]:
            if num < 0:
                max_prod, min_prod = min_prod, max_prod

            max_prod = max(num, num * max_prod)
            min_prod = min(num, num * min_prod)

            result = max(result, max_prod)

        return result
```

2) Reverse Pairs

[Leetcode](https://leetcode.com/problems/reverse-pairs/description/)

Code:
```
class Solution(object):
    def reversePairs(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """

        def merge_sort(start, end):
            if start >= end:
                return 0
            mid = (start + end) // 2
            count = merge_sort(start, mid) + merge_sort(mid + 1, end)
            
            # Count reverse pairs
            j = mid + 1
            for i in range(start, mid + 1):
                while j <= end and nums[i] > 2 * nums[j]:
                    j += 1
                count += j - (mid + 1)
            
            # Merge the two sorted halves
            temp = []
            left, right = start, mid + 1
            while left <= mid and right <= end:
                if nums[left] <= nums[right]:
                    temp.append(nums[left])
                    left += 1
                else:
                    temp.append(nums[right])
                    right += 1
            while left <= mid:
                temp.append(nums[left])
                left += 1
            while right <= end:
                temp.append(nums[right])
                right += 1
            
            # Copy sorted elements back to original array
            nums[start:end+1] = temp
            return count

        return merge_sort(0, len(nums) - 1)
```

3) The Number Pattern

[Link](https://www.naukri.com/code360/problems/ninja-and-the-number-pattern-i_6581959?utm_source=youtube&utm_medium=affiliate&utm_campaign=striver_patternproblems)

Code:
```
def getNumberPattern(n: int) -> None:
    # Write your solution here.
    size = 2 * n - 1  # Define the size of the square matrix

    for i in range(size):
        for j in range(size):
            # Compute value based on the minimum distance to the border
            value = n - min(i, j, size - 1 - i, size - 1 - j)
            print(value, end="")  # Print value without spaces
        print()  # Move to next line
    pass

```

4) The Star Pattern I

[Link](https://www.naukri.com/code360/problems/ninja-and-the-star-pattern-i_6581920?utm_source=youtube&utm_medium=affiliate&utm_campaign=striver_patternproblems)

Code:

```
def getStarPattern(n: int) -> None:
    # Write your solution here.
    for i in range(1,n+1):
        for j in range(1,n+1):
            if i==1 or i==n or j==1 or j==n:
                print("*",end="")
            else:
                print(" ",end="")
        print()


    pass
```

5) Find out how many times the array has been rotated

[Link](https://takeuforward.org/arrays/find-out-how-many-times-the-array-has-been-rotated/)

6) Symmetry

[Link](https://www.naukri.com/code360/problems/symmetry_6581914?utm_source=youtube&utm_medium=affiliate&utm_campaign=striver_patternproblems)

Code:
```
def symmetry(n: int):
    # Upper half including the middle row
    spaces = 2 * (n - 1)
    for i in range(1, n + 1):
        # Print left stars
        print("* " * i, end="")
        
        # Print spaces
        print("  " * spaces, end="")
        
        # Print right stars
        if i != n:
            print("* " * i)
        else:
            print("* " * (i - 1) + "*")
        
        spaces -= 2
    
    # Lower half
    spaces = 2
    for i in range(n - 1, 0, -1):
        # Print left stars
        print("* " * i, end="")
        
        # Print spaces
        print("  " * spaces, end="")
        
        # Print right stars
        print("* " * i)
        
        spaces += 2
```

7) Median-of-two-sorted-arrays

[Leetcode](https://leetcode.com/problems/median-of-two-sorted-arrays/)

Code:
```
class Solution:
    def findMedianSortedArrays(self, nums1, nums2):
        if len(nums1) > len(nums2):
            nums1, nums2 = nums2, nums1

        m, n = len(nums1), len(nums2)
        low, high = 0, m

        while low <= high:
            i = (low + high) // 2
            j = (m + n + 1) // 2 - i

            maxLeft1 = float('-inf') if i == 0 else nums1[i - 1]
            minRight1 = float('inf') if i == m else nums1[i]

            maxLeft2 = float('-inf') if j == 0 else nums2[j - 1]
            minRight2 = float('inf') if j == n else nums2[j]

            if maxLeft1 <= minRight2 and maxLeft2 <= minRight1:
                if (m + n) % 2 == 0:
                    return (max(maxLeft1, maxLeft2) + min(minRight1, minRight2)) / 2.0
                else:
                    return float(max(maxLeft1, maxLeft2))
            elif maxLeft1 > minRight2:
                high = i - 1
            else:
                low = i + 1
```

8) Split array - Largest Sum

[LeetCode](https://leetcode.com/problems/split-array-largest-sum/)

Code:
```
class Solution(object):
    def FindStd(self,nums,pages):
        std,pgStd=1,0
        for i in range(len(nums)):
            if pgStd+nums[i]<=pages:
                pgStd+=nums[i]
            else:
                std+=1
                pgStd=nums[i]
                
        return std

    def splitArray(self, nums, k):
        """
        :type nums: List[int]
        :type k: int
        :rtype: int
        """
        if k>len(nums):
            return -1

        low,high=max(nums),sum(nums)
        while(low<=high):
            mid=(low+high)//2
            numStd=self.FindStd(nums,mid)
            if numStd>k:
                low=mid+1
            else:
                high=mid-1
        return low
```

9) Minimize Max Distance to Gas Station

[Link](https://takeuforward.org/plus/dsa/problems/minimise-max-distance-to-gas-stations)

Code:
```
import math

class Solution:
    def minimiseMaxDistance(self, arr, k):
        n = len(arr)
        
        # Helper function to check if a given distance d is possible
        def can_place(d):
            count = 0
            for i in range(n - 1):
                gap = arr[i + 1] - arr[i]
                # Number of stations needed for this gap
                count += math.floor(gap / d)
                if gap % d == 0:
                    count -= 1  # adjust for exact split
            return count <= k
        
        # Binary search
        left, right = 0, arr[-1] - arr[0]  # smallest and largest possible distances
        precision = 1e-6  # precision up to 5 decimal places
        
        while right - left > precision:
            mid = (left + right) / 2
            if can_place(mid):
                right = mid
            else:
                left = mid
                
        return round(right, 5)
```

10) Median of Two Sorted Arrays

[Leetcode](https://leetcode.com/problems/median-of-two-sorted-arrays/description/)

Code:
```
class Solution:
    def findMedianSortedArrays(self, nums1, nums2):
        n1, n2 = len(nums1), len(nums2)
        n = n1 + n2
        ind1, ind2 = n // 2 - 1, n // 2

        i = j = cnt = 0
        elem1 = elem2 = 0

        while cnt <= ind2:
            if i < n1 and (j >= n2 or nums1[i] <= nums2[j]):
                val = nums1[i]
                i += 1
            else:
                val = nums2[j]
                j += 1

            if cnt == ind1:
                elem1 = val
            if cnt == ind2:
                elem2 = val
            cnt += 1

        if n % 2 == 0:
            return (elem1 + elem2) / 2.0
        else:
            return elem2 * 1.0

```

11) Aggressive Cows

[Link](https://takeuforward.org/plus/dsa/problems/aggressive-cows)

Helper Function Code:
```
class Solution:
    def can_place(self,Nums,dist,cows):
        cow=1
        prev=Nums[0]
        for i in range(1,len(Nums)):
            if Nums[i]-prev >= dist:
                cow+=1
                prev=Nums[i]
            if cow>=cows:
                return True
        return False
```

Brute Force Solution Code:
```
def place(Nums,K):
    Nums.sort()
    low,high=Nums[0],Nums[len(Nums)-1]
    if K==2:
        return high-low
    for i in range(1,high-low+1):
        if can_place(Nums,i,K):
            continue
        else:
            return i-1
```

Optimal Solution(BS):
```
class Solution:
    def aggressiveCows(self, nums, k):
        Nums.sort()
        st,end=Nums[0],Nums[len(Nums)-1]
        if K==2:
            return end-st
        low,high=1,end-st
        while low<=high:
            mid=(low+high)//2
            if self.can_place(Nums,mid,K):
                low=mid+1
            else:
                high=mid-1
        return high
```

`Note : Will update within 24 hours`

---
## 📌 License

Fell free to use, modify, and share with attribution.

Connect with me on my [LinkedIn](www.linkedin.com/in/sahilshaikh110205)
