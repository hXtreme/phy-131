# Exam 1
_Date: 26 Jun, 2020_  
__Name: Harsh Parekh__  
__ID: hnp29__


```python
from math import *
from cmath import *
import numpy as np

rtd = 180.0/pi
dtr = pi/180
```


```python
def f_polar(r, theta):
    x = r*cos(theta)
    y = r*sin(theta)
    return complex(x, y)
```

## Question 1


```python
A = 5 + 5j
B = 7 + 1j

rtd*(phase(A) - phase(B))
```




    36.86989764584402



## Question 2


```python
A = 3 + 9j
B = 1 + 3j

abs(A + B)
```




    12.649110640673518



## Question 3


```python
A = 3 + 9j
B = 1 + 3j

rtd*phase(A + B)
```




    71.56505117707799



## Question 4


```python
A = f_polar(25, dtr*30)
B = f_polar(10, dtr*60)

abs(A - B)
```




    17.08763582558397



## Question 5 - 9


```python
x = lambda t: 3*(t**2) + 8*t - 10
v = lambda t: 6*t + 8
a = lambda t: 6

s = x(7) - x(2)
v_avg = s / (7 - 2)
a_avg = (v(7) - v(2)) / (7 - 2)
print(
    f'5) v_5   : {v(5)}',
    f'6) a_5   : {a(5)}',
    f'7) s     : {s}',
    f'8) v_avg : {v_avg}',
    f'9) a_avg : {a_avg}',
    sep='\n'
)
```

    5) v_5   : 38
    6) a_5   : 6
    7) s     : 175
    8) v_avg : 35.0
    9) a_avg : 6.0


## Question 10


```python
def time_to_fall(h, g=9.81, u=0):
    if u != 0:
        raise NotImplementedError()
    return (2*h / g)**0.5

time_to_fall(55)
```




    3.3485889431663027



## Question 11


```python
def max_height(u, g=9.81, x0=0):
    return (u**2 / (2*g)) + x0

max_height(15, x0=1)
```




    12.46788990825688



## Question 12


```python
def drop_height(v=None, t=None, g=9.81):
    if (v is None) == (t is None):
        raise AttributeError("Exaxtly one of u or t must be specified.")
    if (v is None):
        return g*(t**2) / 2
    else:
        return v**2 / (2*g)

drop_height(v=21)
```




    22.477064220183486



## Question 13 - 14

13: 0 m/s  
14: 1.5s (symmetry)

## Question 15 - 17


```python
u = f_polar(32, dtr*25)
g = 9.81
x0 = 1.5

t = u.imag/g
d_x = u.real * (2*t)

print(
    f'15) t   : {t}',
    f'16) d_x : {d_x}',
    f'17) h   : {max_height(u.imag, x0=x0)}',
    sep='\n'
)
```

    15) t   : 1.3785712921205282
    16) d_x : 79.96223341017671
    17) h   : 10.821750450585721


## Question 18

A: 2i - 5j m/s

## Question 19


```python
cop = 25j
civ = 35

civ_rel_cop = civ - cop
print(
    f'{civ_rel_cop.real}i {civ_rel_cop.imag}j'
)
```

    35.0i - 25.0j


## Question 20


```python
v = 35 - 25j

rtd*phase(v)
```




    -35.53767779197438


