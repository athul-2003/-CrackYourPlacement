- Question : https://www.geeksforgeeks.org/problems/minimum-cost-of-ropes-1587115620/1

```python
import heapq
from typing import List

class Solution:
    def minCost(self, arr: List[int]) -> int:
        # Step 1: Heapify the array
        heapq.heapify(arr)
        
        min_cost = 0
        
        # Step 2: Continue until only one rope remains
        while len(arr) > 1:
            # Step 3: Pop two smallest ropes
            first = heapq.heappop(arr)
            second = heapq.heappop(arr)
            
            # Step 4: Calculate the cost to connect them
            cost = first + second
            min_cost += cost
            
            # Step 5: Push the new rope back into the heap
            heapq.heappush(arr, cost)
        
        return min_cost
```
