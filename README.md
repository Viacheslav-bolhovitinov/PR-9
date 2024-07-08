#include <stdio.h>

int min_steps(int x, int y) {
    int dx = y - x;
    int steps = 0;
    int step_size = 1;

    while (dx > 0) {
        if (dx >= step_size * 2 - 1) {
            dx -= step_size * 2 - 1;
            steps += 2;
            step_size++;
        } else {
            dx -= step_size;
            steps++;
        }
    }

    return steps;
}

int main() {
    int x, y;
    printf("Enter x and y (0 <= x <= y < 2^31): ");
    scanf("%d %d", &x, &y);

    int min_steps_count = min_steps(x, y);
    printf("Minimum steps: %d\n", min_steps_count);

    return 0;
}
