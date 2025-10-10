```py
print("Welch Zahl x:")
x = int(input())

if x >= 0 and x < 7:
    y = -6 * x * x + 8
    print("y = -6x^2 + 8 = ", y)
elif x <= 10 or x >= 11:
    y = -3 * x / 7 + 10
    print("y = -3x/7 + 10 = ", y)
else:
    print("kein antwort")
```
