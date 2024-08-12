- Question : https://leetcode.com/problems/subarray-sum-equals-k/description/

```python
def subarraySum(self, nums: List[int], k: int) -> int:
        count=0
        prefix_sum={0:1}    # Start with sum 0 occurring once
        current_sum=0

        for num in nums:
            current_sum+=num    # Update the running total
            if (current_sum-k) in prefix_sum:
                count+=prefix_sum[current_sum-k]    # Add the number of times this sum was seen
            if current_sum in prefix_sum:
                prefix_sum[current_sum]+=1
            else:
                prefix_sum[current_sum]=1
        return count
```
