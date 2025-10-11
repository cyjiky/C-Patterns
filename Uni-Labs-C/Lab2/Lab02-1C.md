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

✔️ проверка (вывод после каждой операции)

```c
#include <stdio.h>
#include <math.h>
int main() {
    double P = 1.0;
    int ops = 0;

    int n;
    printf("Welch Zahl n: ");
    scanf_s("%d", &n);

    for (int i = 1; i <= n; i++) {
        double sumJ = 0;

        for (int j = 1; j <= i; j++) {
            double SIN = sin(j);
            printf("sin(j) = %.7f\n", SIN);
            double plus = j + SIN;
            printf("j + sin(j)= %.7f\n", plus);
            sumJ += plus;
            printf("sumJ += j + sin(j) = %.7f\n: ", sumJ);
            printf("---------------------");
            ops += 3;
        }

        double k = 0;
        double zahl = 0;
        k = i * i;
        printf("i * i = %.7f\n", k);
        zahl = k + 1;
        printf("k + 1 = %.7f\n", zahl);
        ops += 2;

        double term = sumJ / zahl;
        ops ++;
        printf("term = %.7f\n", term);

        P *= term;
        ops ++;
        printf("P (after i = %d) = %.7f\n", i, P);
    }

    printf("P = %.7f\n", P);
    printf("ops: %d\n", ops);

    return 0;
}
```

