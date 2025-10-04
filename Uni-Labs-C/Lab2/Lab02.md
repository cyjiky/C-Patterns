## первая программа (Demo) 

```c
#include <stdio.h>
#include <math.h>

int main() {
    int R;
    printf("Welch Zahl n: ");
    scanf_s("%d", &R);

    double n = 1.0;

    for (int i = 1; i <= R; i++) {
        double Num = 0.0;
        double sum = 0.0;

        // Суммируем j + sin(j) от j = 1 до i
        for (int j = 1; j <= i; j++) {
            Num = j + sin(j);
            sum += Num;
            //sum += j + sin(j);
        }

        // Делим на i^2 + 1
        double I1 = i++;
        double I2 = i * I1; // (i * i + 1)
        double res = sum / I2;

        // Умножаем на общий результат
        n *= res;
    }

    printf("Antwort = %.7f\n", n); // n = 10 -> Antwort = 0.0814876
    return 0;
}
```
