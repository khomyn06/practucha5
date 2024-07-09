Практична робота #5 Хомин Михайло
#include <stdio.h>

#define MOD 12345

int main() {
    int n;
    scanf("%d", &n);

    if (n == 1) {
        printf("2\n");
        return 0;
    }

    int dp0 = 1, dp1 = 1, dp2 = 0;
    int new_dp0, new_dp1, new_dp2;

    for (int i = 2; i <= n; i++) {
        new_dp0 = (dp0 + dp1 + dp2) % MOD;
        new_dp1 = dp0 % MOD;
        new_dp2 = dp1 % MOD;

        dp0 = new_dp0;
        dp1 = new_dp1;
        dp2 = new_dp2;
    }

    int result = (dp0 + dp1 + dp2) % MOD;
    printf("%d\n", result);

    return 0;
}
