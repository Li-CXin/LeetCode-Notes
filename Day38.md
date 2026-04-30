### Day38 动态规划06

## 322. Coin Change(零钱兑换)
> **Tags**: [`动态规划`](/search?q=动态规划)
题目中说每种硬币的数量是无限的，可以看出是典型的完全背包问题。凑足总额为j - coins[i]的最少个数为dp[j - coins[i]]，那么只需要加上一个钱币coins[i]即dp[j - coins[i]] + 1就是dp[j]（考虑coins[i]），所以dp[j] 要取所有 dp[j - coins[i]] + 1 中最小的。递推公式：dp[j] = min(dp[j - coins[i]] + 1, dp[j]);首先凑足总金额为0所需钱币的个数一定是0，那么dp[0] = 0; 其他下标对应的数值呢？考虑到递推公式的特性，dp[j]必须初始化为一个最大的数，否则就会在min(dp[j - coins[i]] + 1, dp[j])比较的过程中被初始值覆盖。所以下标非0的元素都是应该是最大值。

## 279. Perfect Squares(完全平方数)
> **Tags**: [`动态规划`](/search?q=动态规划)
本题和322. 零钱兑换 (opens new window)是一样的思路，dp[j] 可以由dp[j - i * i]推出， dp[j - i * i] + 1 便可以凑成dp[j]。此时我们要选择最小的dp[j]，所以递推公式：dp[j] = min(dp[j - i * i] + 1, dp[j]);

## 139. Word Break(单词拆分)
> **Tags**: [`动态规划`](/search?q=动态规划)
单词就是物品，字符串s就是背包，单词能否组成字符串s，就是问物品能不能把背包装满。拆分时可以重复使用字典中的单词，说明就是一个完全背包。dp[i] : 字符串长度为i的话，dp[i]为true，表示可以拆分为一个或多个在字典中出现的单词。如果确定dp[j] 是true，且 [j, i] 这个区间的子串出现在字典里，那么dp[i]一定是true。（j < i ）。所以递推公式是 if([j, i] 这个区间的子串出现在字典里 && dp[j]是true) 那么 dp[i] = true。在遍历顺序方面，本题其实我们求的是排列数，为什么呢。 拿 s = "applepenapple", wordDict = ["apple", "pen"] 举例。"apple", "pen" 是物品，那么我们要求 物品的组合一定是 "apple" + "pen" + "apple" 才能组成 "applepenapple"。"apple" + "apple" + "pen" 或者 "pen" + "apple" + "apple" 是不可以的，那么我们就是强调物品之间顺序。所以说，本题一定是 先遍历 背包，再遍历物品。
