## 👾 используются вложенные циклы 
```c
#include <stdio.h>
#include <math.h>
int main() {
    int n;
    double P = 1.0;
    int ops = 0;

    printf("Welch Zahl n: ");
    scanf_s("%d", &n);

    for (int i = 1; i <= n; i++) {
        double sumJ = 0;

        for (int j = 1; j <= i; j++) {
            double SIN = sin(j);
            double plus = j + SIN;
            sumJ += plus;
            ops += 3;
        }

        double k = i * i;
        double zahl = k + 1;
        ops += 2;

        double term = sumJ / zahl;
        ops ++;

        P *= term;
        ops ++;
    }

    printf("P = %.7f\n", P);
    printf("ops: %d\n", ops);

    return 0;
}
```
