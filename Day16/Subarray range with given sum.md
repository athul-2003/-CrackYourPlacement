- Question : https://www.geeksforgeeks.org/problems/subarray-range-with-given-sum0128/1

```python
def count_subarrays_with_sum(arr, tar):
    # Dictionary to store the frequency of prefix sums
    prefix_sums = {}
    
    # Initialize prefix sum and result counter
    prefix_sum = 0
    count = 0
    
    # To account for subarray starting from index 0
    prefix_sums[0] = 1
    
    for num in arr:
        # Update the running prefix sum
        prefix_sum += num
        
        # Check if prefix_sum - tar exists in the map
        if (prefix_sum - tar) in prefix_sums:
            count += prefix_sums[prefix_sum - tar]
        
        # Update the frequency of the current prefix sum in the map
        if prefix_sum in prefix_sums:
            prefix_sums[prefix_sum] += 1
        else:
            prefix_sums[prefix_sum] = 1
    
    return count
```
