#### Conditional Statements (if, elif, else)
Video Outline:
1. Introduction to Conditional Statements
2. if Statement
3. else Statement
4. elif Statement
5. Nested Conditional Statements
6. Practical Examples
7. Common Errors and Best Practices


```python
## if statement
age=20

if age>=18:
    print("You are allowed to vote in the elections")
```

    You are allowed to vote in the elections



```python
age>=18
```




    True




```python
## else
## The else statement executes a block of code if the condition in the if statement is False.

age=16

if age>=18:
    print("You are eligible for voting")
else:
    print("You are a minor")


```

    You are a minor



```python
## elif
## The elif statement allows you to check multiple conditions. It stands for "else if"

age=17

if age<13:
    print("You are a child")
elif age<18:
    print("You are a teenager")
else:
    print("You are an adult")
```

    You are a teenager



```python
## Nested Condiitonal Statements

# You can place one or more if, elif, or else statements inside another if, elif, or else statement to create nested conditional statements.

## number even ,odd,negative

num=int(input("Enter the number"))

if num>0:
    print("The number is positive")
    if num%2==0:
        print("The number is even")
    else:
        print("The number is odd")

else:
    print("The number is zero or negative")
```

    The number is zero or negative



```python
## Practical Examples

## Determine if a year is a leap year using nested condition statement

year=int(input("Enter the year"))

if year%4==0:
    if year%100==0:
        if year%400==0:
            print(year,"is a leap year")
        else:
            print(year,"is not a leap year")
    else:
        print(year,"is a leap year")

else:
    print(year,"is not a leap year")



```

    2024 is a leap year



```python
## Assignment
## Simple Calculator program
# Take user input
num1 = float(input("Enter first number: "))
num2 = float(input("Enter second number: "))
operation = input("Enter operation (+, -, *, /): ")

# Perform the requested operation
if operation == '+':
    result = num1 + num2
elif operation == '-':
    result = num1 - num2
elif operation == '*':
    result = num1 * num2
elif operation == '/':
    if num2 != 0:
        result = num1 / num2
    else:
        result = "Error! Division by zero."
else:
    result = "Invalid operation."

print("Result:", result)
```

    Result: 36.0



```python
### Determine the ticket price based on age and whether the person is a student.
# Ticket pricing based on age and student status

# Take user input
age = int(input("Enter your age: "))
is_student = input("Are you a student? (yes/no): ").lower()

# Determine ticket price
if age < 5:
    price = "Free"
elif age <= 12:
    price = "$10"
elif age <= 17:
    if is_student == 'yes':
        price = "$12"
    else:
        price = "$15"
elif age <= 64:
    if is_student == 'yes':
        price = "$18"
    else:
        price = "$25"
else:
    price = "$20"

print("Ticket Price:", price)


```

#### Complex Example 3: Employee Bonus Calculation

Calculate an employee's bonus based on their performance rating and years of service.


```python
# Employee bonus calculation

# Take user input
years_of_service = int(input("Enter years of service: "))
performance_rating = float(input("Enter performance rating (1.0 to 5.0): "))

# Determine bonus percentage
if performance_rating >= 4.5:
    if years_of_service > 10:
        bonus_percentage = 20
    elif years_of_service > 5:
        bonus_percentage = 15
    else:
        bonus_percentage = 10
elif performance_rating >= 3.5:
    if years_of_service > 10:
        bonus_percentage = 15
    elif years_of_service > 5:
        bonus_percentage = 10
    else:
        bonus_percentage = 5
else:
    bonus_percentage = 0

# Calculate bonus amount
salary = float(input("Enter current salary: "))
bonus_amount = salary * bonus_percentage / 100

print("Bonus Amount: ${:.2f}".format(bonus_amount))

```

## Complex Example 4: User Login System
A simple user login system that checks the username and password.


```python
# User login system

# Predefined username and password
stored_username = "admin"
stored_password = "password123"

# Take user input
username = input("Enter username: ")
password = input("Enter password: ")

# Check login credentials
if username == stored_username:
    if password == stored_password:
        print("Login successful!")
    else:
        print("Incorrect password.")
else:
    print("Username not found.")

```

    Username not found.



```python

```
