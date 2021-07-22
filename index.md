## 浪漫相遇
你变成我，走过我走过的路。
我变成你，走过你走过的路。
然后我们便相遇了...
我宣布，这道题被评为今年最感动的题。
## 题目
输入两个链表，找出它们的第一个公共节点。

如下面的两个链表：

![在这里插入图片描述](https://img-blog.csdnimg.cn/img_convert/7a9b33214d39a8d18c0735293570afa2.png)啊飒


在节点 c1 开始相交。

 

## 思路

我们使用两个指针 node1，node2 分别指向两个链表 headA，headB 的头结点，然后同时分别逐结点遍历，当 node1 到达链表 headA 的末尾时，重新定位到链表 headB 的头结点；当 node2 到达链表 headB 的末尾时，重新定位到链表 headA 的头结点。

这样，当它们相遇时，所指向的结点就是第一个公共结点。




![在这里插入图片描述](https://img-blog.csdnimg.cn/img_convert/20d59e16a1f912260a8786bd8e258ef7.png)

## 代码

```java
public class Solution {
    public ListNode getIntersectionNode(ListNode headA, ListNode headB) {
        ListNode l1=headA;
        ListNode l2=headB;
         if(headA == null || headB == null) return null;
        while(l1!=l2){
             
            l1=l1.next;
            l2=l2.next;
            if (l1==null&&l2==null){
                    return  null;
                }
            if(l1==null){
                l1=headB;
            }
            if(l2==null){
                l2=headA;
            }
            
        }
        return l1;
    }
}
```
如果两个指针走完两个链表，也没有相交，就返回null
```java
 if (l1==null&&l2==null){
                    return  null;
                }
```

