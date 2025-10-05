```c
#include <stdio.h>
#include <math.h>

int main() {
    int n;
    double P = 1.0;
    long long count = 0;

    //double a, b;

    printf("Welch Zahl n: ");
    scanf_s("%d", &n);

    for (int i = 1; i <= n; i++) {
        double sum = 0.0;

        //числитель
        for (int j = 1; j <= i; j++) {
            double sinJ = sin(j);
            //printf("sinJ = -3x/7 + 10 = %d\n", sinJ);
            count++; // sin(j)

            double term = j + sinJ;
            count++; // j + sin(j)

            sum = sum + term;
            count++; // sum + term
        }

        // знаменатель
        double I2 = i * i;
        count++; // i * i

        double I3 = I2 + 1.0;
        count++; // +1

        // деление на знаменатель
        double ant = sum / I2;
        count++;

        P = P * ant;
        count++;
    }

    printf("\nAntwort:\n");
    printf("P = %.7f\n", P);
    printf("Count: %lld\n", count);

    return 0;
}
```
