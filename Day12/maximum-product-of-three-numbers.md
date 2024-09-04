- Question : https://leetcode.com/problems/maximum-product-of-three-numbers/description/

```python
def maximumProduct(self, nums: List[int]) -> int:

        nums.sort()
        # Calculate the product of the three largest numbers
        pro1=nums[-1]*nums[-2]*nums[-3]
        # Calculate the product of the two smallest numbers (possibly negative) and the largest number
        pro2=nums[0]*nums[1]*nums[-1]

        return max(pro1,pro2)
```
