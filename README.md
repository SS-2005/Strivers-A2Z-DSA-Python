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

#### 9)Sorting Techniques:
<br>

#### **Selection Sort** :
  
Selection Sort is a simple comparison-based sorting algorithm. It divides the list into two parts:

  * The sorted part at the beginning

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

✅ Advantages

 * Very simple and intuitive
    
 * Efficient for small datasets
    
 * Adaptive: fast for nearly sorted data
    
 * In-place and stable
    
 * Works well when insertion cost is low

❌ Disadvantages

 * Inefficient for large datasets
 * O(n²) time complexity in worst case
<br>

#### **Bubble sort:**

🔹 Introduction:
Bubble Sort is a simple comparison-based sorting algorithm. It works by repeatedly swapping adjacent elements if they are in the wrong order. It continues this process until the array is sorted.

✅ Advantages:

 *  Very simple to implement
 * Stable sorting algorithm
 *  Works well on nearly sorted arrays
 * No extra memory needed (in-place)

❌ Disadvantages:

 * Very slow for large datasets
 * Inefficient compared to other O(n²) sorts like insertion sort

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
Merge Sort is a divide-and-conquer algorithm. It divides the array into halves, recursively sorts them, and then merges the sorted halves to produce the final sorted array.

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

 * Not stable by default
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

11) Second Largest Element in an Array without sorting

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

12) Check if the array is sorted

Code:
```
def IsSorted(arr):
    return arr==sorted(arr)
```

13) Remove duplicates from Sorted array

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


  *<br>
 ***<br>
*****<br>

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


*****<br>
 ***<br>
  *<br>

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

1         1<br>
1 2     2 1<br>
1 2 3 3 2 1<br>

[Link](https://www.naukri.com/code360/problems/number-crown_6581894)

Code:
```
def numberCrown(n: int) -> None:
    # Write your solution here.
    line = []
    space = 2 * n - 2

    for i in range(1, n + 1):
        line.clear()  # Clear list at the start of each row

        # First sequence (left half)
        for j in range(1, i + 1):
            s = "{} ".format(j)
            line.append(s)
            print(s, end="")

        # Spaces in between
        for j in range(space):
            print(" ", end="")
        space = space - 2

        # Second sequence (right half - reverse order)
        for j in range(i, 0, -1):
            print(j, end=" ")
        
        print()  # Move to the next line
    pass
```

3) Find the number that appears once, and other numbers twice.

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


### III) Hard Probles:

`Note : Will Update within 24 Hours`

---
## 📌 License

fell free to use, modify, and share with attribution.

Connect with me on my [LinkedIn](www.linkedin.com/in/sahilshaikh110205)
