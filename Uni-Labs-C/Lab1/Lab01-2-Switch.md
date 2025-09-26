#решение с использованием конструкции Switch case

```c
#include <stdio.h>
int main() {
    int x;
    int y;
    int caseSelector;
    printf("Welche number x: ");
    scanf_s("%d", &x);
    
    if (x < 0) {
        if (x <= -10) {
            caseSelector = 1;
        } else {
            caseSelector = 2;
        }
    } else {
        if (x < 7) {
            caseSelector = 3;
        } else if (x < 11) {
            caseSelector = 2;
        } else {
            caseSelector = 1;
        }
    }

    switch (caseSelector) {
        case 1:
            y = -3 * x / 7 + 10;
            printf("y = -3x/7 + 10 = %d\n", y);
            break;
        case 2:
            printf("kein antwort\n");
            break;
        case 3:
            y = -6 * x * x + 8;
            printf("y = -6x^2 + 8 = %d\n", y);
            break;
    }
}
```
