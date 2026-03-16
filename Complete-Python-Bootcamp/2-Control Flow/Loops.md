#### Loops
Video Outline:
1. Introduction to Loops
2. for Loop
   - Iterating over a range
   - Iterating over a string

3. while Loop
4. Loop Control Statements
    - break
    - continue
    - pass
5. Nested Loops
6. Practical Examples and Common Errors


```python
range(5)
```




    range(0, 5)




```python
## for loop

for i in range(5):
    print(i)
```

    0
    1
    2
    3
    4



```python
for i in range(1,6):
    print(i)
```

    1
    2
    3
    4
    5



```python
for i in range(1,10,2):
    print(i)
```

    1
    3
    5
    7
    9



```python
for i in range(10,1,-1):
    print(i)
```

    10
    9
    8
    7
    6
    5
    4
    3
    2



```python
for i in range(10,1,-2):
    print(i)
```

    10
    8
    6
    4
    2



```python
## strings

str="Krish Naik"

for i in str:
    print(i)
```

    K
    r
    i
    s
    h
     
    N
    a
    i
    k



```python
## while loop

## The while loop continues to execute as long as the condition is True.

count=0

while count<5:
    print(count)
    count=count+1



```

    0
    1
    2
    3
    4



```python
## Loop Control Statements

## break
## The break statement exits the loop permaturely

## break sstatement

for i in range(10):
    if i==5:
        break
    print(i)
   
```

    0
    1
    2
    3
    4



```python
## continue

## The continue statement skips the current iteration and continues with the next.

for i in range(10):
    if i%2==0:
        continue
    print(i)



```

    1
    3
    5
    7
    9



```python
## pass
## The pass statement is a null operation; it does nothing.

for i in range(5):
    if i==3:
        pass
    print(i)

```

    0
    1
    2
    3
    4



```python
## Nested loopss
## a loop inside a loop

for i in range(3):
    for j in range(2):
        print(f"i:{i} and j:{j}")
```

    i:0 and j:0
    i:0 and j:1
    i:1 and j:0
    i:1 and j:1
    i:2 and j:0
    i:2 and j:1



```python
## Examples- Calculate the sum of first N natural numbers using a while and for loop

## while loop  

n=10   
sum=0
count=1

while count<=n:
    sum=sum+count
    count=count+1

print("Sum of first 10 natural number:",sum)

```

    Sum of first 10 natural number: 55



```python
n=10   
sum=0
for i in range(11):
    sum=sum+i

print(sum)
```

    55



```python
## Example- Prime numbers between 1 and 100

for num in range(1,101):
    if num>1:
        for i in range(2,num):
            if num%i==0:
                break
        else:
            print(num)
```

    2
    3
    5
    7
    11
    13
    17
    19
    23
    29
    31
    37
    41
    43
    47
    53
    59
    61
    67
    71
    73
    79
    83
    89
    97


#### Conclusion:
Loops are powerful constructs in Python that allow you to execute a block of code multiple times. By understanding and using for and while loops, along with loop control statements like break, continue, and pass, you can handle a wide range of programming tasks efficiently.


```python

```
