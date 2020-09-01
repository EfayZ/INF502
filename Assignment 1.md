**1. Write a function with the following signature:** `pythagoreanTheorem(length_a, length_b)`.

```
import math
def pythagoreanTheorem(length_a, length_b):
    length_hypotenuse = math.sqrt((length_a**2) + (length_b**2))
    print(length_hypotenuse)
```

```
>>> pythagoreanTheorem(2, 2)
2.8284271247461903
>>> pythagoreanTheorem(1, 1)
1.4142135623730951
>>> pythagoreanTheorem(3, 4)
5.0
```

**2. Write a function with the following signature:** `list_mangler(list_in)`.

```
def list_mangler(list_in):
    list_out = list()
    for a in list_in:
        if a%2 == 0:
            list_out.append(a*2)
        else: 
            list_out.append(a*3)
    print(list_out)
```
```
>>> list_mangler([1, 2, 3, 4])
[3, 4, 9, 8]
>>> list_mangler([5, 6, 7, 8])
[15, 12, 21, 16]
>>> list_mangler([12, 11, 10, 9])
[24, 33, 20, 27]
```

**3. Write a function with the following signature:** `grade_calc(grades_in, to_drop)`.

```
def grade_calc(grades_in, to_drop):
    grades_in.sort()
    grades_in = grades_in[to_drop:]
    grades_out = sum(grades_in)/len(grades_in)
    if grades_out >= 90:
        print("A")
    elif grades_out >= 80:
        print("B")
    elif grades_out >= 70:
        print("C")
    elif grades_out >= 60:
        print("D")
    else:
        print("F")
```
```
>>> grade_calc([100, 90, 80, 95], 2)
A
>>> grade_calc([10, 52, 44, 65], 2)
F
>>> grade_calc([10, 99, 89, 95, 55, 66, 44, 33], 4)
B
```

**4. Write a function with the following signature:** `odd_even_filter(numbers)`.

```
def odd_even_filter(numbers):
    even_numbers = list()
    odd_numbers = list()
    for a in numbers:
        if a%2 == 0:
            even_numbers.append(a)
        else: 
            odd_numbers.append(a)
    numbers.clear()
    numbers.append(even_numbers)
    numbers.append(odd_numbers)
    print(numbers)
```
```
>>> odd_even_filter([1, 2, 3, 4, 5, 6, 7, 8, 9])
[[2, 4, 6, 8], [1, 3, 5, 7, 9]]
>>> odd_even_filter([11, 22, 333, 444, 555, 66, 77, 88, 99])
[[22, 444, 66, 88], [11, 333, 555, 77, 99]]
>>> odd_even_filter([12, 23, 34, 45, 56, 67, 78, 89, 90, 120, 2333, 6666])
[[12, 34, 56, 78, 90, 120, 6666], [23, 45, 67, 89, 2333]]
```
