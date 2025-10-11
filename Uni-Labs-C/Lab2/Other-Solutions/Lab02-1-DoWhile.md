## ✔️ решение с использованием "Do-While"
```c
#include <stdio.h>
#include <math.h>
int main() {
    int n;
    double P = 1.0;
    int ops = 0;

    printf("Welch Zahl n: ");
    scanf_s("%d", &n);

    int i = 1;

    do {
        double sumJ = 0;
        int j = 1;

        do {
            double SIN = sin(j);
            double plus = j + SIN;
            sumJ += plus;
            ops += 3;
            j++;
        }
        while (j <= i);

        double k = i * i;
        double zahl = k + 1;
        ops += 2;

        double term = sumJ / zahl;
        ops ++;

        P *= term;
        ops ++;
        i ++;
    }
    while (i <= n);

    printf("P = %.7f\n", P);
    printf("ops: %d\n", ops);

    return 0;
}
```
