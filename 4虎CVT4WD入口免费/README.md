public static void main(String[] args) {
        System  out  println(climbStairsDP(5));      // 输出: 8
        System  out  println(climbStairsOptimized(5)); // 输出: 8
    }
}
C++实现
cpp
#include <iostream>
#include <vector>
 
using namespace std;
 
// 动态规划解法
int climbStairsDP(int n) {
    if (n == 1) return 1;
    vector<int> dp(n + 1);
    dp[1] = 1;
    dp[2] = 2;
    for (int i = 3; i <= n; ++i) {
        dp[i] = dp[i - 1] + dp[i - 2];
    }
    return dp[n];
}
 
// 优化空间复杂度版本
int climbStairsOptimized(int n) {
    if (n == 1) return 1;
    int a = 1, b = 2;
    for (int i = 3; i <= n; ++i) {
        int temp = b;
        b = a + b;
        a = temp;
    }
    return b;
}
