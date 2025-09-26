#

```c
#include <stdio.h>
int main() {
    int x, y;
    printf("Welche number x: ");
    scanf_s("%d", &x);

    while (x < 0) {
        if (x <= -10) {
            y = -3 * x / 7 + 10;
            printf("y = -3x/7 + 10 = %d\n", y);
            break;
        } else {
            printf("kein antwort\n");
            break;
        }
    }

    while (x >= 0) {
        if (x < 7) {
            y = -6 * x * x + 8;
            printf("y = -6x^2 + 8 = %d\n", y);
            break;
        } else if (x >= 7) {
            if (x < 11) {
                printf("kein antwort\n");
                break;
            } else {
                y = -3 * x / 7 + 10;
                printf("y = -3x/7 + 10 = %d\n", y);
                break;
            }
        }
    }
    return 0;
}
```
