数学解法（斐波那契数列）
台阶问题实际上就是斐波那契数列的变种，可以使用矩阵快速幂或通项公式进一步提高效率：

python
import math
 
def climb_stairs_math(n):
    sqrt5 = math  sqrt(5)
    phi = (1 + sqrt5) / 2
    psi = (1 - sqrt5) / 2
    return int((phi ** (n + 1) - psi ** (n + 1)) / sqrt5)
 
# 测试
print(climb_stairs_math(5))  # 输出: 8
时间复杂度：O(log n)（使用快速幂算法）
