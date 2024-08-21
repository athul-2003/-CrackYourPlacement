- Question : https://leetcode.com/problems/4sum/description/

```python
def fourSum(self, nums: List[int], target: int) -> List[List[int]]:
        n=len(nums)
        res=[]
        nums.sort()

        for i in range(n-3):          # First element
            if i>0 and nums[i]==nums[i-1]:
                continue
            for j in range(i+1,n-2):   # Second element
                if j>i+1 and nums[j]==nums[j-1]:
                    continue

                left=j+1
                right=n-1      # Two pointers for third and fourth elements
                while left<right:
                    total=nums[left]+nums[right]+nums[i]+nums[j]

                    if total==target:
                        res.append([nums[i],nums[j],nums[left],nums[right]])

                        while left < right and nums[left]==nums[left+1]:
                            left+=1
                        while left < right and nums[right]==nums[right-1]:
                            right-=1
                        left+=1
                        right-=1

                    elif total<target:
                        left+=1
                    else:
                        right-=1
        return res
```