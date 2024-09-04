```python
def generateSubstrings(string):
    substrings = []
    length = len(string)
    
    for i in range(length):
        for j in range(i + 1, length + 1):
            substrings.append(string[i:j])
    
    return substrings
```
