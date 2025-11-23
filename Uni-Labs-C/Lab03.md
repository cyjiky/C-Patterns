```c
#include <stdio.h>
#include <stdbool.h>
#include <unistd.h>
#define ROW 23
#define COL 80
typedef struct {
	int x;
	int y;
} Point;
bool MoveDown(int y) {
	return (y < ROW);
}
bool MoveUp(int y) {
	return (y >= 0);
}
int main() {
	char matrix[ROW][COL];
	int fill_count = 1;
	for (int j = 0; j < COL; j++) {
		if (j % 2 == 0) {
			for (int i = 0; i < ROW; i++) {
				matrix[i][j] = '#';
			}
		} else {
			for (int i = ROW - 1; i >= 0; i--) {
				matrix[i][j] = '#';
			}
		}
	}
	printf("Matrix (%dx%d).\n", ROW, COL);
	int startX = (COL - 1) / 2;
	Point p1;
	Point p2;
	p1.y = startX;
	p1.x = ROW - 1;;
	p2.y = startX + 1;
	p2.x = 0;
	while (p1.y >= 0 && p2.y < COL) {
		while (MoveDown(p2.x) && MoveUp(p1.x)) {
			usleep(10000);
			printf("\033[%d;%dH%c", p1.x+1, p1.y+1, matrix[p1.x][p1.y]);
			printf("\033[%d;%dH%c", p2.x+1, p2.y+1, matrix[p2.x][p2.y]);
			p1.x--;
			p2.x++;
		}
		p1.x += 1;
		p2.x -= 1;
		p1.y--;
		p2.y++;
		while (MoveDown(p1.x) && MoveUp(p2.x)) {
			usleep(10000);
			printf("\033[%d;%dH%c", p1.x+1, p1.y+1, matrix[p1.x][p1.y]);
			printf("\033[%d;%dH%c", p2.x+1, p2.y+1, matrix[p2.x][p2.y]);
			p1.x++;
			p2.x--;
		}
		p1.x -= 1;
		p2.x += 1;
		p1.y--;
		p2.y++;
	}
	return 0;
}
```
