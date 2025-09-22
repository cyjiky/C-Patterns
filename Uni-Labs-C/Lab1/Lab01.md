# с булевыми операторами 

```c
#define _CRT_SECURE_NO_WARNINGS 
#include <stdio.h> //библиотека С

int main() {
    int x, y;

    printf("Welche number x: "); //выводит на консоль запрос пользователю 
    scanf_s("%ld", &x);("%ld", &x); //принимает значение от пользователя 

    //цикл if-else
    if (x >= 0 && x < 7) { //and 
        y = -6 * x * x + 8;
        printf("y = -6x^2 + 8 = %.2ld\n", y);
    } 
    else if ((x <= -10) || (x >= 11)) { //or
        y = -3 * x / 7 + 10; // целочисленное деление
        printf("y = -3x/7 + 10 = %.2ld\n", y);
    } 
    else {
        printf("kein antwort\n");
    }
    return 0; //возвращает 0
}
```
