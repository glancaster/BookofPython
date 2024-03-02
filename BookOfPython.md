# Book Of Python

By Graham Lancaster

## Overview

This book provides practical insights into Python programming, including code snippets, essential libraries, and language nuances. It's highly recommended to code along with the examples provided to enhance your learning experience. Topics covered include:

- Best Practices
- Modularization
- Keyboard Shortcuts
- Built-ins
- Essential Tools
- Code Optimization
- Automation

## About the Author

I've been self-teaching coding since 2019, discovering its potential to craft creative projects that enhance daily life. While Python is my primary language, I also have experience in C, C++, C#, LabVIEW, Matlab, and HTML/CSS. Currently, I'm seeking to expand my expertise and undertake projects in C++.

## Setup

As of writing, I utilize Python 3.12.1 and Visual Studio Code for my coding endeavors.

# Table of Contents

- [Book Of Python](#book-of-python)
  - [Overview](#overview)
  - [About the Author](#about-the-author)
  - [Setup](#setup)
- [Table of Contents](#table-of-contents)
- [Built - Ins](#built---ins)
  - [Strings](#strings)
    - [Print a String](#print-a-string)
    - [Print out variables, change how it outputs and do evaluations](#print-out-variables-change-how-it-outputs-and-do-evaluations)
    - [Debug your variables with a `variable=`](#debug-your-variables-with-a-variable)
    - [Text can be centered](#text-can-be-centered)
    - [Display dates your own way](#display-dates-your-own-way)
    - [Find where things happen in a string or if a word exists in string](#find-where-things-happen-in-a-string-or-if-a-word-exists-in-string)
    - [Find words that end in -ly](#find-words-that-end-in--ly)
    - [Split a message based on criteria](#split-a-message-based-on-criteria)
    - [Long Strings](#long-strings)
    - [Find the closest string match](#find-the-closest-string-match)
  - [Numbers](#numbers)
    - [Common Operations](#common-operations)
    - [Get the remainder of a division, modulo operator](#get-the-remainder-of-a-division-modulo-operator)
    - [Readability of Long Numbers](#readability-of-long-numbers)
    - [Check if variable in a Number](#check-if-variable-in-a-number)
  - [Lists](#lists)
  - [Dictionaries](#dictionaries)
  - [Sets](#sets)
  - [Functions](#functions)
  - [Classes](#classes)
    - [Edit and call **str** and **repr** from print statements](#edit-and-call-str-and-repr-from-print-statements)
- [Import This](#import-this)
- [Helpful Snippets](#helpful-snippets)
  - [Get multiples of a number in a list](#get-multiples-of-a-number-in-a-list)
- [References](#references)
  - [Helpful](#helpful)
  - [Libraries](#libraries)

# Built - Ins

## Strings

### Print a String

```Python
print("Hello World")
print("Hello" + "World")
print("Hello", "World")
```

```code
Hello World
HelloWorld
Hello World
```

### Print out variables, change how it outputs and do evaluations

```Python
message = "Hello"
number = 39.239

print(f"{message} World")
# Round to the ones decimal place
print(f"{number:.1f}")
print(f"{number + 10}")
```

```code
Hello World
39.2
49.239
```

```code
name = "Brad"
age = 29

print("Hello %s" % name)
print("%s is %s years old" % (name, age))
# Shifts the second row by 5 spaces
print("Age: %(age)s\nAge: %(age)5s" % {"age" : age})
```

```code
Hello Brad
Brad is 29 years old
Age: 29
Age:    29
```

```Python
largenumber = 183984943.34893

print(f"${largenumber:,.2f}")
print(f"{largenumber:{"_"}}")
```

```code
$183,984,943.35
183_984_943.34893
```

### Debug your variables with a `variable=`

```Python
print(f"{largenumber= }")
```

```code
largenumber= 183984943.34893
```

### Text can be centered

```Python
print(f"{"Title":-^30}")
```

```code
------------Title-------------
```

### Display dates your own way

```Python
date = (9,5,2023)

print(f"{date[0]:02}/{date[1]:02}/{date[2]}")
```

```code
09/05/2023
```

```Python
from datetime import datetime

date = datetime(2043, 3, 15, 16, 23)

print(f"{date:%m/%d/%Y} at {date:%I:%M %p} which is on a {date:%A} in {date:%B}")
```

```code
03/15/2043 at 04:23 PM which is on a Sunday in March
```

### Find where things happen in a string or if a word exists in string

```Python
message = "Hello, it is nice out today"

print(message.find("nice"))
print(message.find("rainy"))
```

```code
13
-1
```

### Find words that end in -ly

```Python
import re

message = "The boat trip went by quickly"
re.findall(r"\w+ly\b", message)
```

```code
['quickly']
```

### Split a message based on criteria

```Python
import re

message = "Dear John, I hope this message finds you well"
message.split(',')
message.split() # This leaves the comma attached to John
re.split(' |, ', message) # Splits when it sees a comma or space

```

```code
['Hey John', ' how are you']
['Hey', 'John,', 'how', 'are', 'you']
['Hey', 'John', 'how', 'are', 'you']
```

### Long Strings

```Python
longtext = ("my view on this sentence is "
            "that it is very long "
            "but you can break it up like this.")
longmessage = "or you can break it up like this " \
            "using the backslash symbol. " \
            "very neat indeed"
```

```code
'my view on this sentence is that it is very long but you can break it up like this.'
'or you can break it up like this using the backslash symbol. very neat indeed'

```

### Find the closest string match

```Python
from difflib import get_close_matches

dogs = ['Frenchie', 'Lab', 'Corgi', 'Bulldog']
get_close_matches('Frencher', dogs)
```

```code
['Frenchie']
```

## Numbers

### Common Operations

```Python
firstNum = 10
secondNum = 5

print(10+5)
print(firstNum + secondNum)
print(firstNum - secondNum)
```

```code
15
15
5
```

```Python
print(3/2)   # Long Division
print(3//2)  # Floor Division
```

```code
1.5
1
```

```Python
print(4*2)
print(4**2)
```

```code
8
16
```

### Get the remainder of a division, modulo operator

```Python
9 % 4
15 % 5 # if it returns 0 then it is divisible by that number
```

```code
1
0
```

### Readability of Long Numbers

```Python
longNum = 348320239304
longNumber = 348_320_239_304  # Use _ to help break up the large number
longNumber == longNum
```

```code
True
```

### Check if variable in a Number

```Python
from numbers import Number
a = 6
b = 3.5
c = 'string'

print(isinstance(a,Number))
print(isinstance(b,Number))
print(isinstance(c,Number))
```

```code
True
True
False
```

## Lists

## Dictionaries

## Sets

## Functions

## Classes

### Edit and call **str** and **repr** from print statements

```Python
class Dog:
    def __init__(self, name, breed):
        self.name = name
        self.breed = breed
    def __str__(self):
        return f"Hello {self.name}, you are a {self.breed}"
    def __repr__(self):
        return f"{type(self).__name__}(name='{self.name}', breed={self.breed})"

firstDog = Dog("Bug", "Frenchie")

print(f"User Friendly ::: {firstDog!s}")
print(f"Developer Friendly ::: {firstDog!r}")
```

```Python
User Friendly ::: Hello Bug, you are a Frenchie
Developer Friendly ::: Dog(name='Bug', breed=Frenchie)
```

# Import This

# Helpful Snippets

### Get multiples of a number in a list

```Python
def getMultiples(numList : list, num : int) -> list:
    """Gets the mutliples of num that exist in numList

    Args:
        numList (list): list of numbers
        num (int): number to get multiple of

    Returns:
        list: list of numbers that are multiples of num
    """
    return [x for x in numList if x % num == 0]

numbers = [2,3,5,7,9,12,15]
getMultiples(numbers, 3)
```

```code
[3, 9, 12, 15]
```

# References

## Helpful

- [khuyentran1401.github.io](https://khuyentran1401.github.io/Efficient_Python_tricks_and_tools_for_data_scientists/README.html)
- [F-Strings](https://realpython.com/python-f-strings/)

## Libraries

- [datetime](https://docs.python.org/3/library/datetime.html#module-datetime)
- [re](https://docs.python.org/3/library/re.html#)
- [difflib](https://docs.python.org/3/library/difflib.html#)
