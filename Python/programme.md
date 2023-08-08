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
