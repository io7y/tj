# 测试
print(climb_stairs_dp(5))      # 输出: 8
print(climb_stairs_optimized(5)) # 输出: 8
时间复杂度：O(n)
空间复杂度：普通版O(n)，优化版O(1)

Java实现
java
public class ClimbStairs {
    // 动态规划解法
    public static int climbStairsDP(int n) {
        if (n == 1) return 1;
        int[] dp = new int[n + 1];
        dp[1] = 1;
        dp[2] = 2;
        for (int i = 3; i <= n; i++) {
            dp[i] = dp[i - 1] + dp[i - 2];
        }
        return dp[n];
    }
    
    // 优化空间复杂度版本
    public static int climbStairsOptimized(int n) {
        if (n == 1) return 1;
        int a = 1, b = 2;
        for (int i = 3; i <= n; i++) {
            int temp = b;
            b = a + b;
            a = temp;
        }
        return b;
    }
