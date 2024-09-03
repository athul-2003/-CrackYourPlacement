- Question : https://www.geeksforgeeks.org/problems/min-number-of-flips3210/1?itm_source=geeksforgeeks&itm_medium=article&itm_campaign=practice_card

```python
def minFlips(self, S):
        # Code here
        flip_0_start=0
        flip_1_start=0
        
        for i in range(len(S)):
            if i%2==0:
                if S[i]!='0':
                    flip_0_start+=1
            else:
                if S[i]!='1':
                    flip_0_start+=1
            
            if i%2==0:
                if S[i]!='1':
                    flip_1_start+=1
            else:
                if S[i]!='0':
                    flip_1_start+=1
        return min(flip_0_start,flip_1_start)

# consider the required output as:
      # 010101    or
      # 101010
```
