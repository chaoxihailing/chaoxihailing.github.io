### Algorithm
[swap two](https://leetcode.com/problems/swap-nodes-in-pairs/submissions/)

解题思路：
	在这里我们需要三个条件，current， current.next, current.next.next 来完成一次两两交换
	数据的交换需要额外空间，所以我们创建一个`prev`,并把它的next指向head.

	由于是两两交换，所以要判定 current.next.next，current.next 不能为空，
	最关键的一步是 fist.next = second.next;
	第一个两两交换后，我们需要把指针移动已经交换好的最后一个node
	
``` java 
public ListNode swapPairs(ListNode head) {
        ListNode prev = new ListNode(0);
        prev.next = head;
        ListNode current = prev;
        while(current.next != null && current.next.next != null){
            ListNode first = current.next;
            ListNode second = current.next.next;
            
            first.next = second.next;
            current.next = second;
            current.next.next = first;
            current = current.next.next;
        }
        
        return prev.next;
    }
```

### Review  
[Microservices](https://martinfowler.com/articles/microservices.html)  

皓叔的专栏，给了很多有用的英文技术资料，我打算Review这些英文技术知识，顺便对知识体系做一些梳理

1. 为什么要有微服务
因为单体计算机的存在性能瓶颈，不能很好的进行扩展，同时没办法面对海量的数据，所以需要多台应用做成分布式，来满足业务的需求，但是在实施分布式的时候，整个单体应用过于复杂，不便于开发。于是出现了SOA的思想，面对接口进行数据的交互的系统设计，将单体应用拆分为多个微小的子服务，每个服务都有自己的数据库，服务与服务之间不通过共享数据库来进行数据的交互，而是通过服务的接口进行调用。 

2. 实现微服务需要那些要求
对业务逻辑有深刻的理解，能够区分微服务的边界,数据的交换通过接口来进行
要有自动化部署工具，因为微服务一般会有几百或者上万个实例，如果通过人工去管理，是一种不靠谱的方法
微服务的依赖需要有自动切换，不能出现单点依赖，然后这个单点失效后，整个系统全部不能工作了

### Tip  
如果在Linux或者是mac平台上开发的话，shell一定需要安装oh-my-shell,他会记录命令的历史，并自动提示功能
tmux，也是一个必须的掌握的技能，他可以让你不需要打开多个terminal窗口


### Share  

[站在未来的十字路口](http://www.ruanyifeng.com/blog/2019/01/survivor-preface.html)  
随着计算更加的智能化，对人类的社会带来的巨大的影响，会有很多职业消失，会有有很多人失业。但是我个人觉得大势不可避免，那么我们应该都需要有一技之长，主动学习，更好地面对未来。
