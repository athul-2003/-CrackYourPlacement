- Question : https://www.geeksforgeeks.org/print-all-the-duplicates-in-the-input-string/

```python
def printDups(strng):
  
  dict1={}
  
  for ele in strng:
    if ele in dict1:
      dict1[ele]+=1
    else:
      dict1[ele]=1
      
  for key,val in dict1.items():
    if val>1:
      print(f"{key}, count = {val}")
      
str = "test string"
printDups(str)
```

Output : 

- t, count = 3
- s, count = 2
