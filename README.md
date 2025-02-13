#include <stdio.h>

#define MOD 12345

int main() {
    int n;
    scanf("%d", &n);

    if (n < 1 || n >= 10000) {
        return 1;
    }

    long long a[10001] = {0}, b[10001] = {0}, c[10001] = {0};

    a[1] = 1;  
    b[1] = 1; 
    c[1] = 0; 

    for (int i = 2; i <= n; i++) {
        a[i] = (a[i-1] + b[i-1] + c[i-1]) % MOD;
        b[i] = a[i-1] % MOD;
        c[i] = b[i-1] % MOD;
    }
    long long result = (a[n] + b[n] + c[n]) % MOD;

    printf("%lld\n", result);

    return 0;
}
