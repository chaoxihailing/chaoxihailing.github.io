### Algorithm

    爬楼梯
    1. 暴力求解
    class Solution{
        public int climbStairs(int n){
            climb_Stairs(0, n);
        }

        public int climb_Stairs(int i, int n){
            if(i > n){
                return 0;
            }

            if(i == n){
                return 1;
            }

            return climb_Stair(i + 1, n) + climb_Stairs(i+2 ,n);
        }
    }

    2. 递归
    ```Java
        class Solution{
            public int climbStairs(int n){
                int memo[] = new int[n +1];
                return climb_Stairs(0, n, memo);
            }

            public int climb_Stairs(int i, int n, int memo[]){
                ifi(i > 0){
                    return 0;
                }

                if(i == n){
                    return 1;
                }

                if(memo[i] > 0 ){
                    return memo[i];
                }

                memo[i] = climb_Stairs(i+1, n, memo) + climb_Stairs(i + 2, n, memo);

                return memo[1];
            }
        }
    ```

    3. 动态规划
    ```java
        class Solution{
            public int climbStairs(int n){
                if(n == 1){
                    return 1;
                }

                int[] dp = new int[n + 1];
                dp[1] = 1;
                dp[2] = 2;

                for(int i = 3; i <= n; i++){
                    dp[i] = dp[i-1] + dp[i -2];
                }
                return dp[n];
            }
        }
    ```
### Review
[code Review](https://medium.com/palantir/code-review-best-practices-19e02780015f)

这篇文章讲述了code review如何实施，其分为四个大步骤来讲述
1. 为什么要做，code review 是什么，以及如何去做code review
2. 做code Review的前期准备
3. code Review
4. code review例子

为什么要做code review, CR可以提高代码的阅读性，在功能上可以减少bug的产生，可以在开发人员共享知识，可以维护同一的编码共识.
当代码要合并到master分支的时候，就可以要Review
什么是code Review，就是当你在提交代码的时候，要找你的上级或者是同事来一起检查你的代码是否规范，有没有需要改进的地方，或者有明显的问题
要维持code Review，就必须要有时刻重构代码的习惯

code Review的要点
代码是否反应了作者的意图，如果Reviewer觉得不明白的地方，应该向代码提交者提问

1. 代码的解决问题的意图是否达到,代码是否足够简洁
2. 是否可以抽取公用的方法
3. 是否有第三方的类库可以使用
4. 代码是否遵循团队编码标准
5. 是否会依赖外部系统，是否可以会影响不同系统的关系
6. 是否有文档提供

要严肃地对待code Review，注意提问题的语气，使用建议性的提议

### Tip
teamViewer 可以让你远程连接电脑
在练习算法的时候，如果是初步入门，没有解题的思路的话，就把代码背下，
算法七分靠练，三分靠背

### Share
极客时间 Java并发编程实战讲的挺好，推荐
