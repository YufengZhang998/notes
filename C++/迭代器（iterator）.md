<!--
 * @Description : 
 * @Author      : Yufeng Zhang
 * @Date: 2023-10-30 20:41:31
 * @LastEditTime: 2023-10-30 20:43:24
-->
# iterator说明
迭代器（iterator）是一种检查容器内元素并遍历元素的数据类型   
遍历（vector、deque、list、set、map）等数据结构

# 例程
```
//将vector的元素值全部修改为2
vector<int> v(10,1);
for(vector<int>::iterator it = v.begin();it!=v.end();++it)
*it = 2;
```