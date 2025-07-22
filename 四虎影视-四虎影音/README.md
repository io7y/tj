int main() {
    cout << climbStairsDP(5) << endl;      // 输出: 8
    cout << climbStairsOptimized(5) << endl; // 输出: 8
    return 0;
}
JavaScript实现
javascript
// 动态规划解法
function climbStairsDP(n) {
    if (n === 1) return 1;
    const dp = new Array(n + 1)  fill(0);
    dp[1] = 1;
    dp[2] = 2;
    for (let i = 3; i <= n; i++) {
        dp[i] = dp[i - 1] + dp[i - 2];
    }
    return dp[n];
}
 
// 优化空间复杂度版本
function climbStairsOptimized(n) {
    if (n === 1) return 1;
    let a = 1, b = 2;
    for (let i = 3; i <= n; i++) {
        [a, b] = [b, a + b];
    }
    return b;
}
 
// 测试
console  log(climbStairsDP(5));      // 输出: 8
console  log(climbStairsOptimized(5)); // 输出: 8
