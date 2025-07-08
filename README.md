#include <stdio.h>

#define MOD 12345

int main() {
    int n;
    printf("Введіть довжину послідовності n: ");
    scanf("%d", &n);

    if (n == 1) {
        printf("Кількість шуканих послідовностей: 2\n");
        return 0;
    }
    if (n == 2) {
        printf("Кількість шуканих послідовностей: 4\n");
        return 0;
    }

    int dp[10001];
    
    dp[1] = 2; 
    dp[2] = 4; 
    dp[3] = 7; 

    for (int i = 4; i <= n; i++) {
        dp[i] = (dp[i-1] + dp[i-2] + dp[i-3]) % MOD;
    }

    printf("Кількість шуканих послідовностей: %d\n", dp[n]);
    return 0;
}
