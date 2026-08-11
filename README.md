<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:4facfe,50:00f2fe,100:43e97b&height=250&section=header&text=Smallest%20Missing%20Integer&fontSize=42&fontColor=ffffff&animation=fadeIn&fontAlignY=38&desc=LeetCode%20Easy%20%7C%20Java%20Solution&descAlignY=58"/>

<p align="center">

<img src="https://readme-typing-svg.herokuapp.com?font=Poppins&weight=700&size=24&duration=3000&pause=800&color=00C2FF&center=true&vCenter=true&width=900&lines=LeetCode+Easy+Solution;HashSet+%2B+Sequential+Prefix;Time+Complexity+%3A+O(n);Space+Complexity+%3A+O(n);Clean+and+Optimal+Java+Solution"/>

</p>

<p align="center">
<img src="https://img.shields.io/badge/Language-Java-orange?style=for-the-badge&logo=openjdk">
<img src="https://img.shields.io/badge/Time-O(n)-brightgreen?style=for-the-badge">
<img src="https://img.shields.io/badge/Space-O(n)-blue?style=for-the-badge">
<img src="https://img.shields.io/badge/Difficulty-Easy-success?style=for-the-badge">
</p>

</div>

---

# ✨ Problem Overview

Given an integer array **nums**, determine:

- 📌 The **longest sequential prefix**
- ➕ Compute its **sum**
- 🔍 Find the **smallest missing integer** greater than or equal to that sum.

---

# 🎯 Approach

```text
Start
   │
   ▼
Find Longest Sequential Prefix
   │
   ▼
Calculate Prefix Sum
   │
   ▼
Store Array Elements in HashSet
   │
   ▼
Start from Prefix Sum
   │
   ▼
Present in Set?
 ┌───────┴────────┐
 │                │
Yes              No
 │                │
Increment      Return Answer
 │
 └───────────────►
```

---

# 🚀 Java Solution

```java
import java.util.*;

class Solution {
    public int missingInteger(int[] nums) {
        int sum = nums[0];

        // Find sum of longest sequential prefix
        for (int i = 1; i < nums.length; i++) {
            if (nums[i] == nums[i - 1] + 1) {
                sum += nums[i];
            } else {
                break;
            }
        }

        HashSet<Integer> set = new HashSet<>();

        for (int num : nums) {
            set.add(num);
        }

        while (set.contains(sum)) {
            sum++;
        }

        return sum;
    }
}
```

---

# 📊 Complexity Analysis

| Operation | Complexity |
|-----------|------------|
| Prefix Traversal | **O(n)** |
| HashSet Creation | **O(n)** |
| Missing Integer Search | **O(n)** (Worst Case) |

### Overall

- ⏱️ **Time:** `O(n)`
- 💾 **Space:** `O(n)`

---

<div align="center">

### ⭐ If this solution helped you, consider giving it a star!

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:43e97b,100:38f9d7&height=120&section=footer"/>

</div>
