### Day43 动态规划10

## 300. Longest Increasing Subsequence（最长递增子序列）
> **Tags**: [`动态规划`](/search?q=动态规划)
dp[i]表示i之前包括i的以nums[i]结尾的最长递增子序列的长度，位置i的最长升序子序列等于j从0到i-1各个位置的最长升序子序列 + 1 的最大值。所以：if (nums[i] > nums[j]) dp[i] = max(dp[i], dp[j] + 1)；注意这里不是要dp[i] 与 dp[j] + 1进行比较，而是我们要取dp[j] + 1的最大值。每一个i，对应的dp[i]（即最长递增子序列）起始大小至少都是1.

## 674. Longest Continuous Increasing Subsequence（最长连续递增序列）
> **Tags**: [`动态规划`](/search?q=动态规划)
本题相对于300.最长递增子序列 (opens new window)最大的区别在于“连续”。因此只需要更改j的遍历为i-1即可ac。

## 718. Maximum Length of Repeated Subarray（最长重复子数组）
> **Tags**: [`动态规划`](/search?q=动态规划)
要想到 用二维数组可以记录两个字符串的所有比较情况，这样就比较好推 递推公式了。dp[i][j] ：以下标i - 1为结尾的A，和以下标j - 1为结尾的B，最长重复子数组长度为dp[i][j]。据dp[i][j]的定义，dp[i][j]的状态只能由dp[i - 1][j - 1]推导出来。即当A[i - 1] 和B[j - 1]相等的时候，dp[i][j] = dp[i - 1][j - 1] + 1;
