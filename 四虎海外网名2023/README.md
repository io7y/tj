def climb_stairs_recursive(n):
    if n == 1:
        return 1
    if n == 2:
        return 2
    return climb_stairs_recursive(n-1) + climb_stairs_recursive(n-2)
 
# 测试
print(climb_stairs_recursive(5))  # 输出: 8
时间复杂度：O(2^n)（指数级，效率低）

动态规划解法（高效）
python
def climb_stairs_dp(n):
    if n == 1:
        return 1
    dp = [0] * (n + 1)
    dp[1] = 1
    dp[2] = 2
    for i in range(3, n + 1):
        dp[i] = dp[i-1] + dp[i-2]
    return dp[n]
 
# 优化空间复杂度版本
def climb_stairs_optimized(n):
    if n == 1:
        return 1
    a, b = 1, 2
    for _ in range(3, n + 1):
        a, b = b, a + b
    return b
