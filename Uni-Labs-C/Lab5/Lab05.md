```c
#include <stdio.h>
#define ROW 10
#define COL 10

int Arr[ROW][COL] = {
   { 55, 34, 18, 92, 12, 67, 39, 78, 41, 23},
   { 88,  7, 95, 29, 51, 62,  4, 16, 80, 71},
   { 25, 47,  2, 60, 19, 99, 36, 83, 11, 58},
   { 76, 31, 10, 53, 86,  1, 93, 49, 21, 65},
   {  9, 74, 45, 27, 68, 89, 32,  5, 97, 14},
   { 59, 90, 20, 73, 44, 15, 85, 38, 64,  3},
   { 17, 50, 81, 22, 66, 96, 48, 79, 13, 54},
   { 42, 63, 35, 75,  6, 57, 98, 28, 87, 40},
   { 72, 100, 56, 33, 91, 24, 69, 46, 84, 30},
   { 43, 82, 61,  8, 77, 52, 26, 70, 94, 37}
};

int IdxCOL = 0;

int Val(int k) {
   return Arr[k][IdxCOL];
}

void Swap(int k1, int k2) {
   int temp = Arr[k1][IdxCOL];
   Arr[k1][IdxCOL] = Arr[k2][IdxCOL];
   Arr[k2][IdxCOL] = temp;
}

void Sort(int left, int right) {
   if (left >= right) {
       return;
   }

   int mid = left + (right - left) / 2;
   int p = Val(mid);
   int i = left;
   int j = right;

   while (i <= j) {
       while (Val(i) > p) {
           i++;
       }
       while (Val(j) < p) {
           j--;
       }
       if (i <= j) {
           Swap(i, j);
           i++;
           j--;
       }
   }
   if (left < j) {
       Sort(left, j);
   }
   if (i < right) {
       Sort(i, right);
   }
}
void SortCOL() {
   for (int j = 0; j < COL; j++) {
       IdxCOL = j;
       Sort(0, ROW - 1);
   }
}

int main() {
   printf("Matrix:\n");
   for (int i = 0; i < ROW; i++) {
       for (int j = 0; j < COL; j++) {
           printf("%3d ", Arr[i][j]);
       }
       printf("\n");
   }

   SortCOL();
   printf("\nNeue Matrix:\n");
   for (int i = 0; i < ROW; i++) {
       for (int j = 0; j < COL; j++) {
           printf("%3d ", Arr[i][j]);
       }
       printf("\n");
   }
   return 0;
}
```
