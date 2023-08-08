python program factorial of number
-----------------------------------
```
def fact(y):
    count=1
    while(y>0):
        count=count*y
        y-=1
    return count

x=int(input("Enter number"))
print(fact(x))
```




Array
======


Add all array element
----------------------
```
l=[5,3,9,2,1]
count=0
for i in l:
    count=count+i
print(count)

```

