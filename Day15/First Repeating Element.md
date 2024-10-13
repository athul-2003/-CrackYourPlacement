- Question : https://www.geeksforgeeks.org/batch/ds-with-python/track/hashing-basic-python/problem/first-repeating-element4018

```python
def firstRepeated(self,arr):
        
        #arr : given array
        #n : size of the array
        
        dict1={}
        first_index={}
        
        for i,ele in enumerate(arr):
            if ele in dict1:
                dict1[ele]+=1
            else:
                dict1[ele]=1
                first_index[ele]=i+1
                
        min_index=float('inf')
        
        for num,val in dict1.items():
            if val>1:
                min_index=min(min_index,first_index[num])
                
        if min_index==float('inf'):
            return -1
        else:
            return min_index
```
