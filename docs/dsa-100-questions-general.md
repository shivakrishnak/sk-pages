---
layout: default
title: Dsa100
nav_order: 11
---

100 High-ROI DSA Questions, Grouped by Pattern — General Interview Reference
Assume standard ListNode{val,next} and TreeNode{val,left,right} classes are defined.

PATTERN: TWO POINTERS

**1. Two Sum II (sorted array)**
**BF:** check every pair with nested loop - O(n^2)
**Opt:** two pointers from both ends, move based on sum vs target - O(n)
```java
public int[] twoSum(int[] nums, int target) {
    int l=0, r=nums.length-1;
    while (l<r) {
        int sum = nums[l]+nums[r];              // current pair sum
        if (sum==target) return new int[]{l,r}; // match found
        else if (sum<target) l++;               // need larger sum
        else r--;                               // need smaller sum
    }
    return new int[]{-1,-1};
}
```

**2. Valid Palindrome**
**BF:** reverse string and compare - O(n) extra space
**Opt:** two pointers converge, skip non-alphanumeric - O(n), O(1) space
```java
public boolean isPalindrome(String s) {
    int l=0, r=s.length()-1;
    while (l<r) {
        while (l<r && !Character.isLetterOrDigit(s.charAt(l))) l++; // skip junk
        while (l<r && !Character.isLetterOrDigit(s.charAt(r))) r--; // skip junk
        if (Character.toLowerCase(s.charAt(l)) != Character.toLowerCase(s.charAt(r))) return false; // mismatch
        l++; r--;
    }
    return true;
}
```

**3. Container With Most Water**
**BF:** check every pair of lines - O(n^2)
**Opt:** two pointers, move the shorter line inward - O(n)
```java
public int maxArea(int[] height) {
    int l=0, r=height.length-1, max=0;
    while (l<r) {
        int area = Math.min(height[l],height[r]) * (r-l); // width * shorter height
        max = Math.max(max, area);
        if (height[l]<height[r]) l++; else r--;            // move shorter side
    }
    return max;
}
```

**4. 3Sum**
**BF:** three nested loops, check triplets sum to 0 - O(n^3)
**Opt:** sort, fix one element, two-pointer for remaining pair - O(n^2)
```java
public List<List<Integer>> threeSum(int[] nums) {
    Arrays.sort(nums);                             // enables two-pointer + dup skip
    List<List<Integer>> res = new ArrayList<>();
    for (int i=0;i<nums.length-2;i++) {
        if (i>0 && nums[i]==nums[i-1]) continue;   // skip dup fixed element
        int l=i+1, r=nums.length-1;
        while (l<r) {
            int sum = nums[i]+nums[l]+nums[r];
            if (sum==0) {
                res.add(Arrays.asList(nums[i],nums[l],nums[r]));
                while (l<r && nums[l]==nums[l+1]) l++; // skip dup
                while (l<r && nums[r]==nums[r-1]) r--; // skip dup
                l++; r--;
            } else if (sum<0) l++; else r--;
        }
    }
    return res;
}
```

**5. Remove Duplicates from Sorted Array**
**BF:** use a set, copy back - O(n) extra space
**Opt:** slow-fast pointer, overwrite in place - O(1) space
```java
public int removeDuplicates(int[] nums) {
    int slow=0;
    for (int fast=1; fast<nums.length; fast++) {
        if (nums[fast]!=nums[slow]) {          // new unique value found
            slow++;
            nums[slow]=nums[fast];             // write forward
        }
    }
    return slow+1;
}
```

**6. Trapping Rain Water**
**BF:** for each index find max-left and max-right by scanning - O(n^2)
**Opt:** two pointers with running leftMax/rightMax - O(n), O(1) space
```java
public int trap(int[] height) {
    int l=0, r=height.length-1, leftMax=0, rightMax=0, water=0;
    while (l<r) {
        if (height[l]<height[r]) {
            leftMax = Math.max(leftMax, height[l]);  // best wall so far from left
            water += leftMax - height[l];             // water trapped at l
            l++;
        } else {
            rightMax = Math.max(rightMax, height[r]); // best wall so far from right
            water += rightMax - height[r];
            r--;
        }
    }
    return water;
}
```

**7. Sort Colors (Dutch National Flag)**
**BF:** count sort by counting 0s/1s/2s then overwrite - two passes
**Opt:** single pass, three pointers (low, mid, high) - O(n), one pass
```java
public void sortColors(int[] nums) {
    int low=0, mid=0, high=nums.length-1;
    while (mid<=high) {
        if (nums[mid]==0) { swap(nums,low++,mid++); }      // 0 goes to front
        else if (nums[mid]==1) { mid++; }                  // 1 stays in place
        else { swap(nums,mid,high--); }                    // 2 goes to back, recheck mid
    }
}
private void swap(int[] a,int i,int j){int t=a[i];a[i]=a[j];a[j]=t;}
```

**8. Merge Sorted Array (nums1 has extra space at end)**
**BF:** merge into new array, copy back - O(n+m) extra space
**Opt:** fill from the back with three pointers - O(1) space
```java
public void merge(int[] nums1, int m, int[] nums2, int n) {
    int i=m-1, j=n-1, k=m+n-1;
    while (j>=0) {
        if (i>=0 && nums1[i]>nums2[j]) nums1[k--]=nums1[i--]; // larger from nums1
        else nums1[k--]=nums2[j--];                            // larger from nums2
    }
}
```

PATTERN: SLIDING WINDOW

**9. Longest Substring Without Repeating Characters**
**BF:** check every substring for uniqueness - O(n^3)
**Opt:** expanding window, hashmap of last seen index - O(n)
```java
public int lengthOfLongestSubstring(String s) {
    Map<Character,Integer> last = new HashMap<>();
    int start=0, max=0;
    for (int end=0; end<s.length(); end++) {
        char c = s.charAt(end);
        if (last.containsKey(c) && last.get(c)>=start) start = last.get(c)+1; // shrink past dup
        last.put(c,end);
        max = Math.max(max, end-start+1);
    }
    return max;
}
```

**10. Maximum Sum Subarray of Size K**
**BF:** recompute sum for every window of size k - O(n*k)
**Opt:** fixed-size sliding window, add new/subtract old - O(n)
```java
public int maxSumSubarray(int[] nums, int k) {
    int sum=0, max=0;
    for (int i=0;i<nums.length;i++) {
        sum += nums[i];                       // add new element
        if (i>=k) sum -= nums[i-k];            // remove element leaving window
        if (i>=k-1) max = Math.max(max,sum);
    }
    return max;
}
```

**11. Longest Substring with At Most K Distinct Characters**
**BF:** try every substring, count distinct chars - O(n^2)
**Opt:** expanding window with frequency map, shrink when distinct>k - O(n)
```java
public int lengthOfLongestSubstringKDistinct(String s, int k) {
    Map<Character,Integer> freq = new HashMap<>();
    int start=0, max=0;
    for (int end=0; end<s.length(); end++) {
        freq.merge(s.charAt(end),1,Integer::sum);      // add char
        while (freq.size()>k) {
            char c = s.charAt(start);
            freq.put(c, freq.get(c)-1);                // shrink from left
            if (freq.get(c)==0) freq.remove(c);
            start++;
        }
        max = Math.max(max, end-start+1);
    }
    return max;
}
```

**12. Minimum Window Substring**
**BF:** check every substring for containing all chars of t - O(n^2) or worse
**Opt:** expand window till valid, shrink to minimize, freq map + count - O(n)
```java
public String minWindow(String s, String t) {
    Map<Character,Integer> need = new HashMap<>();
    for (char c: t.toCharArray()) need.merge(c,1,Integer::sum);
    Map<Character,Integer> window = new HashMap<>();
    int required = need.size(), formed=0, start=0, minLen=Integer.MAX_VALUE, minStart=0;
    int l=0;
    for (int r=0;r<s.length();r++) {
        char c = s.charAt(r);
        window.merge(c,1,Integer::sum);
        if (need.containsKey(c) && window.get(c).intValue()==need.get(c).intValue()) formed++; // satisfied one char
        while (formed==required) {                     // shrink while still valid
            if (r-l+1<minLen) { minLen=r-l+1; minStart=l; }
            char lc = s.charAt(l);
            window.put(lc, window.get(lc)-1);
            if (need.containsKey(lc) && window.get(lc)<need.get(lc)) formed--;
            l++;
        }
    }
    return minLen==Integer.MAX_VALUE ? "" : s.substring(minStart, minStart+minLen);
}
```

**13. Longest Repeating Character Replacement**
**BF:** try every substring, check if replaceable within k changes - O(n^2)
**Opt:** window valid when (length - maxFreqChar) <= k, track max freq - O(n)
```java
public int characterReplacement(String s, int k) {
    int[] count = new int[26];
    int start=0, maxCount=0, max=0;
    for (int end=0; end<s.length(); end++) {
        count[s.charAt(end)-'A']++;
        maxCount = Math.max(maxCount, count[s.charAt(end)-'A']); // most frequent char in window
        while (end-start+1-maxCount > k) {              // too many chars to replace
            count[s.charAt(start)-'A']--;
            start++;
        }
        max = Math.max(max, end-start+1);
    }
    return max;
}
```

**14. Fruit Into Baskets (longest subarray with at most 2 distinct)**
**BF:** check every subarray for distinct count <=2 - O(n^2)
**Opt:** sliding window with freq map, shrink when distinct>2 - O(n)
```java
public int totalFruit(int[] fruits) {
    Map<Integer,Integer> freq = new HashMap<>();
    int start=0, max=0;
    for (int end=0; end<fruits.length; end++) {
        freq.merge(fruits[end],1,Integer::sum);
        while (freq.size()>2) {
            int f = fruits[start];
            freq.put(f, freq.get(f)-1);
            if (freq.get(f)==0) freq.remove(f);         // basket type exhausted
            start++;
        }
        max = Math.max(max, end-start+1);
    }
    return max;
}
```

**15. Sliding Window Maximum**
**BF:** scan max in every window of size k - O(n*k)
**Opt:** deque holding indices, keep decreasing values only - O(n)
```java
public int[] maxSlidingWindow(int[] nums, int k) {
    Deque<Integer> dq = new ArrayDeque<>();    // stores indices, values decreasing
    int[] res = new int[nums.length-k+1];
    for (int i=0;i<nums.length;i++) {
        if (!dq.isEmpty() && dq.peekFirst()<=i-k) dq.pollFirst(); // out of window
        while (!dq.isEmpty() && nums[dq.peekLast()]<nums[i]) dq.pollLast(); // remove smaller
        dq.offerLast(i);
        if (i>=k-1) res[i-k+1] = nums[dq.peekFirst()]; // front is max
    }
    return res;
}
```

PATTERN: HASHING / PREFIX SUM

**16. Two Sum (unsorted array)**
**BF:** check every pair - O(n^2)
**Opt:** hashmap store value->index, check complement - O(n)
```java
public int[] twoSum(int[] nums, int target) {
    Map<Integer,Integer> map = new HashMap<>();
    for (int i=0;i<nums.length;i++) {
        int comp = target-nums[i];
        if (map.containsKey(comp)) return new int[]{map.get(comp),i}; // pair found
        map.put(nums[i],i);
    }
    return new int[]{-1,-1};
}
```

**17. Group Anagrams**
**BF:** compare every string with every other for anagram match - O(n^2 * k)
**Opt:** hashmap keyed by sorted string - O(n * k log k)
```java
public List<List<String>> groupAnagrams(String[] strs) {
    Map<String,List<String>> groups = new HashMap<>();
    for (String s: strs) {
        char[] c = s.toCharArray();
        Arrays.sort(c);                                  // canonical key
        groups.computeIfAbsent(new String(c), k->new ArrayList<>()).add(s);
    }
    return new ArrayList<>(groups.values());
}
```

**18. Subarray Sum Equals K**
**BF:** check sum of every subarray - O(n^2)
**Opt:** prefix sum + hashmap of prefix frequencies - O(n)
```java
public int subarraySum(int[] nums, int k) {
    Map<Integer,Integer> prefixCount = new HashMap<>();
    prefixCount.put(0,1);                        // empty prefix
    int sum=0, count=0;
    for (int n: nums) {
        sum += n;
        count += prefixCount.getOrDefault(sum-k,0); // subarrays ending here summing to k
        prefixCount.merge(sum,1,Integer::sum);
    }
    return count;
}
```

**19. Longest Consecutive Sequence**
**BF:** sort array, scan for consecutive runs - O(n log n)
**Opt:** hashset, only start counting from sequence starts - O(n)
```java
public int longestConsecutive(int[] nums) {
    Set<Integer> set = new HashSet<>();
    for (int n: nums) set.add(n);
    int max=0;
    for (int n: set) {
        if (!set.contains(n-1)) {               // n is start of a sequence
            int len=1;
            while (set.contains(n+len)) len++;
            max = Math.max(max,len);
        }
    }
    return max;
}
```

**20. Top K Frequent Elements**
**BF:** sort by frequency - O(n log n)
**Opt:** hashmap of freq + min-heap of size k - O(n log k)
```java
public int[] topKFrequent(int[] nums, int k) {
    Map<Integer,Integer> freq = new HashMap<>();
    for (int n: nums) freq.merge(n,1,Integer::sum);
    PriorityQueue<Integer> heap = new PriorityQueue<>((a,b)->freq.get(a)-freq.get(b)); // min-heap by freq
    for (int key: freq.keySet()) {
        heap.offer(key);
        if (heap.size()>k) heap.poll();         // drop least frequent
    }
    int[] res = new int[k];
    for (int i=k-1;i>=0;i--) res[i]=heap.poll();
    return res;
}
```

**21. Product of Array Except Self**
**BF:** for each index multiply all other elements - O(n^2)
**Opt:** prefix product then suffix product in two passes - O(n), no division
```java
public int[] productExceptSelf(int[] nums) {
    int n = nums.length;
    int[] res = new int[n];
    res[0]=1;
    for (int i=1;i<n;i++) res[i]=res[i-1]*nums[i-1];   // prefix product
    int suffix=1;
    for (int i=n-1;i>=0;i--) { res[i]*=suffix; suffix*=nums[i]; } // multiply suffix product
    return res;
}
```

PATTERN: BINARY SEARCH

**22. Binary Search (basic)**
**BF:** linear scan - O(n)
**Opt:** halve search space each step - O(log n)
```java
public int search(int[] nums, int target) {
    int lo=0, hi=nums.length-1;
    while (lo<=hi) {
        int mid = lo+(hi-lo)/2;                 // avoids overflow
        if (nums[mid]==target) return mid;
        else if (nums[mid]<target) lo=mid+1;
        else hi=mid-1;
    }
    return -1;
}
```

**23. Search in Rotated Sorted Array**
**BF:** linear scan - O(n)
**Opt:** binary search, determine which half is sorted each step - O(log n)
```java
public int search(int[] nums, int target) {
    int lo=0, hi=nums.length-1;
    while (lo<=hi) {
        int mid=lo+(hi-lo)/2;
        if (nums[mid]==target) return mid;
        if (nums[lo]<=nums[mid]) {              // left half sorted
            if (nums[lo]<=target && target<nums[mid]) hi=mid-1;
            else lo=mid+1;
        } else {                                 // right half sorted
            if (nums[mid]<target && target<=nums[hi]) lo=mid+1;
            else hi=mid-1;
        }
    }
    return -1;
}
```

**24. Find First and Last Position of Element in Sorted Array**
**BF:** linear scan for first/last match - O(n)
**Opt:** two binary searches, one biased left one biased right - O(log n)
```java
public int[] searchRange(int[] nums, int target) {
    return new int[]{findBound(nums,target,true), findBound(nums,target,false)};
}
private int findBound(int[] nums, int target, boolean first) {
    int lo=0, hi=nums.length-1, res=-1;
    while (lo<=hi) {
        int mid=lo+(hi-lo)/2;
        if (nums[mid]==target) {
            res=mid;
            if (first) hi=mid-1; else lo=mid+1;  // keep searching same direction for bound
        } else if (nums[mid]<target) lo=mid+1;
        else hi=mid-1;
    }
    return res;
}
```

**25. Find Minimum in Rotated Sorted Array**
**BF:** linear scan for min - O(n)
**Opt:** binary search comparing mid to right end - O(log n)
```java
public int findMin(int[] nums) {
    int lo=0, hi=nums.length-1;
    while (lo<hi) {
        int mid=lo+(hi-lo)/2;
        if (nums[mid]>nums[hi]) lo=mid+1;        // min is in right half
        else hi=mid;                              // min is in left half (incl mid)
    }
    return nums[lo];
}
```

**26. Median of Two Sorted Arrays**
**BF:** merge both arrays, find median - O(m+n)
**Opt:** binary search on smaller array to partition both correctly - O(log(min(m,n)))
```java
public double findMedianSortedArrays(int[] a, int[] b) {
    if (a.length>b.length) return findMedianSortedArrays(b,a); // ensure a is smaller
    int m=a.length, n=b.length, lo=0, hi=m;
    while (lo<=hi) {
        int i=(lo+hi)/2, j=(m+n+1)/2-i;          // partition point in each array
        int aLeft = i==0?Integer.MIN_VALUE:a[i-1];
        int aRight = i==m?Integer.MAX_VALUE:a[i];
        int bLeft = j==0?Integer.MIN_VALUE:b[j-1];
        int bRight = j==n?Integer.MAX_VALUE:b[j];
        if (aLeft<=bRight && bLeft<=aRight) {    // correct partition found
            if ((m+n)%2==0) return (Math.max(aLeft,bLeft)+Math.min(aRight,bRight))/2.0;
            else return Math.max(aLeft,bLeft);
        } else if (aLeft>bRight) hi=i-1;
        else lo=i+1;
    }
    return -1;
}
```

**27. Search a 2D Matrix**
**BF:** scan every cell - O(m*n)
**Opt:** treat matrix as flattened sorted array, single binary search - O(log(m*n))
```java
public boolean searchMatrix(int[][] matrix, int target) {
    int rows=matrix.length, cols=matrix[0].length;
    int lo=0, hi=rows*cols-1;
    while (lo<=hi) {
        int mid=lo+(hi-lo)/2;
        int val = matrix[mid/cols][mid%cols];    // map 1D index back to 2D
        if (val==target) return true;
        else if (val<target) lo=mid+1;
        else hi=mid-1;
    }
    return false;
}
```

PATTERN: LINKED LIST

**28. Reverse Linked List**
**BF:** push values to a stack, rebuild list - O(n) extra space
**Opt:** iterative pointer reversal in place - O(1) space
```java
public ListNode reverseList(ListNode head) {
    ListNode prev=null, curr=head;
    while (curr!=null) {
        ListNode next=curr.next;    // save next before overwriting
        curr.next=prev;             // reverse the link
        prev=curr; curr=next;
    }
    return prev;
}
```

**29. Detect Cycle in Linked List**
**BF:** store visited nodes in a hashset - O(n) extra space
**Opt:** Floyd's slow/fast pointer, they meet if cycle exists - O(1) space
```java
public boolean hasCycle(ListNode head) {
    ListNode slow=head, fast=head;
    while (fast!=null && fast.next!=null) {
        slow=slow.next; fast=fast.next.next;
        if (slow==fast) return true;   // pointers met, cycle confirmed
    }
    return false;
}
```

**30. Merge Two Sorted Lists**
**BF:** collect all values, sort, rebuild list - O((m+n) log(m+n))
**Opt:** merge by comparing heads, splice pointers - O(m+n)
```java
public ListNode mergeTwoLists(ListNode l1, ListNode l2) {
    ListNode dummy = new ListNode(0), tail=dummy;
    while (l1!=null && l2!=null) {
        if (l1.val<=l2.val) { tail.next=l1; l1=l1.next; }
        else { tail.next=l2; l2=l2.next; }
        tail=tail.next;
    }
    tail.next = (l1!=null) ? l1 : l2;   // attach remaining nodes
    return dummy.next;
}
```

**31. Remove Nth Node From End of List**
**BF:** count length first pass, remove in second pass - two passes
**Opt:** two pointers, gap of n, single pass - O(n), one pass
```java
public ListNode removeNthFromEnd(ListNode head, int n) {
    ListNode dummy = new ListNode(0); dummy.next=head;
    ListNode fast=dummy, slow=dummy;
    for (int i=0;i<n;i++) fast=fast.next;      // move fast n steps ahead
    while (fast.next!=null) { fast=fast.next; slow=slow.next; }
    slow.next = slow.next.next;                 // skip target node
    return dummy.next;
}
```

**32. Find Middle of Linked List**
**BF:** count nodes, traverse to length/2 - two passes
**Opt:** slow/fast pointer, slow at middle when fast reaches end - one pass
```java
public ListNode middleNode(ListNode head) {
    ListNode slow=head, fast=head;
    while (fast!=null && fast.next!=null) {
        slow=slow.next; fast=fast.next.next;    // slow moves half as fast
    }
    return slow;
}
```

**33. LRU Cache**
**BF:** array/list, linear scan to find/evict least recently used - O(n) per op
**Opt:** LinkedHashMap with accessOrder=true, override removeEldestEntry - O(1) per op
```java
class LRUCache {
    private final int capacity;
    private final LinkedHashMap<Integer,Integer> cache;
    public LRUCache(int capacity) {
        this.capacity = capacity;
        cache = new LinkedHashMap<>(capacity, 0.75f, true) {  // true = access order
            protected boolean removeEldestEntry(Map.Entry<Integer,Integer> e) {
                return size() > LRUCache.this.capacity;        // auto-evict oldest
            }
        };
    }
    public int get(int key) { return cache.getOrDefault(key,-1); }
    public void put(int key, int value) { cache.put(key,value); }
}
```

PATTERN: STACK & QUEUE

**34. Valid Parentheses**
**BF:** repeatedly remove matching adjacent pairs - O(n^2)
**Opt:** stack, push opens, pop and match on close - O(n)
```java
public boolean isValid(String s) {
    Deque<Character> stack = new ArrayDeque<>();
    Map<Character,Character> pairs = Map.of(')','(',']','[','}','{');
    for (char c: s.toCharArray()) {
        if (pairs.containsValue(c)) stack.push(c);          // opening bracket
        else if (pairs.containsKey(c)) {
            if (stack.isEmpty() || stack.pop()!=pairs.get(c)) return false; // mismatch
        }
    }
    return stack.isEmpty();
}
```

**35. Min Stack**
**BF:** scan entire stack for min on every getMin() call - O(n) per call
**Opt:** second stack tracking running minimum - O(1) per call
```java
class MinStack {
    private Deque<Integer> stack = new ArrayDeque<>();
    private Deque<Integer> minStack = new ArrayDeque<>();
    public void push(int val) {
        stack.push(val);
        minStack.push(minStack.isEmpty() ? val : Math.min(val, minStack.peek())); // track min so far
    }
    public void pop() { stack.pop(); minStack.pop(); }
    public int top() { return stack.peek(); }
    public int getMin() { return minStack.peek(); }
}
```

**36. Next Greater Element**
**BF:** for each element scan rightward for greater - O(n^2)
**Opt:** monotonic decreasing stack of indices - O(n)
```java
public int[] nextGreaterElements(int[] nums) {
    int n = nums.length;
    int[] res = new int[n];
    Arrays.fill(res,-1);
    Deque<Integer> stack = new ArrayDeque<>();  // holds indices, values decreasing
    for (int i=0;i<n;i++) {
        while (!stack.isEmpty() && nums[stack.peek()]<nums[i]) {
            res[stack.pop()] = nums[i];         // found next greater for popped index
        }
        stack.push(i);
    }
    return res;
}
```

**37. Daily Temperatures**
**BF:** for each day scan forward for a warmer day - O(n^2)
**Opt:** monotonic decreasing stack of indices - O(n)
```java
public int[] dailyTemperatures(int[] temps) {
    int[] res = new int[temps.length];
    Deque<Integer> stack = new ArrayDeque<>();
    for (int i=0;i<temps.length;i++) {
        while (!stack.isEmpty() && temps[stack.peek()]<temps[i]) {
            int idx = stack.pop();
            res[idx] = i-idx;                   // days waited
        }
        stack.push(i);
    }
    return res;
}
```

**38. Evaluate Reverse Polish Notation**
**BF:** n/a — this problem is inherently stack-shaped, no simpler brute force
**Opt:** stack, push numbers, pop two on operator - O(n)
```java
public int evalRPN(String[] tokens) {
    Deque<Integer> stack = new ArrayDeque<>();
    for (String t: tokens) {
        switch (t) {
            case "+": stack.push(stack.pop()+stack.pop()); break;
            case "*": stack.push(stack.pop()*stack.pop()); break;
            case "-": { int b=stack.pop(), a=stack.pop(); stack.push(a-b); break; } // order matters
            case "/": { int b=stack.pop(), a=stack.pop(); stack.push(a/b); break; }
            default: stack.push(Integer.parseInt(t));
        }
    }
    return stack.pop();
}
```

**39. Implement Queue using Stacks**
**BF:** n/a — the two-stack trick is already the standard solution
**Opt:** two stacks, transfer only when out-stack empty (amortized O(1))
```java
class MyQueue {
    private Deque<Integer> in = new ArrayDeque<>();
    private Deque<Integer> out = new ArrayDeque<>();
    public void push(int x) { in.push(x); }
    public int pop() {
        if (out.isEmpty()) while (!in.isEmpty()) out.push(in.pop()); // reverse order once
        return out.pop();
    }
    public int peek() {
        if (out.isEmpty()) while (!in.isEmpty()) out.push(in.pop());
        return out.peek();
    }
}
```

PATTERN: TREES

**40. Maximum Depth of Binary Tree**
**BF:** n/a — recursion is already the natural/optimal approach
**Opt:** recursive DFS, 1 + max(left depth, right depth) - O(n)
```java
public int maxDepth(TreeNode root) {
    if (root==null) return 0;
    return 1 + Math.max(maxDepth(root.left), maxDepth(root.right)); // deeper subtree + self
}
```

**41. Level Order Traversal (BFS)**
**BF:** DFS with depth tracking, append to depth-indexed lists - works but less natural
**Opt:** BFS using a queue, process level by level - O(n)
```java
public List<List<Integer>> levelOrder(TreeNode root) {
    List<List<Integer>> res = new ArrayList<>();
    if (root==null) return res;
    Queue<TreeNode> q = new LinkedList<>(); q.add(root);
    while (!q.isEmpty()) {
        int size = q.size();                     // nodes in current level
        List<Integer> level = new ArrayList<>();
        for (int i=0;i<size;i++) {
            TreeNode node = q.poll();
            level.add(node.val);
            if (node.left!=null) q.add(node.left);
            if (node.right!=null) q.add(node.right);
        }
        res.add(level);
    }
    return res;
}
```

**42. Validate Binary Search Tree**
**BF:** in-order traversal into a list, check sorted - O(n) extra space
**Opt:** recursive bounds-checking, pass min/max down - O(n), O(1) extra (excl recursion)
```java
public boolean isValidBST(TreeNode root) {
    return validate(root, null, null);
}
private boolean validate(TreeNode node, Integer lower, Integer upper) {
    if (node==null) return true;
    if (lower!=null && node.val<=lower) return false;   // violates lower bound
    if (upper!=null && node.val>=upper) return false;   // violates upper bound
    return validate(node.left, lower, node.val) && validate(node.right, node.val, upper);
}
```

**43. Lowest Common Ancestor of BST**
**BF:** find path from root to each node, compare paths - O(n) extra space
**Opt:** use BST property, branch based on value comparison - O(h) time, O(1) space
```java
public TreeNode lowestCommonAncestor(TreeNode root, TreeNode p, TreeNode q) {
    while (root!=null) {
        if (p.val<root.val && q.val<root.val) root=root.left;   // both in left subtree
        else if (p.val>root.val && q.val>root.val) root=root.right; // both in right subtree
        else return root;                                        // split point = LCA
    }
    return null;
}
```

**44. Diameter of Binary Tree**
**BF:** for every node compute height of subtrees separately - O(n^2)
**Opt:** single DFS, compute height and update diameter simultaneously - O(n)
```java
private int diameter=0;
public int diameterOfBinaryTree(TreeNode root) {
    height(root);
    return diameter;
}
private int height(TreeNode node) {
    if (node==null) return 0;
    int left = height(node.left);
    int right = height(node.right);
    diameter = Math.max(diameter, left+right);   // path through this node
    return 1 + Math.max(left,right);
}
```

**45. Invert Binary Tree**
**BF:** n/a — recursive swap is already optimal
**Opt:** recursively swap left/right children - O(n)
```java
public TreeNode invertTree(TreeNode root) {
    if (root==null) return null;
    TreeNode temp = root.left;
    root.left = invertTree(root.right);   // recurse then swap
    root.right = invertTree(temp);
    return root;
}
```

**46. Serialize and Deserialize Binary Tree**
**BF:** n/a — pre-order with null markers is the standard efficient approach
**Opt:** pre-order DFS string with null markers, split and rebuild - O(n)
```java
public String serialize(TreeNode root) {
    if (root==null) return "#,";
    return root.val + "," + serialize(root.left) + serialize(root.right); // pre-order
}
public TreeNode deserialize(String data) {
    Queue<String> nodes = new LinkedList<>(Arrays.asList(data.split(",")));
    return build(nodes);
}
private TreeNode build(Queue<String> nodes) {
    String val = nodes.poll();
    if (val.equals("#")) return null;              // null marker
    TreeNode node = new TreeNode(Integer.parseInt(val));
    node.left = build(nodes);
    node.right = build(nodes);
    return node;
}
```

**47. Path Sum (root to leaf equals target)**
**BF:** n/a — DFS with running sum is already the natural approach
**Opt:** DFS subtracting target as you descend, check at leaf - O(n)
```java
public boolean hasPathSum(TreeNode root, int targetSum) {
    if (root==null) return false;
    if (root.left==null && root.right==null) return targetSum==root.val; // leaf check
    return hasPathSum(root.left, targetSum-root.val) || hasPathSum(root.right, targetSum-root.val);
}
```

PATTERN: GRAPHS

**48. Number of Islands**
**BF:** n/a — grid traversal is inherently the approach, no simpler alternative
**Opt:** DFS/BFS flood-fill, sink visited land to '0' - O(rows*cols)
```java
public int numIslands(char[][] grid) {
    int count=0;
    for (int i=0;i<grid.length;i++)
        for (int j=0;j<grid[0].length;j++)
            if (grid[i][j]=='1') { count++; sink(grid,i,j); }  // new island found
    return count;
}
private void sink(char[][] g, int i, int j) {
    if (i<0||i>=g.length||j<0||j>=g[0].length||g[i][j]!='1') return;
    g[i][j]='0';                        // mark visited
    sink(g,i+1,j); sink(g,i-1,j); sink(g,i,j+1); sink(g,i,j-1);
}
```

**49. Course Schedule (cycle detection)**
**BF:** DFS with recursion stack to detect back-edge - O(V+E), works but less scalable
**Opt:** Kahn's algorithm, topological sort via in-degree + queue - O(V+E)
```java
public boolean canFinish(int numCourses, int[][] prerequisites) {
    List<List<Integer>> graph = new ArrayList<>();
    for (int i=0;i<numCourses;i++) graph.add(new ArrayList<>());
    int[] inDegree = new int[numCourses];
    for (int[] p: prerequisites) { graph.get(p[1]).add(p[0]); inDegree[p[0]]++; }
    Queue<Integer> q = new LinkedList<>();
    for (int i=0;i<numCourses;i++) if (inDegree[i]==0) q.add(i);  // no prereqs
    int visited=0;
    while (!q.isEmpty()) {
        int course = q.poll(); visited++;
        for (int next: graph.get(course)) if (--inDegree[next]==0) q.add(next);
    }
    return visited==numCourses;   // all visited = no cycle
}
```

**50. Clone Graph**
**BF:** n/a — hashmap-tracked DFS/BFS is the standard efficient approach
**Opt:** DFS with hashmap of original->clone to avoid infinite recursion - O(V+E)
```java
public Node cloneGraph(Node node) {
    if (node==null) return null;
    return clone(node, new HashMap<>());
}
private Node clone(Node node, Map<Node,Node> visited) {
    if (visited.containsKey(node)) return visited.get(node);   // already cloned
    Node copy = new Node(node.val);
    visited.put(node, copy);
    for (Node nbr: node.neighbors) copy.neighbors.add(clone(nbr, visited));
    return copy;
}
```

**51. Word Ladder (shortest transformation length)**
**BF:** try all words, build graph fully, then BFS - expensive graph construction
**Opt:** BFS layer by layer, generate neighbors by changing one letter at a time - O(n*26*L)
```java
public int ladderLength(String beginWord, String endWord, List<String> wordList) {
    Set<String> dict = new HashSet<>(wordList);
    if (!dict.contains(endWord)) return 0;
    Queue<String> q = new LinkedList<>(); q.add(beginWord);
    int steps=1;
    while (!q.isEmpty()) {
        int size=q.size();
        for (int i=0;i<size;i++) {
            String word = q.poll();
            if (word.equals(endWord)) return steps;
            char[] chars = word.toCharArray();
            for (int j=0;j<chars.length;j++) {
                char orig = chars[j];
                for (char c='a'; c<='z'; c++) {
                    chars[j]=c;
                    String next = new String(chars);
                    if (dict.remove(next)) q.add(next);  // remove = mark visited
                }
                chars[j]=orig;
            }
        }
        steps++;
    }
    return 0;
}
```

**52. Dijkstra's Shortest Path**
**BF:** Bellman-Ford relax all edges V-1 times - O(V*E)
**Opt:** min-heap (priority queue) greedy relaxation - O(E log V)
```java
public int[] dijkstra(int n, List<int[]>[] graph, int src) {
    int[] dist = new int[n];
    Arrays.fill(dist, Integer.MAX_VALUE);
    dist[src]=0;
    PriorityQueue<int[]> pq = new PriorityQueue<>((a,b)->a[1]-b[1]); // [node, dist]
    pq.offer(new int[]{src,0});
    while (!pq.isEmpty()) {
        int[] curr = pq.poll();
        int u = curr[0], d = curr[1];
        if (d>dist[u]) continue;                 // stale entry, skip
        for (int[] edge: graph[u]) {
            int v = edge[0], w = edge[1];
            if (dist[u]+w < dist[v]) {
                dist[v] = dist[u]+w;              // relax edge
                pq.offer(new int[]{v, dist[v]});
            }
        }
    }
    return dist;
}
```

**53. Detect Cycle in Undirected Graph**
**BF:** n/a — DFS with parent tracking is the standard efficient approach
**Opt:** DFS, track parent to distinguish back-edge from trivial parent-edge - O(V+E)
```java
public boolean hasCycle(int n, List<List<Integer>> graph) {
    boolean[] visited = new boolean[n];
    for (int i=0;i<n;i++) if (!visited[i] && dfs(i,-1,graph,visited)) return true;
    return false;
}
private boolean dfs(int node, int parent, List<List<Integer>> graph, boolean[] visited) {
    visited[node]=true;
    for (int nbr: graph.get(node)) {
        if (!visited[nbr]) { if (dfs(nbr,node,graph,visited)) return true; }
        else if (nbr!=parent) return true;        // visited neighbor that isn't parent = cycle
    }
    return false;
}
```

**54. Number of Connected Components in Undirected Graph**
**BF:** DFS/BFS from every unvisited node, count runs - O(V+E) (this IS the optimal approach)
**Opt:** Union-Find (disjoint set) - near O(V+E) with path compression, faster in practice for many queries
```java
class UnionFind {
    int[] parent, rank;
    UnionFind(int n) { parent=new int[n]; rank=new int[n]; for (int i=0;i<n;i++) parent[i]=i; }
    int find(int x) { return parent[x]==x ? x : (parent[x]=find(parent[x])); } // path compression
    void union(int a, int b) {
        int ra=find(a), rb=find(b);
        if (ra==rb) return;
        if (rank[ra]<rank[rb]) { int t=ra; ra=rb; rb=t; }
        parent[rb]=ra;
        if (rank[ra]==rank[rb]) rank[ra]++;
    }
}
public int countComponents(int n, int[][] edges) {
    UnionFind uf = new UnionFind(n);
    for (int[] e: edges) uf.union(e[0], e[1]);
    Set<Integer> roots = new HashSet<>();
    for (int i=0;i<n;i++) roots.add(uf.find(i));  // count distinct roots
    return roots.size();
}
```

PATTERN: BACKTRACKING

**55. Subsets**
**BF:** n/a — backtracking IS the standard approach (bitmask is an alternative, same complexity)
**Opt:** backtrack, include/exclude each element - O(2^n)
```java
public List<List<Integer>> subsets(int[] nums) {
    List<List<Integer>> res = new ArrayList<>();
    backtrack(nums, 0, new ArrayList<>(), res);
    return res;
}
private void backtrack(int[] nums, int start, List<Integer> curr, List<List<Integer>> res) {
    res.add(new ArrayList<>(curr));               // every state is a valid subset
    for (int i=start; i<nums.length; i++) {
        curr.add(nums[i]);
        backtrack(nums, i+1, curr, res);
        curr.remove(curr.size()-1);               // undo choice
    }
}
```

**56. Permutations**
**BF:** n/a — backtracking with a used[] array is the standard approach
**Opt:** backtrack, track used elements, build permutation - O(n * n!)
```java
public List<List<Integer>> permute(int[] nums) {
    List<List<Integer>> res = new ArrayList<>();
    backtrack(nums, new ArrayList<>(), new boolean[nums.length], res);
    return res;
}
private void backtrack(int[] nums, List<Integer> curr, boolean[] used, List<List<Integer>> res) {
    if (curr.size()==nums.length) { res.add(new ArrayList<>(curr)); return; }
    for (int i=0;i<nums.length;i++) {
        if (used[i]) continue;
        used[i]=true; curr.add(nums[i]);
        backtrack(nums, curr, used, res);
        used[i]=false; curr.remove(curr.size()-1); // undo choice
    }
}
```

**57. Combination Sum**
**BF:** n/a — backtracking with reuse is the standard approach
**Opt:** backtrack, allow reuse of same index, prune when sum exceeds target - O(2^target) worst case
```java
public List<List<Integer>> combinationSum(int[] candidates, int target) {
    List<List<Integer>> res = new ArrayList<>();
    backtrack(candidates, target, 0, new ArrayList<>(), res);
    return res;
}
private void backtrack(int[] c, int remain, int start, List<Integer> curr, List<List<Integer>> res) {
    if (remain==0) { res.add(new ArrayList<>(curr)); return; }
    if (remain<0) return;                          // prune
    for (int i=start;i<c.length;i++) {
        curr.add(c[i]);
        backtrack(c, remain-c[i], i, curr, res);    // i not i+1: allows reuse
        curr.remove(curr.size()-1);
    }
}
```

**58. N-Queens**
**BF:** n/a — backtracking with column/diagonal pruning is the standard approach
**Opt:** backtrack row by row, track used columns/diagonals for O(1) conflict check - O(n!) worst case, heavily pruned
```java
public List<List<String>> solveNQueens(int n) {
    List<List<String>> res = new ArrayList<>();
    int[] queens = new int[n];                     // queens[row] = col
    backtrack(0, n, queens, res);
    return res;
}
private void backtrack(int row, int n, int[] queens, List<List<String>> res) {
    if (row==n) { res.add(build(queens,n)); return; }
    for (int col=0; col<n; col++) {
        if (isValid(queens,row,col)) {
            queens[row]=col;
            backtrack(row+1, n, queens, res);
        }
    }
}
private boolean isValid(int[] queens, int row, int col) {
    for (int r=0;r<row;r++) {
        int c = queens[r];
        if (c==col || Math.abs(c-col)==Math.abs(r-row)) return false; // column or diagonal clash
    }
    return true;
}
private List<String> build(int[] queens, int n) {
    List<String> board = new ArrayList<>();
    for (int q: queens) {
        StringBuilder row = new StringBuilder();
        for (int i=0;i<n;i++) row.append(i==q?'Q':'.');
        board.add(row.toString());
    }
    return board;
}
```

**59. Word Search (in grid)**
**BF:** n/a — backtracking DFS from every cell is the standard approach
**Opt:** DFS backtracking, mark visited temporarily then restore - O(rows*cols*4^L)
```java
public boolean exist(char[][] board, String word) {
    for (int i=0;i<board.length;i++)
        for (int j=0;j<board[0].length;j++)
            if (dfs(board,word,0,i,j)) return true;
    return false;
}
private boolean dfs(char[][] b, String w, int idx, int i, int j) {
    if (idx==w.length()) return true;
    if (i<0||i>=b.length||j<0||j>=b[0].length||b[i][j]!=w.charAt(idx)) return false;
    char temp = b[i][j];
    b[i][j]='#';                                   // mark visited temporarily
    boolean found = dfs(b,w,idx+1,i+1,j) || dfs(b,w,idx+1,i-1,j)
                  || dfs(b,w,idx+1,i,j+1) || dfs(b,w,idx+1,i,j-1);
    b[i][j]=temp;                                   // restore for other paths
    return found;
}
```

PATTERN: DYNAMIC PROGRAMMING

**60. Climbing Stairs**
**BF:** recursion trying both step choices - O(2^n)
**Opt:** bottom-up DP, ways[i]=ways[i-1]+ways[i-2] (Fibonacci pattern) - O(n), O(1) space
```java
public int climbStairs(int n) {
    if (n<=2) return n;
    int prev2=1, prev1=2;
    for (int i=3;i<=n;i++) {
        int curr = prev1+prev2;      // ways to reach i = ways to i-1 + ways to i-2
        prev2=prev1; prev1=curr;
    }
    return prev1;
}
```

**61. Maximum Subarray (Kadane's Algorithm)**
**BF:** check sum of every subarray - O(n^2)
**Opt:** running max ending here vs starting fresh - O(n)
```java
public int maxSubArray(int[] nums) {
    int maxSoFar=nums[0], maxEndingHere=nums[0];
    for (int i=1;i<nums.length;i++) {
        maxEndingHere = Math.max(nums[i], maxEndingHere+nums[i]); // extend or restart
        maxSoFar = Math.max(maxSoFar, maxEndingHere);
    }
    return maxSoFar;
}
```

**62. Longest Common Subsequence**
**BF:** recursion trying match/skip choices for both strings - O(2^(m+n))
**Opt:** 2D DP table, dp[i][j] built from dp[i-1][j-1]/dp[i-1][j]/dp[i][j-1] - O(m*n)
```java
public int longestCommonSubsequence(String a, String b) {
    int m=a.length(), n=b.length();
    int[][] dp = new int[m+1][n+1];
    for (int i=1;i<=m;i++)
        for (int j=1;j<=n;j++)
            dp[i][j] = (a.charAt(i-1)==b.charAt(j-1))
                ? dp[i-1][j-1]+1                          // chars match, extend
                : Math.max(dp[i-1][j], dp[i][j-1]);        // skip one char from either
    return dp[m][n];
}
```

**63. 0/1 Knapsack**
**BF:** recursion trying include/exclude every item - O(2^n)
**Opt:** 2D DP, dp[i][w] = best value using first i items with capacity w - O(n*capacity)
```java
public int knapsack(int[] weights, int[] values, int capacity) {
    int n = weights.length;
    int[][] dp = new int[n+1][capacity+1];
    for (int i=1;i<=n;i++) {
        for (int w=0; w<=capacity; w++) {
            dp[i][w] = dp[i-1][w];                        // exclude item i
            if (weights[i-1]<=w)
                dp[i][w] = Math.max(dp[i][w], dp[i-1][w-weights[i-1]] + values[i-1]); // include item i
        }
    }
    return dp[n][capacity];
}
```

**64. Coin Change (minimum coins for amount)**
**BF:** recursion trying every coin at every amount - O(coins^amount)
**Opt:** 1D DP, dp[a] = min coins for amount a, built bottom-up - O(amount*coins)
```java
public int coinChange(int[] coins, int amount) {
    int[] dp = new int[amount+1];
    Arrays.fill(dp, amount+1);                            // "infinity" sentinel
    dp[0]=0;
    for (int a=1;a<=amount;a++)
        for (int c: coins)
            if (c<=a) dp[a] = Math.min(dp[a], dp[a-c]+1); // use one coin c + best for remainder
    return dp[amount]>amount ? -1 : dp[amount];
}
```

**65. Longest Increasing Subsequence**
**BF:** DP where dp[i] = 1 + max(dp[j]) for all j<i with nums[j]<nums[i] - O(n^2)
**Opt:** patience sorting with binary search on tails array - O(n log n)
```java
public int lengthOfLIS(int[] nums) {
    int[] tails = new int[nums.length];
    int size=0;
    for (int num: nums) {
        int lo=0, hi=size;
        while (lo<hi) {                                    // binary search insertion point
            int mid=(lo+hi)/2;
            if (tails[mid]<num) lo=mid+1; else hi=mid;
        }
        tails[lo]=num;
        if (lo==size) size++;                               // extended the sequence
    }
    return size;
}
```

**66. Edit Distance**
**BF:** recursion trying insert/delete/replace at every mismatch - O(3^(m+n))
**Opt:** 2D DP, dp[i][j] = edits to convert a[0..i] to b[0..j] - O(m*n)
```java
public int minDistance(String a, String b) {
    int m=a.length(), n=b.length();
    int[][] dp = new int[m+1][n+1];
    for (int i=0;i<=m;i++) dp[i][0]=i;                     // delete all of a
    for (int j=0;j<=n;j++) dp[0][j]=j;                     // insert all of b
    for (int i=1;i<=m;i++)
        for (int j=1;j<=n;j++)
            dp[i][j] = (a.charAt(i-1)==b.charAt(j-1))
                ? dp[i-1][j-1]                              // chars match, no edit
                : 1 + Math.min(dp[i-1][j-1], Math.min(dp[i-1][j], dp[i][j-1])); // replace/delete/insert
    return dp[m][n];
}
```

**67. House Robber**
**BF:** recursion trying rob/skip every house - O(2^n)
**Opt:** DP, rob[i] = max(rob[i-1], rob[i-2]+nums[i]) - O(n), O(1) space
```java
public int rob(int[] nums) {
    int prev2=0, prev1=0;
    for (int n: nums) {
        int curr = Math.max(prev1, prev2+n);   // skip this house vs rob it
        prev2=prev1; prev1=curr;
    }
    return prev1;
}
```

**68. Word Break**
**BF:** recursion trying every prefix split - O(2^n)
**Opt:** 1D DP, dp[i]=true if s[0..i) breakable into dictionary words - O(n^2)
```java
public boolean wordBreak(String s, List<String> wordDict) {
    Set<String> dict = new HashSet<>(wordDict);
    boolean[] dp = new boolean[s.length()+1];
    dp[0]=true;                                             // empty prefix
    for (int i=1;i<=s.length();i++)
        for (int j=0;j<i;j++)
            if (dp[j] && dict.contains(s.substring(j,i))) { dp[i]=true; break; } // valid split found
    return dp[s.length()];
}
```

**69. Unique Paths (grid, top-left to bottom-right)**
**BF:** recursion trying right/down at every cell - O(2^(m+n))
**Opt:** 2D DP, paths[i][j] = paths[i-1][j] + paths[i][j-1] - O(m*n)
```java
public int uniquePaths(int m, int n) {
    int[][] dp = new int[m][n];
    for (int i=0;i<m;i++) dp[i][0]=1;      // only one way along top row
    for (int j=0;j<n;j++) dp[0][j]=1;      // only one way along left column
    for (int i=1;i<m;i++)
        for (int j=1;j<n;j++)
            dp[i][j] = dp[i-1][j] + dp[i][j-1];   // from above + from left
    return dp[m-1][n-1];
}
```

PATTERN: GREEDY / INTERVALS

**70. Jump Game (can reach last index)**
**BF:** recursion/backtracking trying every jump length - O(2^n)
**Opt:** greedy, track farthest reachable index while scanning - O(n)
```java
public boolean canJump(int[] nums) {
    int farthest=0;
    for (int i=0;i<nums.length;i++) {
        if (i>farthest) return false;              // stuck, can't reach index i
        farthest = Math.max(farthest, i+nums[i]);
    }
    return true;
}
```

**71. Gas Station (find starting index for full circuit)**
**BF:** try every starting station, simulate full circuit - O(n^2)
**Opt:** greedy single pass, reset start when running total goes negative - O(n)
```java
public int canCompleteCircuit(int[] gas, int[] cost) {
    int total=0, tank=0, start=0;
    for (int i=0;i<gas.length;i++) {
        int diff = gas[i]-cost[i];
        total += diff; tank += diff;
        if (tank<0) { start=i+1; tank=0; }   // can't reach here from current start, restart
    }
    return total>=0 ? start : -1;
}
```

**72. Merge Intervals**
**BF:** compare every pair of intervals for overlap, merge repeatedly - O(n^2)
**Opt:** sort by start, then single sweep merging overlapping intervals - O(n log n)
```java
public int[][] merge(int[][] intervals) {
    Arrays.sort(intervals, (a,b)->Integer.compare(a[0],b[0]));
    List<int[]> merged = new ArrayList<>();
    for (int[] iv: intervals) {
        if (merged.isEmpty() || merged.get(merged.size()-1)[1]<iv[0]) merged.add(iv); // no overlap
        else merged.get(merged.size()-1)[1] = Math.max(merged.get(merged.size()-1)[1], iv[1]); // extend
    }
    return merged.toArray(new int[merged.size()][]);
}
```

**73. Meeting Rooms II (minimum rooms needed)**
**BF:** check every pair of meetings for overlap, count max concurrent - O(n^2)
**Opt:** sort by start, min-heap of end times, reuse room if earliest ends before next starts - O(n log n)
```java
public int minMeetingRooms(int[][] intervals) {
    Arrays.sort(intervals, (a,b)->Integer.compare(a[0],b[0]));
    PriorityQueue<Integer> endTimes = new PriorityQueue<>();  // earliest-ending room on top
    for (int[] iv: intervals) {
        if (!endTimes.isEmpty() && endTimes.peek()<=iv[0]) endTimes.poll(); // reuse freed room
        endTimes.offer(iv[1]);
    }
    return endTimes.size();
}
```

PATTERN: HEAP

**74. Kth Largest Element in an Array**
**BF:** sort full array, index from the end - O(n log n)
**Opt:** min-heap of size k, keep only k largest seen - O(n log k)
```java
public int findKthLargest(int[] nums, int k) {
    PriorityQueue<Integer> heap = new PriorityQueue<>();  // min-heap
    for (int n: nums) {
        heap.offer(n);
        if (heap.size()>k) heap.poll();     // drop smallest, keep k largest
    }
    return heap.peek();
}
```

**75. Find Median from Data Stream**
**BF:** insert into sorted list every time, find middle - O(n) per insert
**Opt:** two heaps (max-heap for lower half, min-heap for upper half), balance sizes - O(log n) per insert
```java
class MedianFinder {
    private PriorityQueue<Integer> lower = new PriorityQueue<>(Collections.reverseOrder()); // max-heap
    private PriorityQueue<Integer> upper = new PriorityQueue<>();                            // min-heap
    public void addNum(int num) {
        lower.offer(num);
        upper.offer(lower.poll());               // balance: move largest of lower to upper
        if (upper.size()>lower.size()) lower.offer(upper.poll()); // rebalance sizes
    }
    public double findMedian() {
        if (lower.size()>upper.size()) return lower.peek();
        return (lower.peek()+upper.peek())/2.0;
    }
}
```

PATTERN: BIT MANIPULATION

**76. Single Number (every element twice except one)**
**BF:** hashmap count frequencies, return the one with count 1 - O(n) extra space
**Opt:** XOR all elements, duplicates cancel out to 0 - O(n), O(1) space
```java
public int singleNumber(int[] nums) {
    int result=0;
    for (int n: nums) result ^= n;   // a^a=0, a^0=a, order doesn't matter
    return result;
}
```

**77. Number of 1 Bits (Hamming Weight)**
**BF:** check each of 32 bits with shift and mask - O(32)
**Opt:** Brian Kernighan's trick, n & (n-1) clears lowest set bit - O(number of set bits)
```java
public int hammingWeight(int n) {
    int count=0;
    while (n!=0) {
        n &= (n-1);      // clears the lowest set bit each time
        count++;
    }
    return count;
}
```

**78. Counting Bits (0 to n, count set bits for each)**
**BF:** for each number count bits individually - O(n log n)
**Opt:** DP, bits[i] = bits[i>>1] + (i&1) reuse previous results - O(n)
```java
public int[] countBits(int n) {
    int[] res = new int[n+1];
    for (int i=1;i<=n;i++) res[i] = res[i>>1] + (i&1); // shift-right result + last bit
    return res;
}
```

**79. Missing Number (0 to n, one missing)**
**BF:** sort and scan for gap - O(n log n)
**Opt:** XOR all indices and values together, missing number remains - O(n), O(1) space
```java
public int missingNumber(int[] nums) {
    int result = nums.length;                 // account for index n
    for (int i=0;i<nums.length;i++) result ^= i ^ nums[i];
    return result;
}
```

**80. Power of Two**
**BF:** repeatedly divide by 2, check remainder - O(log n)
**Opt:** power of two has exactly one set bit, check n & (n-1) == 0 - O(1)
```java
public boolean isPowerOfTwo(int n) {
    return n>0 && (n & (n-1))==0;   // clears only set bit, must become 0
}
```

PATTERN: MATRIX

**81. Rotate Image (90 degrees in place)**
**BF:** copy to new matrix with transformed indices - O(n^2) extra space
**Opt:** transpose then reverse each row, in place - O(1) extra space
```java
public void rotate(int[][] matrix) {
    int n = matrix.length;
    for (int i=0;i<n;i++)
        for (int j=i+1;j<n;j++) {
            int t=matrix[i][j]; matrix[i][j]=matrix[j][i]; matrix[j][i]=t; // transpose
        }
    for (int[] row: matrix) {
        for (int l=0,r=n-1;l<r;l++,r--) { int t=row[l]; row[l]=row[r]; row[r]=t; } // reverse row
    }
}
```

**82. Spiral Matrix (return elements in spiral order)**
**BF:** n/a — boundary-tracking traversal is the standard approach
**Opt:** track top/bottom/left/right bounds, shrink after each side - O(rows*cols)
```java
public List<Integer> spiralOrder(int[][] matrix) {
    List<Integer> res = new ArrayList<>();
    int top=0, bottom=matrix.length-1, left=0, right=matrix[0].length-1;
    while (top<=bottom && left<=right) {
        for (int j=left;j<=right;j++) res.add(matrix[top][j]); top++;      // across top
        for (int i=top;i<=bottom;i++) res.add(matrix[i][right]); right--;  // down right
        if (top<=bottom) { for (int j=right;j>=left;j--) res.add(matrix[bottom][j]); bottom--; } // across bottom
        if (left<=right) { for (int i=bottom;i>=top;i--) res.add(matrix[i][left]); left++; }     // up left
    }
    return res;
}
```

**83. Set Matrix Zeroes**
**BF:** use a copy matrix to track original zeros, then zero out - O(m*n) extra space
**Opt:** use first row/column as markers instead of extra space - O(1) extra space
```java
public void setZeroes(int[][] matrix) {
    int rows=matrix.length, cols=matrix[0].length;
    boolean firstRowZero=false, firstColZero=false;
    for (int j=0;j<cols;j++) if (matrix[0][j]==0) firstRowZero=true;
    for (int i=0;i<rows;i++) if (matrix[i][0]==0) firstColZero=true;
    for (int i=1;i<rows;i++)
        for (int j=1;j<cols;j++)
            if (matrix[i][j]==0) { matrix[i][0]=0; matrix[0][j]=0; }  // mark using borders
    for (int i=1;i<rows;i++)
        for (int j=1;j<cols;j++)
            if (matrix[i][0]==0 || matrix[0][j]==0) matrix[i][j]=0;
    if (firstRowZero) for (int j=0;j<cols;j++) matrix[0][j]=0;
    if (firstColZero) for (int i=0;i<rows;i++) matrix[i][0]=0;
}
```

PATTERN: STRINGS

**84. Longest Palindromic Substring**
**BF:** check every substring for palindrome - O(n^3)
**Opt:** expand around center for every index (odd and even length) - O(n^2)
```java
public String longestPalindrome(String s) {
    int start=0, maxLen=0;
    for (int i=0;i<s.length();i++) {
        int len1 = expand(s,i,i);       // odd length, center at i
        int len2 = expand(s,i,i+1);     // even length, center between i,i+1
        int len = Math.max(len1,len2);
        if (len>maxLen) { maxLen=len; start = i-(len-1)/2; }
    }
    return s.substring(start, start+maxLen);
}
private int expand(String s, int l, int r) {
    while (l>=0 && r<s.length() && s.charAt(l)==s.charAt(r)) { l--; r++; }
    return r-l-1;
}
```

**85. Valid Anagram**
**BF:** sort both strings, compare - O(n log n)
**Opt:** frequency count array, compare counts - O(n)
```java
public boolean isAnagram(String s, String t) {
    if (s.length()!=t.length()) return false;
    int[] count = new int[26];
    for (int i=0;i<s.length();i++) { count[s.charAt(i)-'a']++; count[t.charAt(i)-'a']--; }
    for (int c: count) if (c!=0) return false;   // mismatch in frequency
    return true;
}
```

**86. Implement strStr (substring search / needle in haystack)**
**BF:** check every starting position, compare substring - O(n*m)
**Opt:** KMP with failure function to skip re-comparisons - O(n+m)
```java
public int strStr(String haystack, String needle) {
    int n=haystack.length(), m=needle.length();
    if (m==0) return 0;
    int[] lps = buildLPS(needle);                 // longest prefix-suffix table
    int i=0, j=0;
    while (i<n) {
        if (haystack.charAt(i)==needle.charAt(j)) { i++; j++; if (j==m) return i-j; }
        else if (j>0) j = lps[j-1];                // fall back using failure function
        else i++;
    }
    return -1;
}
private int[] buildLPS(String p) {
    int[] lps = new int[p.length()];
    int len=0, i=1;
    while (i<p.length()) {
        if (p.charAt(i)==p.charAt(len)) { lps[i++] = ++len; }
        else if (len>0) len = lps[len-1];
        else lps[i++]=0;
    }
    return lps;
}
```

**87. Longest Palindromic Subsequence**
**BF:** try all subsequences, check palindrome - O(2^n)
**Opt:** 2D DP, same as LCS between string and its reverse - O(n^2)
```java
public int longestPalindromeSubseq(String s) {
    int n=s.length();
    int[][] dp = new int[n][n];
    for (int i=n-1;i>=0;i--) {
        dp[i][i]=1;                                // single char is palindrome of length 1
        for (int j=i+1;j<n;j++) {
            if (s.charAt(i)==s.charAt(j)) dp[i][j] = dp[i+1][j-1]+2;  // match, extend inward
            else dp[i][j] = Math.max(dp[i+1][j], dp[i][j-1]);
        }
    }
    return dp[0][n-1];
}
```

PATTERN: ARRAYS / MISC

**88. Best Time to Buy and Sell Stock (one transaction)**
**BF:** check every buy-sell pair - O(n^2)
**Opt:** track minimum price seen so far, max profit at each step - O(n)
```java
public int maxProfit(int[] prices) {
    int minPrice=Integer.MAX_VALUE, maxProfit=0;
    for (int p: prices) {
        minPrice = Math.min(minPrice, p);          // best day to have bought so far
        maxProfit = Math.max(maxProfit, p-minPrice);
    }
    return maxProfit;
}
```

**89. Best Time to Buy and Sell Stock II (unlimited transactions)**
**BF:** try every combination of buy/sell days recursively - O(2^n)
**Opt:** greedy, sum every positive day-to-day gain - O(n)
```java
public int maxProfit(int[] prices) {
    int profit=0;
    for (int i=1;i<prices.length;i++)
        if (prices[i]>prices[i-1]) profit += prices[i]-prices[i-1]; // capture every uptick
    return profit;
}
```

**90. Majority Element (appears more than n/2 times)**
**BF:** hashmap count frequencies, find max - O(n) extra space
**Opt:** Boyer-Moore voting, candidate + counter cancels out non-majority - O(1) space
```java
public int majorityElement(int[] nums) {
    int count=0, candidate=0;
    for (int n: nums) {
        if (count==0) candidate=n;                 // pick new candidate
        count += (n==candidate) ? 1 : -1;
    }
    return candidate;
}
```

**91. Rotate Array (by k steps)**
**BF:** rotate one step at a time, k times - O(n*k)
**Opt:** reverse whole array, then reverse two parts - O(n), O(1) space
```java
public void rotate(int[] nums, int k) {
    k %= nums.length;
    reverse(nums, 0, nums.length-1);   // reverse all
    reverse(nums, 0, k-1);             // reverse first k
    reverse(nums, k, nums.length-1);   // reverse remaining
}
private void reverse(int[] a, int l, int r) {
    while (l<r) { int t=a[l]; a[l]=a[r]; a[r]=t; l++; r--; }
}
```

**92. Move Zeroes (to end, maintain order of non-zero)**
**BF:** copy non-zeros to new array, fill rest with zero - O(n) extra space
**Opt:** two pointers, swap non-zero forward in place - O(n), O(1) space
```java
public void moveZeroes(int[] nums) {
    int insertPos=0;
    for (int n: nums) if (n!=0) nums[insertPos++]=n;   // pack non-zeros to front
    while (insertPos<nums.length) nums[insertPos++]=0; // fill remainder with zero
}
```

PATTERN: SORTING

**93. Merge Sort**
**BF:** n/a — this IS the optimal comparison-based divide and conquer approach
**Opt:** divide into halves, sort recursively, merge sorted halves - O(n log n)
```java
public void mergeSort(int[] a, int l, int r) {
    if (l>=r) return;
    int mid=(l+r)/2;
    mergeSort(a,l,mid);
    mergeSort(a,mid+1,r);
    merge(a,l,mid,r);
}
private void merge(int[] a, int l, int mid, int r) {
    int[] temp = new int[r-l+1];
    int i=l, j=mid+1, k=0;
    while (i<=mid && j<=r) temp[k++] = (a[i]<=a[j]) ? a[i++] : a[j++]; // pick smaller
    while (i<=mid) temp[k++]=a[i++];
    while (j<=r) temp[k++]=a[j++];
    System.arraycopy(temp,0,a,l,temp.length);
}
```

**94. Quick Sort**
**BF:** n/a — this IS the standard approach; worst case O(n^2) on bad pivots
**Opt:** partition around pivot, recurse on sides - O(n log n) average
```java
public void quickSort(int[] a, int lo, int hi) {
    if (lo>=hi) return;
    int p = partition(a, lo, hi);
    quickSort(a, lo, p-1);
    quickSort(a, p+1, hi);
}
private int partition(int[] a, int lo, int hi) {
    int pivot = a[hi], i=lo-1;
    for (int j=lo;j<hi;j++) {
        if (a[j]<pivot) { i++; int t=a[i]; a[i]=a[j]; a[j]=t; }  // move smaller left
    }
    int t=a[i+1]; a[i+1]=a[hi]; a[hi]=t;   // place pivot in final position
    return i+1;
}
```

PATTERN: GRAPH / GRID EXTRA

**95. Flood Fill**
**BF:** n/a — DFS/BFS from the start pixel is the standard approach
**Opt:** DFS, recolor matching neighbors recursively - O(rows*cols)
```java
public int[][] floodFill(int[][] image, int sr, int sc, int color) {
    int oldColor = image[sr][sc];
    if (oldColor!=color) fill(image, sr, sc, oldColor, color);
    return image;
}
private void fill(int[][] img, int i, int j, int oldColor, int newColor) {
    if (i<0||i>=img.length||j<0||j>=img[0].length||img[i][j]!=oldColor) return;
    img[i][j]=newColor;
    fill(img,i+1,j,oldColor,newColor); fill(img,i-1,j,oldColor,newColor);
    fill(img,i,j+1,oldColor,newColor); fill(img,i,j-1,oldColor,newColor);
}
```

**96. Rotting Oranges (multi-source BFS, minutes to rot all)**
**BF:** repeatedly scan whole grid each minute until no change - O(rows*cols) per minute, slow
**Opt:** multi-source BFS, start from all rotten oranges simultaneously - O(rows*cols)
```java
public int orangesRotting(int[][] grid) {
    Queue<int[]> q = new LinkedList<>();
    int fresh=0;
    for (int i=0;i<grid.length;i++)
        for (int j=0;j<grid[0].length;j++) {
            if (grid[i][j]==2) q.add(new int[]{i,j});   // all initial rotten sources
            else if (grid[i][j]==1) fresh++;
        }
    int minutes=0;
    int[][] dirs = {{1,0},{-1,0},{0,1},{0,-1}};
    while (!q.isEmpty() && fresh>0) {
        int size=q.size();
        for (int k=0;k<size;k++) {
            int[] cell = q.poll();
            for (int[] d: dirs) {
                int ni=cell[0]+d[0], nj=cell[1]+d[1];
                if (ni>=0&&ni<grid.length&&nj>=0&&nj<grid[0].length&&grid[ni][nj]==1) {
                    grid[ni][nj]=2; fresh--; q.add(new int[]{ni,nj});  // newly rotten
                }
            }
        }
        minutes++;
    }
    return fresh==0 ? minutes : -1;
}
```

**97. Number of Provinces (connected components via adjacency matrix)**
**BF:** n/a — DFS from every unvisited city is the standard approach (Union-Find is the alternative, same complexity class)
**Opt:** DFS/Union-Find over adjacency matrix - O(n^2)
```java
public int findCircleNum(int[][] isConnected) {
    int n = isConnected.length;
    boolean[] visited = new boolean[n];
    int provinces=0;
    for (int i=0;i<n;i++) {
        if (!visited[i]) { dfs(isConnected, visited, i); provinces++; }  // new province found
    }
    return provinces;
}
private void dfs(int[][] mat, boolean[] visited, int i) {
    visited[i]=true;
    for (int j=0;j<mat.length;j++)
        if (mat[i][j]==1 && !visited[j]) dfs(mat, visited, j);
}
```

PATTERN: DESIGN

**98. Implement Trie (Prefix Tree)**
**BF:** n/a — a HashSet of all strings works for exact search but can't do efficient prefix search
**Opt:** tree of child nodes per character, isEnd flag per node - O(L) per operation
```java
class Trie {
    class Node { Node[] children = new Node[26]; boolean isEnd; }
    private Node root = new Node();
    public void insert(String word) {
        Node curr = root;
        for (char c: word.toCharArray()) {
            int idx = c-'a';
            if (curr.children[idx]==null) curr.children[idx] = new Node();
            curr = curr.children[idx];
        }
        curr.isEnd = true;
    }
    public boolean search(String word) {
        Node node = find(word);
        return node!=null && node.isEnd;
    }
    public boolean startsWith(String prefix) { return find(prefix)!=null; }
    private Node find(String s) {
        Node curr = root;
        for (char c: s.toCharArray()) {
            int idx = c-'a';
            if (curr.children[idx]==null) return null;   // path breaks, not found
            curr = curr.children[idx];
        }
        return curr;
    }
}
```

**99. Design Circular Queue**
**BF:** n/a — a fixed array with head/tail pointers wrapping around IS the standard approach
**Opt:** array with modulo-wrapped front/rear indices, size counter - O(1) per operation
```java
class MyCircularQueue {
    private int[] data; private int head=0, count=0, capacity;
    public MyCircularQueue(int k) { data = new int[k]; capacity = k; }
    public boolean enQueue(int value) {
        if (count==capacity) return false;
        data[(head+count)%capacity] = value;   // wrap using modulo
        count++;
        return true;
    }
    public boolean deQueue() {
        if (count==0) return false;
        head = (head+1)%capacity;               // advance head, wrap around
        count--;
        return true;
    }
    public int Front() { return count==0 ? -1 : data[head]; }
    public int Rear() { return count==0 ? -1 : data[(head+count-1)%capacity]; }
}
```

PATTERN: DYNAMIC PROGRAMMING EXTRA

**100. Partition Equal Subset Sum**
**BF:** try including/excluding every element recursively - O(2^n)
**Opt:** subset-sum DP, dp[s] = reachable sum using items so far, target = total/2 - O(n*sum)
```java
public boolean canPartition(int[] nums) {
    int sum=0;
    for (int n: nums) sum+=n;
    if (sum%2!=0) return false;               // odd total can't split evenly
    int target = sum/2;
    boolean[] dp = new boolean[target+1];
    dp[0]=true;
    for (int n: nums)
        for (int s=target; s>=n; s--)          // iterate backward to avoid reuse in same pass
            dp[s] = dp[s] || dp[s-n];
    return dp[target];
}
```
