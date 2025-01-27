---
extends: _layouts.documentation
section: content
title: Python
description: Python Dev Snippets
---

# Python

## Requirements

```bash
# Get the requirments to a file
pip freeze -r myrequiremets.txt


# Installing the modules from the requirments file
pip install -r myrequirements.txt


```

--- 

## Preventing user input during sleep. 

This function disables all user input if used after a sleep function. As this uses the msvcrt module, this is only usable on Microsoft Windows.

```python
import msvcrt
def disableInput():
    while msvcrt.kbhit(): msvcrt.getwch()

#example usage
time.sleep(5)
disableInput()
input("Press enter to continue...")

```

---

## Python 3 f-strings: formatted string literals

The new f-Strings are string literals that start with an `f` at the beginning, and allow for expressions to be evaluated inside of curly braces. This is way easier to keep track of, especially with a long set of parameters and strings.

#### Simple Syntax
```python
name = "Sal"
age = 33
f"Hello, {name}. You are {age}"
# 'Hello, Sal. You are 33.'

# Capital `F` is also valid
F"Hello, {name}. You are {age}"
# 'Hello, Sal. You are 33.'

# The output returned is a string, with single quotes, but you can wrap f-Strings in the print command, too.
print(f"{name} is {age} and that is great!")
# Sal is 33 and that is great!
```
#### Arbitrary Expressions
Since f-Strings are evaluated at runtime, you can put any valid Python expression inside of them. This allows for some cool things to happen!
```python
# The basics
f"{2 * 21}"
# '42'

# You can call functions
def to_lowercase(input):
    return input.lower()

name = "Sal Mac"
f"{to_lowercase(name)} loves to code."
# 'sal mac loves to code.'

```

---

## Two Matrix Multiplication 

The following python snippet is for multiplication of two matrix. simply using for loops & list.

```python
r1 = int(input("Enter no. of rows of first matrix : "))
c1 = int(input("Enter no. of coloumns of first matrix : "))
r2 = int(input("Enter no. of rows of second matrix : "))
c2 = int(input("Enter no. of coloumns of second matrix : "))
C = []
D = []
A = []

print("\nFirst Matrix :")
for i in range(r1):
    
    temp1 = []
    for i in range(c1):
        
       temp1.append(float(input("Enter a value : "))) #values of first matrix
    A.append(temp1)

B = []
print("\nSecond Matrix :")
for i in range(r2):
    
    temp2 = []
    for i in range(c2):
        
       temp2.append(float(input("Enter a value : "))) #values of second matrix
    B.append(temp2)

print("\nFirst Matrix : ",A)
print("Second Matrix : ",B)

for i in range(r1):
    for j in range(c2):
        s= 0
        for k in range(c1):
            s = s+(A[i][k]*B[k][j]) # perform matrix multiplication
        C.append(s)
  
    D.append(C)
    C = []
 
print("\nFinal Matrix : ",D) # final matrix after multiplication

```
## Useful Function - Force 2 Decimals
This function returns the given integer as a string with 2 decimals points, useful for prices.
```python
def forceTwoDecimals(integer):
    if str(round(integer,2)) == str(round(integer,1)):
        return str(integer)+"0"
    else: 
        return str(integer)
```


### Reversing A string
```python
test_string="test string"
reverse_test_string=test_string[::-1]
print(reverse_test_string)
```

Output: "gnirts tset"

## Useful Function - isPalindrome
This function returns true if a given string is a palindrome
```python
def isPalindrome(str):
    return str == str[::-1]
```


#### Note :
As a python developer, be careful with Python indentation. sometimes even if lines look visually indented, from python perspective they maybe are not indented & causes errors. IDEs like PyCharm are useful for debugging and avoiding common errors such as this.
