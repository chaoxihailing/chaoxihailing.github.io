###  Algorithm
    1. 用栈实现队列
    思路： 栈是先入先出，而栈是后入先出的。为了实现队列，需要两个栈（inputStack， outPutStack）去维护数据进入的顺序，并将inputStack的顺序一次取出，放到outputStack，那么outputStack出站的顺序就变为了队列的先入先出。
    ```java
    public Soluction{
        Stack<Integer> inputStack = new Stack<>();
        Stack<Integer> outputStack = new Stack<>();

        public Solution(){

        }

        public void put(int x){
            inputStack.push(x);
        }

        public boolean empty(){
            return inputStack.empty() && outputStack.empty();
        }

        public int peek(){
            if(outputStack.empty()){
                while(!inputStack.empty()){
                    outputStack.push(inputStack.pop());
                }
            }
            return outputStack.peek();
        }


        public int pop(){
            peek();
            return outputStack.pop();
        }
    }
    
    ```

    2. 用队列实现栈
    思路：栈是后入先出，队列是先入先出。栈可以看成是队列是个一个贪吃蛇版本。将队列的数据循环移除，添加。直到最后一个输入的数据为队列的第一位。
    ```java
    public Soluction{
        private LinkedList<Integer> queue = new LinkedList<Integer>();

        public int push(int x){
            queue.add(x);
            int count = queue.size();
            while(count > 1){
                queue.add(queue.remove());
                count--:
            }
            
        }

        public int peek(){
          return  queue.peek();
        }

        public int pop(){
             return queue.remove();
        }

        public boolean empty(){
             return queue.isEmpty();
        }
    }
    ```
### Review
[数据库性能优化](https://www.mysql.com/cn/why-mysql/presentations/tune-mysql-queries-performance/)
1. Cost-based query optimization in MySQL 基本的优化器的知识  
2. Tools for monitoring, analyzing, and tuning queries    监控工具，分析工具，查询工具  
3. Data access and index selection    数据执行时，索引的选择 和 数据扫描的方式  
4. join optimizer    join 优化  
5. Sbuqueries     子查询优化  
6. sorting    排序优化
7. Influencing the optimizer 影响optimizer的要素

### Tip
工具： xdm工具挺好用的，免费版的idm。
shell： 使用别名，可以快速的跳转的文件，alias download ="cd /path/download", 但是记得要持久化，否则重启后，alias会失效
mysql: show processlist 可以在线上查看数据库正在连接的数据，以及正在执行的语句
scp 方便在两个Linux服务器传输文件

### Share
[OAuth 2.0的一个简单解释](http://www.ruanyifeng.com/blog/2019/04/oauth_design.html)

简明的介绍了OAuth2



