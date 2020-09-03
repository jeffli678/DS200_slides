# Python Basic

Author: Xusheng Li

--- 

## Why Python

Python is now extremely **popular**
Python is used in many fields, including **Data Science**
Python is relatively **easy to learn and read**
Python language is **highly flexible**
Python has very good **library support**

--- 

## What Python is not good at

Python is so flexible that people can write **bugs hard to find**
Python is relatively **slow** (~10-100 times slower than C)

--- 

## A Brief History of Python

- Python is created by Guido van Rossum and first released in 1991 
    - Slightly older than me!
- Python 2.0 was released in 2000
- Python 3.0 was released in 2008
- Python 2 was officially discontinued in 2020
    - But it is still used in a lot of places (SAD)
- The latest stable release of Python 3 is 3.8.5 (20 July 2020)
- Python 2 and 3 are similar to each other
    - But the differences can sometimes drive newbie (experts) crazy
- What we will cover are mostly common in both Python 2 and 3

---

## Installation

---

## Windows Users

- Download Python installer from the official website
    - https://www.python.org/ftp/python/3.8.5/python-3.8.5-amd64.exe

- Double-click to run it
- Check the "Add Python to PATH" checkbox
- Click next until it installs
- Open a Command Prompt (cmd), run "python" in it

---

## macOS Fans

- macOS comes with python preinstalled
- Open your terminal
- And run python3
- You are all set

---

## Linux Lovers

If you are using Linux, you already have Python installed
And you can likely skip this tutorial

---

## Getting a code editor

---

- You do not have to use a code editor
    - Yeah, one can code with notepad
- But a good code editor can make your life easier
- Be warned this is a highly debated issue among the programmers:
    - "What is the best code editor?"

---

## VS Code is not the best, not the worst

https://code.visualstudio.com/
It is not hard to get it installed

--- 

## Python is Interpreted

Python is `interpreted`, which means you do not need to compile the program before you run it

```Python
$ python3
Python 3.8.2 (default, Jul 16 2020, 14:00:26) 
[GCC 9.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> 1+1
2
```
---

## Python can be used as a calculator

```Python
>>> 1 + 1 
2
>>> 10 - 6
4
>>> 99 * 128
12672
>>> 100 / 5
20.0
>>> 1 / 3
0.3333333333333333
```

For division, Python 3 does floating-point division by default

---

If you wish to do an integer division, use `//`
```Python
>>> 20 // 3
6
>>> 100 // 7
14
```

Use `%` for modulus calculation
```Python
>>> 20 % 3
2
>>> 100 % 7
2
```

---

## Use Parenthesis to specify the order of the computation

```Python
>>> (1 + 3) * 10
40
>>> (5 - 2) / 20
0.15
```

--- 

## Python can handle arbitrarily large integer numbers

Well, up to the RAM limit of your computer
```Python
>>> 1111111111111111111111111111111111111111111111111111111111111111111*
55555555555555555555555555555555555555555555555555555555555555555555555\
55555555555555555555555555555555555555555555555555555555555555555555555\
555555555555555555555555555555555555555555555555
617283950617283950617283950617283950617283950617283950617283950617222222\
222222222222222222222222222222222222222222222222222222222222222222222222\
222222222222222222222222222222222222222222222160493827160493827160493827\
1604938271604938271604938271604938271605
```
---

## Variables 

A `variable` is "a symbolic name associated with a value and whose associated value may be changed" (Wikipedia)

```Python
>>> x = 3
>>> print(x)
3
>>> x = 10
>>> print(x)
10
```
---

## Be careful!

Python does not enforce a strong type on variables,
which means you can change the type of a variable

```Python
>>> x = 3
>>> x = 'abc'
>>> print(x)
abc
```

Please `NEVER` ever do this!

---

## Strings

- In Python, a string can be double-quoted or single-quoted
- There are some differences, but we will not mention it today

```Python
>>> s1 = 'hello'
>>> s2 = "goodbye"
>>> s1 + s2
'hellogoodbye'
>>> s1 + " " + s2
'hello goodbye'
```

---

## Writing a script with Python

If we wish to do more stuff in one Python program,
we prefer to put all the code in a file and run it all at once. 
Save the following content to **main.py**

```Python
def main():
    l = range(100)
    val = sum(l)
    print(val)

main()
```
- main() is a function, and the last line simply calls the main to execute it
- the "main" function does not have to be called main()
- inside main(), there is stuff we have not covered yet. Feel free to ignore it

---

## Running a Python script

- Launch a cmd/terminal and cd to where you saved the main.py
    - you might put the main.py on the desktop so it is easier to get to it
- Type
    - "python main.py", if you are on Windows
    - "python3 main.py". if you are on macOS
    and press enter
- You should get something like this:

```Bash
 $ python3 main.py 
4950
```
---

## OMG, indentions!

---

- Python uses indentions to annotate code structures
- It is somehow restrictive and it has caused much criticism
- I will not defend the design decision
    - But you can get used to it quickly

```Python
def main():
    l = range(100)
    val = sum(l)
    print(val)

main()
```
- The indentions on the no.2/3/4 lines are MANDATORY!
- Python will complain if you do not properly deal with it
- I suggest you use "tab" to add indention
- If you are not sure where to put indentions, refer to some example code and see how they do it

---

## Life-saving tip

If you see an error message about indention but everything looks fine,
that's probably because you copied code from another place (lol I caught you)
and the indentions screw up.
```
To deal with it, delete all the indentions and redo them using tabs
```

---

## # Use comment to explain your code

- Comments are important for others to understand your code
- Code can be incomprehensible or confusing without proper comments
- For this class, we will not assign points for comments
    - But please try to practice it
- In Python, any line that starts with "#" is considered a comment

```Python
>>> # This is a comment
>>> # nothing happens
```
You can see that the interpreter does not return anything for the comments

---

## More on Strings

use `str()` to convert an integer to a string

```Python
>>> val = 10
>>> s = 'The value is ' + str(val)
>>> s
'The value is 10'
```

---

Use `int()` to convert a string to an integer

```Python
>>> s = "1024"
>>> val = int(s)
>>> val
1024
>>> s = "0x1234"
>>> val = int(s, 16)
>>> val
4660
```

---

Use `str[a, b]` to take part of a string

```Python
>>> s = 'this is a sentence'
>>> s[0:4]
'this'
>>> s[5:7]
'is'
```

If you omit `b`, the slice runs until the run of the string
If you omit `a`, it starts from the beginning

```Python
>>> s[5:]
'is a sentence'
>>> s[:9]
'this is a'
```

---

Use `find()` to look for a sub-string
It returns the index of the first occurrence of the sub-string

```Python
>>> s = 'this is a sentence'
>>> s.find('sentence')
10
```

If the substring is not found, it returns -1

```Python
>>> s.find('pizza')
-1
```
--- 

Be aware it does not understand the notion of `words`

```Python
>>> s.find('is')
2
```

What if you wish to find the first occurrence of the word "is"?

```Python
>>> s.split(' ')
['this', 'is', 'a', 'sentence']
```
---

## List

---

List is the most important construct in Python

```Python
>>> l = [3, 2, 7, 1, 4, 6, 5, 8, 9]
>>> type(l)
<class 'list'>
```

Do not use `list` as the variable name because it is a Python keyword!

---

List can be indexed

```Python
>>> l = [3, 2, 7, 1, 4, 6, 5, 8, 9]
>>> l[0]
3
>>> l[4]
4
>>> l[-1]
9
>>> l[-3]
5
```

Note: a negative index counts from the end

---

List member can be modified

```Python
>>> l[3] = 100
>>> l
[3, 2, 7, 100, 4, 6, 5, 8, 9]
```

---

Append to the end of a list

```Python
>>> l = [3, 2, 7, 1, 4, 6, 5, 8, 9]
>>> l.append(1234)
>>> l
[3, 2, 7, 1, 4, 6, 5, 8, 9, 1234]

```
Note, `append` modifies the list in-place, rather return it

Do NOT do this:

```Python
l = l.append(1234)
```

---

You can also `insert` new element at any index

```Python
>>> l = [3, 2, 7, 1, 4, 6, 5, 8, 9]
>>> l.insert(3, 100)
>>> l
[3, 2, 7, 100, 1, 4, 6, 5, 8, 9, 3]
```

Again, `insert` modifies the list rather return it

---

Delete a particular element from the list

```Python
>>> l = [3, 2, 7, 1, 4, 6, 5, 8, 9]
>>> del l[2]
>>> l
[3, 2, 1, 4, 6, 5, 8, 9]
```

---

Remove the element with a certain value from the list

```Python
>>> l = [1, 2, 3, 1, 2, 3]
>>> l.remove(1)
>>> l
[2, 3, 1, 2, 3]
```
Note, it only removes the first occurrence of value 1

---



List can be `sliced`

```Python
>>> l = [3, 2, 7, 1, 4, 6, 5, 8, 9]
>>> l[2 : 5]
[7, 1, 4]
>>> l[4 : ]
[4, 6, 5, 8, 9]
>>> l[-3 : ]
[5, 8, 9]
```

---

Checking membership

```Python
>>> l = [3, 2, 7, 1, 4, 6, 5, 8, 9]
>>> 2 in l
True
>>> 2020 in l
False
```
---

`len`, `min` and `max`

```Python
>>> l = [3, 2, -7, 1, 4, 6, 50, 8, 9]
>>> len(l)
9
>>> max(l)
50
>>> min(l)
-7
```
----

`count` how many times a value occurs in the list

```Python
>>> l = [1, 2, 3, 1, 2, 3]
>>> l.count(2)
2
```

---

Use `index` to look for things

```Python
>>> l2 = ['this', 'is', 'a', 'sentence']
>>> l2.index('is')
1
>>> l2.index('the')
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ValueError: 'the' is not in list
```
Note, if the value being searched is absent from the list,
it will trigger an exception

---

## if

---

`if` statement is important for code structure

```Python
if condition:
   true statement
else:
   false statement
```

---

```Python
a = input('please type an integer:')
a = int(a)
if a == 5:
    print('correct!')
else:
    print('try again')
```

Note, we use `==` for comparison of equality, not `=`

I am sure someone will encounter this

---

Use `elif` to organize more conditions

```Python
if condition 1:
   statement a
elif condition 2:
   statement b
else:
    statement c
```

---

## for

---

```Python
for loop_val in value_set:
    do_something
```

For example,

```Python
for i in [0, 1, 2, 3, 4]
    print(i * i)
```

Note, `range(n)` is a convenient way to get the list of integers from 0 to n-1

```Python
>>> list(range(10))
[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
```

---

## while

---

`while` is another way to implement loop

It is most suitable when you cannot easily express a value set


```Python
i = 0
while i < 10:
    print(i * i)
    i += 1
```

Or, you `break` out when a certain condition is met

```Python
i = 0
while True:
    print(i * i)
    i += 1
    if i > 10:
        break
```

---

## Function

---

`function` helps you better organize code

If an operation is repeated for 100 times, you do not have to repeat the code 100 times

```Python
def calc(val1, val2):
    val = val1 + val2 + val1 * val2
    print(val)
    return val
```

Now you can call it like this:

```Python
ret1 = calc(10, 4)
ret2 = calc(20, 8)
# ....
```

---

## Congratulations!

We have now covered a handful of Python features

To learn more, please refer to the references at the end of these slides

---

## One last thing: pip

---

`pip` is the package manager of Python

It lets you install packages easily

Packages are important for you to reuse other people's code

```Bash
pip install present
```

---

`present` is the package used to present these slides to you

The installation should succeed without any issue

Then you can run this command to view the slides

```Bash
present basic_python.md
```
---

## References

- Official tutorial: https://docs.python.org/3/tutorial/index.html
- Official language reference: https://docs.python.org/3/reference/index.html
- Book: "Beginning Python: From Novice to Professional, 2nd Edition"
- Google and StackOverflow