### Algorithm
    题目： 验证二叉搜索树

    解法1：
        思路：因为是二叉搜索树，所以左子树是小于根，根小于右子树。
        ```
        class solution{
            public boolean isValiaBST(TreeNode root) {
                if(root == null){
                     return true;
                }
                return valid(root, Long.MIN_VALUE, Long.MAX_VALUE);
            }
        
            public valid(TreeNode root, long low, long high){
                 if(root == null) return true;
                 if(root.val <= low || root.val >= high) return false;

                 return valid(root.left, low, root.val) && valid(root.right, root.val, hight);
            }
        }
        ```
    解法2：直接中序遍历，然后将所有遍历的节点保存的一个数组你，再判断这个数组是不是有序的
    ```java
    
    class sulution{
        public booblean isValidBST(){
        
             public List<Integer> list = new ArrayList<Integer>();
                 inOrder(root, list);
                 for(int i=0; i<list.size() -1 ; i++){
                     if(list.get(i) >= list.get(i+1) return false;
                 }

                 return true;
        }
         
         public void inOrder(TreeNode node, ListNode<Integer> list){
              if(node == null) return;
              inOrder(node.left,list);
              list.add(node.val);
              inOrder(node.right,list);
         }
    }
    ```

    解法3：
        思路：递归去遍历
        ```java
        class sulution{
            public boolean isValidBST(TreeNode root){
                Stack<TreeNode> stack  = new Stack<TreeNode>();

                double inorder = - Double.MAX_VALUE;

                while(!stack.isEmpty() || root !=null ){
                        while(root != null){
                            stack.push(root)；
                        root = root.left;
                    }
                    root = stack.pop();

                    if(root.val <= inorder) return false;
                    inorder = root.val;
                    root = root.right;
                }
                
                 return true;
                }
        }
         ```
### Review
> Effective Java 3rd
1. Consider static factory methods instead of constructors
使用 静态工厂方法来代替 构造器

好处：
1. 静态工厂方法有名字
2. 静态工厂方法不像构造方法，不需要每次调用的时候构造一个新的对象
3. 静态工厂方法可以返回多个不同的类型，而构造器只能返回类type
4. 静态工厂方法可以接受函数作为参数
5. 在使用包含方法的类时，返回对象所属的类不必事先存在

缺点：
1. 仅提供静态工厂方法的主要限制是，没要公有或者受保护的构造方法的类是无法被子类实例化。
2. 程序员比较难找到它们，它们在API文档中不像构造函数那样清晰。

常见的静态方法命名：
* from 
* of
* valueOf
* instance or getInstance
* create or newInstance
* getType
* newType
* type

    总结⼀一下，静态⼯厂方法与公有的构造方法都有各自的适用场景，我们需要理解他们各自的优点。通常，静态⼯厂是优先选择的，这样可以避免习惯性地在没有考虑静态⼯厂的情况下就提供公有构造⽅方法的情况发⽣生。

### Tip
vim 命令行模式 可以让你不用鼠标就可以移动代码， `:5,20m.`, 移动5,到20行的代码到当前光标下
多列缩进， `v,j,>>`。


### Share
wireshark 抓包，通过抓包分析可以直观的查看到TCP,UDP协议。推荐《wireshark网络分析的艺术》
