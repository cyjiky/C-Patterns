```c
#include <stdio.h>
#define ROW 10
#define COL 10

int Arr[ROW][COL] = {
   {100, 99, 98, 97, 96, 95, 94, 93, 92, 91},
   { 90, 89, 88, 87, 86, 85, 84, 83, 82, 81},
   { 80, 79, 78, 77, 76, 75, 74, 73, 72, 71},
   { 70, 69, 68, 67, 66, 65, 64, 63, 62, 61},
   { 60, 59, 58, 57, 56, 55, 54, 53, 52, 51},
   { 50, 49, 48, 47, 46, 45, 44, 43, 42, 41},
   { 40, 39, 38, 37, 36, 35, 34, 33, 32, 31},
   { 30, 29, 28, 27, 26, 25, 24, 23, 22, 21},
   { 20, 19, 18, 17, 16, 15, 14, 13, 12, 11},
   { 10,  9,  8,  7,  6,  5,  4,  3,  2,  1}
};

int Row(int p) {
   int left = 0;
   int right = ROW - 1;
   int mid = 0;

   while (left <= right) {
       mid = left + (right - left) / 2;
       if (p > Arr[mid][0]) {
           right = mid - 1;
       } else if (p < Arr[mid][COL-1]) {
           left = mid + 1;
       } else {
           return mid;
       }
   }
   return -1;
}

int Col(int rowId, int p) {
   int left = 0;
   int right = COL - 1;
   int val = 0;
   int mid = 0;
   int result = -1;

   while (left <= right) {
       mid = left + (right - left) / 2;
       int value = Arr[rowId][mid];
       val++;

       if (value == p) {
           result = mid;
           right = mid - 1;
       }
       else if (value < p) {
           right = mid - 1;
       } else {
           left = mid + 1;
       }
   }
   if (result != -1) {
       printf("Antwort: [%d][%d]\n", rowId, result);
       return result;
   }
   return -1;
}

int main() {
   for (int i = 0; i < ROW; i++) {
       for (int j = 0; j < COL; j++) {
           printf("%3d ", Arr[i][j]);
       }
       printf("\n");
   }
   printf("\nSuchen [0, 5]:\n");

   for (int p = 0; p <= 5; p++) {
       int targetRow = Row(p);
       if (targetRow != -1) {
           if (Col(targetRow, p) != -1) {
               int found = 1;
           }
       }
   }
   return 0;
}
```
