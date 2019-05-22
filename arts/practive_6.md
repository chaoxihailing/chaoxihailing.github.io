### Algorithm

N皇后问题
    思路：解法1： DFS, 深度递归，每走一步都需要，重新查看这个棋盘，这个皇后是否符合,如果不符合的话，就回复这一步，如果符合的话，就继续递归查看下一步是不符合。
    解法2：DFS的基础上加一个缓存
    ```java
    public List<String[]> solveNQueens(int n){
       List<Sting[]> res = new ArrayList<>();
       helper(0, new boolean[n], new boolean[2*n], new boolean[2*n], new String[n], res);
       return res;
    }


    private void helper(int r, boolean[] cols, boolean[] d1, boolean[] d2, String[] board, List<String[]> res) {
       if (r == board.length) res.add(board.clone());
       else { 
           for (int c = 0; c < board.length; c++) { 
             int id1 = r -c +board.length, id2 = 2*board.length -r -c -1;
             if(!cols[c] && !d1[id1] && !d2[id2]) { 
                char[] row = new char[board.length];
                Arrays.fill(row, '.'); row[c] = 'Q';
                board[r] = new String(row);
                cols[c] = true; d1[id1] = true, d2[id2] = true;
                help(r+1, cols, d1, d2, board, res);
                cols[c] = false; d1[id1] = false; d2[id2] = false;
             }
           }
       }
    }

    ```
### Review
(介绍了分布式的方方面面)[http://www.aosabook.org/en/distsys.html]

### Tip
微信有网页版，学习一定要有个详细的地图，地图的节点代表着3个w,what,why,how.

mq 消息队列的使用，在只有一个的时候，要做到幂等性。
### Share
[分布式系统架构](https://time.geekbang.org/column/article/2080)
