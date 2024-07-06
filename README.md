# C-Practice-2

#include <stdio.h>

int gcd(int a, int b) {
    if (b == 0)
        return a;
    else
        return gcd(b, a % b);
}

int lcm(int a, int b) {
    return a * b / gcd(a, b);
}

int main() {
    int n, i;
    scanf("%d", &n);

    int numbers[n];
    for (i = 0; i < n; i++) {
        scanf("%d", &numbers[i]);
    }

    int lcm_result = numbers[0];
    for (i = 1; i < n; i++) {
        lcm_result = lcm(lcm_result, numbers[i]);
    }

    printf("%d\n", lcm_result);

    return 0;
}
