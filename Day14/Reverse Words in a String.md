- Question : https://leetcode.com/problems/reverse-words-in-a-string/description/

```python
def reverseWords(self, s: str) -> str:
        l=s.split()

        beg=0
        end=len(l)-1

        while beg<end:
            l[beg],l[end]=l[end],l[beg]
            beg+=1
            end-=1
        s=' '.join(l)
        
        return s
```
