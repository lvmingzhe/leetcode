- [数组](#数组)
  - [数组拷贝](#数组拷贝)
  - [数组求和](#数组求和)
  - [判断一个数字是否存在](#判断一个数字是否存在)
  - [删除第一个元素](#删除第一个元素)
  - [返回最大值和最小值](#返回最大值和最小值)
  - [将两个Vector合并](#将两个vector合并)
  - [反向排序](#反向排序)
  - [从一个大数组中分出两个小数组](#从一个大数组中分出两个小数组)
  - [按照pair的第二个参数排序](#按照pair的第二个参数排序)
- [字符串](#字符串)
  - [插入字符串的insert函数](#插入字符串的insert函数)
  - [删除字符串末尾的字符](#删除字符串末尾的字符)
  - [空格char](#空格char)
  - [字符串<---->数字](#字符串----数字)
  - [反转字符串](#反转字符串)
  - [将所有字母变成小写字母](#将所有字母变成小写字母)
  - [判断是否是字母或者数字](#判断是否是字母或者数字)
- [链表](#链表)
  - [建立一个新number的链表节点](#建立一个新number的链表节点)
  - [往后遍历链表](#往后遍历链表)
  - [反转链表](#反转链表)
  - [建立一个新的链表模板](#建立一个新的链表模板)
- [堆和队列](#堆和队列)
  - [声明队列](#声明队列)
  - [关于堆（优先队列）的操作](#关于堆优先队列的操作)
  - [队列的常规操作](#队列的常规操作)
- [二分查找](#二分查找)
  - [边界问题](#边界问题)
- [二叉树](#二叉树)
  - [二叉树的前序遍历模板：](#二叉树的前序遍历模板)
  - [中序遍历](#中序遍历)
  - [后续遍历](#后续遍历)
  - [中序遍历模板](#中序遍历模板)
  - [层序遍历模板](#层序遍历模板)
  - [从有序数组恢复二叉搜索树](#从有序数组恢复二叉搜索树)
  - [树的高度](#树的高度)
  - [二叉树递归](#二叉树递归)
  - [二叉树搜索一条边](#二叉树搜索一条边)
  - [二叉树遍历整个树](#二叉树遍历整个树)
  - [二叉树用右边子树代替当前节点](#二叉树用右边子树代替当前节点)
- [哈希表](#哈希表)
  - [遍历unordered_map迭代器](#遍历unordered_map迭代器)

# 数组
## 数组拷贝
```cpp
std::copy(std::begin(a),std::end(a),std::begin(b));
```

## 数组求和
```cpp
int sum = accumulate(vec.begin() , vec.end() , 0);
// 0是累加的初值
```
## 判断一个数字是否存在
```cpp
int res=std::count(v.begin(),v.end(),queryNumber);
```

## 删除第一个元素
```cpp
tmp.erase(tmp.begin());
```

## 返回最大值和最小值
```cpp
return *max_element(a.begin(),a.end());
return *min_element(a.begin(),a.end());
```

## 将两个Vector合并
```cpp
vector<string>vec1,vec2,vec3;
//... vec1,vec2赋值
		vec3.insert(vec3.end(),vec1.begin(),vec1.end());
		vec3.insert(vec3.end(),vec2.begin(),vec2.end());
```

## 反向排序
```cpp
sort(nums.rbegin(), nums.rend());
```

## 从一个大数组中分出两个小数组
```cpp
vector<int> leftPart(nums.begin(),nums.begin()+idx);
vector<int> rightPart(nums.begin()+idx+1,nums.end());
```

## 按照pair的第二个参数排序
```cpp
bool static cmp (const pair<int, int>& a, const pair<int, int>& b) {
    return a.second > b.second; // 按照频率从大到小排序
}

vector<pair<int, int>> vec(map.begin(), map.end());
sort(vec.begin(), vec.end(), cmp); // 给频率排个序

```

# 字符串
## 插入字符串的insert函数
```cpp
string str="hello";
 string s="Hahah";
 str.insert(1,s);   //在原串下标为1的字符e前插入字符串s
 cout<<str<<endl;   // 结果:    hHahahello
 
 string str1="hello";
 charc='w';
 str1.insert(4,5,c);    //在原串下标为4的字符o前插入5个字符c
 cout<<str1<<endl;  // 结果：   hellwwwwwo
 
 string str2="hello";
 string s2="weakhaha";
 str2.insert(0,s2,1,3); //将字符串s2从下标为1的e开始数3个字符，分别是eak，插入原串的下标为0的字符h前
 cout<<str2<<endl;  //  结果：  eakhello
```

## 删除字符串末尾的字符
```cpp
    string str = "123456";
    //方法一：使用substr()
    str = str.substr(0, str.length() - 1);
    //方法二：使用erase()
    str.erase(str.end() - 1);
    //方法三：使用pop_back()
    str.pop_back();
```
## 空格char
```cpp
char c = '\0';
```

## 字符串<---->数字
```cpp
stoi(string) //将字符串转换为数字
to_string(int)  //将数字转换为字符串
```

## 反转字符串
```cpp
reverse(s.begin(),s.end()); 
```

## 将所有字母变成小写字母

tolower函数

## 判断是否是字母或者数字

isalnum函数，如果是则返回1

# 链表

## 建立一个新number的链表节点
```cpp
Node* cur = new Node(number);
```

## 往后遍历链表
```cpp
cur = cur->next;
```

## 反转链表

```cpp
ListNode* head；//（原链表）
ListNode* backward=nullptr, * forward;
while(head)
{
      forward = head->next;
      head->next = backward;
      backward = head;
      head = forward;
 }
//backward是反转之后的链表
```

## 建立一个新的链表模板
```cpp
//头节点
{
   head = new ListNode(node->val);
   pre = head;
 }
//后序节点
{
   cur = new ListNode(node->val);
   pre->next = cur;
   pre = pre->next;
}

```

# 堆和队列

## 声明队列
```cpp
queue<int> q;  //声明一个int类型的队列
priority_queue <int, vector<int>, greater<int> > q; 
//从小到大的优先队列（小顶堆）
priority_queue <int, vector<int>, less<int> > q; //从大到小
priority_queue <int> q; //大顶堆
```

## 关于堆（优先队列）的操作
```cpp
用priority_queue来建堆：
大根堆：priority_queue <int> heap
小根堆：priority_queue<int, vector<int>, greater<int>> heap
操作：heap.top() 返回堆顶值
heap.pop() 删除堆顶
heap.push(num) 加入一个元素进堆
heap.size()堆中元素个数
heap.empty()判断一个队列是否为空
```

## 队列的常规操作

```cpp
q.back()返回最后一个元素
q.front()返回第一个元素
q.pop()删除第一个元素
q.push()在末尾加入一个元素
q.size()返回队列中元素的个数
q.empty()如果队列空则返回真
```

# 二分查找
## 边界问题
边界还是有点迷，什么时候用i<=j,什么时候用i<j。

什么时候j=n-1,什么时候j=n

什么时候m+1,m-1，什么时候m

什么时候返回i,什么时候返回j

# 二叉树
## 二叉树的前序遍历模板：
```cpp
void traversal(TreeNode* cur,vector<int>& vec)
{
    if(cur==nullptr)return;
    vec.push_back(cur->val);
    traversal(cur->left,vec);
    traversal(cur->right,vec);
}
```

## 中序遍历
```cpp
void traversal(TreeNode* cur, vector<int>& vec) {
if (cur == NULL) return;
        traversal(cur->left, vec);  // 左
        vec.push_back(cur->val);    // 中
        traversal(cur->right, vec); // 右
   }
```

## 后续遍历
```cpp
void traversal(TreeNode* cur, vector<int>& vec) {
if (cur == NULL) return;
        traversal(cur->left, vec);  // 左
        traversal(cur->right, vec); // 右
        vec.push_back(cur->val);    // 中
    }
```

## 中序遍历模板
```cpp
// 二叉搜索树中序遍历模板：
void searchBST(TreeNode* cur) {
    if (cur == NULL) return ;
    searchBST(cur->left);       // 左
    （处理节点）                // 中
    searchBST(cur->right);      // 右
    return ;
}
```

## 层序遍历模板
```cpp
queue<TreeNode*> q;
if(root!=nullptr) q.push(root->val);
while(!q.empty())
{
    int size=q.size();
    TreeNode* node;
    for(int i=0;i<size;i++)
    {
        node = q.front();
        q.pop();
        //操作
        if(node->left)    q.push(node->left);
        if(node->right)    q.push(node->right);
    }
}
```

## 从有序数组恢复二叉搜索树
> 这个和恢复最小高度树有什么区别?
```cpp
void Vector2Tree(TreeNode* root, vector<int>& tmp)
{
    if(root == nullptr) return;
    Vector2Tree(root->left,tmp);
    if(root->val == tmp[0])
    {
       tmp.erase(tmp.begin());
    }
    else
    {
       root->val = tmp[0];
       tmp.erase(tmp.begin());
    }
       Vector2Tree(root->right,tmp);
}
```

## 树的高度
```cpp
int treeHeight(TreeNode* root)
{
    if（root==nullptr） return 0;
    int leftHeight = treeHeight(root->left);
    int rightHeight = treeHeight(root->right);
    return max(leftHeight,rightHeight)+1;
}
```

> 二叉树最近公共祖先问题，怎么解？
> 剑指 Offer 68 - II. 二叉树的最近公共祖先”


## 二叉树递归

因为是递归函数，所以在使用过函数后，就认为左右子树已经算出结果。

> 递归带不带返回值的有什么区别?


## 二叉树搜索一条边

```cpp
if(递归函数(root->left)) return left;
if(递归函数(root->right)) return right;
```

## 二叉树遍历整个树
```cpp
Treenode* left = 递归函数（root->left）;
Treenode* right = 递归函数(root->right);
left处理函数
right处理函数
```

如果有处理中间节点的逻辑，那就要注意遍历顺序（前中后序），反之则随意。

## 二叉树用右边子树代替当前节点

```cpp
    root = root->right
```

# 哈希表

## 遍历unordered_map迭代器
```cpp
for ( auto it = mymap.begin(); it != mymap.end(); ++it )         
cout << " " << it->first << ":" << it->second;
```


