# Difference Between Permutation, Combination, and Subset in Java

## **1. Permutation (Order Matters)**
- A **permutation** is an arrangement of elements where **order matters**.
- **Formula:**  
  \[
  P(n, r) = \frac{n!}{(n-r)!}
  \]
  where `n` is the total elements, and `r` is the number of selected elements.
- **Example:** Given `{A, B, C}`, permutations of length 2 are:
  - `{A, B}`, `{A, C}`, `{B, A}`, `{B, C}`, `{C, A}`, `{C, B}`

### **Java Code for Permutations**
```
    public List<List<Integer>> permute(int[] nums) {
        List<List<Integer>> ans = new ArrayList<>();
        List<Integer> al = new ArrayList<>();
        permutation(nums.length, nums, al, new boolean[nums.length], ans);
        return ans;
    }

    private void permutation(int n, int[] arr, List<Integer> al, boolean[] vis, List<List<Integer>> ans) {
        if (al.size() == n) {
            List<Integer> temp = new ArrayList<>(al);
            ans.add(temp);
            return;
        }
        for (int i = 0; i < n; i++) {
            if (vis[i] == false) {
                vis[i] = true;
                // pick
                al.add(arr[i]);
                permutation(n, arr, al, vis, ans);
                // not pick
                al.remove(al.size() - 1);
                permutation(n, arr, al, vis, ans);
                vis[i] = false;
            }
        }
    }
```
---

## **2. Combination (Order Does Not Matter)**
- A **combination** selects elements where **order does not matter**.
- **Formula:**  
  \[
  C(n, r) = \frac{n!}{r!(n-r)!}
  \]
- **Example:** Given `{A, B, C}`, combinations of length 2 are:
  - `{A, B}`, `{A, C}`, `{B, C}`

### **Java Code for Combinations**
```
    public List<List<Integer>> combine(int n, int k) {
        List<Integer> al = new ArrayList<>();
        List<List<Integer>> ans = new ArrayList<>();
        combinations(1, n, k, al, ans);
        return ans;
    }

    private void combinations(int start, int n, int k, List<Integer> al, List<List<Integer>> ans) {
        if (k == 0) {
            List<Integer> temp = new ArrayList<>(al);
            ans.add(temp);
            return;
        }
        if (start > n) return;

        // Pick the element.
        al.add(start);
        combinations(start + 1, n, k - 1, al, ans);

        // Don't pick the element.
        al.remove(al.size() - 1);
        combinations(start + 1, n, k, al, ans);
    }
```

### **combinations code using for loop**

```
    public List<List<Integer>> combine(int n, int k) {
        List<Integer> al = new ArrayList<>();
        List<List<Integer>> ans = new ArrayList<>();
        combinations(1, n, k, al, ans);
        return ans;
    }

    private void combinations(int start, int n, int k, List<Integer> al, List<List<Integer>> ans) {
        if (k == 0) {
            List<Integer> temp = new ArrayList<>(al);
            ans.add(temp);
        }

        for (int i = start; i <= n; i++) {
            al.add(i);
            combinations(i + 1, n, k - 1, al, ans);
            al.remove(al.size() - 1);
        }
    }
```
---

## **3. Subset (All Possible Selections)**
- A **subset/subsequence** is any selection of elements (including empty and full set).
- **Total subsets for `n` elements:** \( 2^n \)
- **order of elements matter i.e. if ABC is the sequence then A must appear B and C in the subset/subsequence**
- **They are non contiguous** 

- **Example:** Given `{A, B, C}`, subsets are:
  - `{}`, `{A}`, `{B}`, `{C}`, `{A, B}`, `{A, C}`, `{B, C}`, `{A, B, C}`

### **Java Code for Subsets**
```
    public List<List<Integer>> subsets(int[] nums) {
        int n = nums.length;
        List<Integer> al = new ArrayList<>();
        List<List<Integer>> ans = new ArrayList<>();
        subsets(0, n, al, ans, nums);
        return ans;
    }

    private void subsets(int idx, int n, List<Integer> al, List<List<Integer>> ans, int[] nums) {
        if (idx == n) {
            List<Integer> temp = new ArrayList<>(al);
            ans.add(temp);
            return;
        }
        // Pick the element.
        al.add(nums[idx]);
        subsets(idx + 1, n, al, ans, nums);

        // Don't pick the element.
        al.remove(al.size() - 1);
        subsets(idx + 1, n, al, ans, nums);
    }
```

### **subset code using for loop**

```
    public List<List<Integer>> subsets(int[] nums) {
        int n = nums.length;
        List<Integer> al = new ArrayList<>();
        List<List<Integer>> ans = new ArrayList<>();
        subsets(0, n, al, ans, nums);
        return ans;
    }

    private void subsets(int idx, int n, List<Integer> al, List<List<Integer>> ans, int[] nums) {
        List<Integer> temp = new ArrayList<>(al);
        ans.add(temp);
        // using loop
        for (int i = idx; i < n; i++) {
            al.add(nums[i]);
            subsets(i + 1, n, al, ans, nums);
            al.remove(al.size() - 1);
        }
    }
```

-----------------------------------------------------------------------------------------------------------
## **Key Differences**
| Concept      | Order Matters | Formula                          | Example Output (for `ABC` with `r=2`) |
|-------------|--------------|--------------------------------|--------------------------------|
| **Permutation** | ✅ Yes        | \( P(n, r) = \frac{n!}{(n-r)!} \) | `{A, B}`, `{A, C}`, `{B, A}`, `{B, C}`, `{C, A}`, `{C, B}` |
| **Combination** | ❌ No        | \( C(n, r) = \frac{n!}{r!(n-r)!} \) | `{A, B}`, `{A, C}`, `{B, C}` |
| **Subset**    | ❌ No        | \( 2^n \)                      | `{}`, `{A}`, `{B}`, `{C}`, `{A, B}`, `{A, C}`, `{B, C}`, `{A, B, C}` |

---

## **Conclusion**
- Use **permutations** when order **matters**.
- Use **combinations** when order **does not matter**.
- Use **subsets** to generate **all possible selections**.
