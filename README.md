# Practical-task-9
#include <stdio.h>

int calculateSteps(int x, int y) {
    // Перевірте, чи знаходяться x та y в допустимому діапазоні
    if (x < 0 || y < 0 || x > y || y >= 2147483648) {
        printf ("Неправильне введення. x та y повинні задовольняти умовам 0 <= x <= y < 2^31.\n");
        return -1;
    }
    
    // Ініціалізація змінних
    int steps = 0;
    int current = x;
    
    // Розрахувати мінімальну кількість кроків
    while (current < y) {
        if (current + 2 <= y) {
            current += 2;
        } else {
            current += 1;
        }
        steps++;
    }
    
    return steps;
}

int main() {
    
    int x, y;
    
    x = 45;
    y = 48;
    printf("Мінімальні кроки від %d до %d: %d\n", x, y, calculateSteps(x, y));
    
    x = 45;
    y = 49;
    printf("Мінімальні кроки від %d до %d: %d\n", x, y, calculateSteps(x, y));
    
    x = 45;
    y = 50;
    printf("Мінімальні кроки від %d до %d: %d\n", x, y, calculateSteps(x, y));
    
    x = 45;
    y = 51;
    printf("Мінімальні кроки від %d до %d: %d\n", x, y, calculateSteps(x, y));
    
    return 0;
}
