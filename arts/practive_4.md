### Algorithm
   二叉树最大深度
   ```java
   class soluction{
       public int maxDepth(TreeNode root) {
           return (root == null) ? 0 : 1 + Math.max(maxDepth(root.left, root.right) );
       }
   }
   ```

   二叉树最小深度
    ```java
    class soluction {
        public int minDepth(TreeNode root) {  
            if(root == null) {  
                    return;
            }

            int left = minDepth(root.left);
            int right = minDepth(root.right);

            return (root.left == null || root.right == null) ? left + right + 1 : Math.min(left, right) + 1;
        }
    }
    ```
### Review
(程序员修养)[https://www.quora.com/What-are-some-of-the-most-basic-things-every-programmer-should-know]
1. 糟糕的架构会比糟糕的代码导致更多问题
2. 你会花更多时间去思考而不是编码
3. 获得更多薪水的最佳机会就是谈判前
4. 位置决定你的工作，而不是你的工作技能
5. 频繁提交代码
6. 在feature branch 工作
7. 学习vim或者emacs
8. 企业的目的是赚钱
9. 编码的目的是为了解决问题，而不是为了艺术
10. 你的老板认为你是可以替换的
11. 最好的程序员总是在构建东西
12. 工作的目的是为了获得报酬
13. 始终要知道你的工作的企业是如何赚钱，这决定了谁获得了报酬
14. 时刻考虑重构
15. 必须思考在程序有问题的情况下，如何处理
16. 使用版本管理
17. 使用成熟的第三方库
18. 单元测试，尤其在代码复杂的时候
19. 避免对新技术的过度狂热
20. linux知识是必须的

### Tip
安装软件的时候，要注意软件的版本和软件插件的版本是否一致
使用scp 传输文件
在学习东西的时候，记得看文档
vim对 列块操作 十分方便 `crtl-v`选中，`I`插入，然后`ESC`退出
### Share
(阮一峰 每周分享第 52 期)[http://www.ruanyifeng.com/blog/2019/04/weekly-issue-52.html]


