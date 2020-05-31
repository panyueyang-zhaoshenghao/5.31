# 第一题
直接抄模板
```cpp
#include<bits/stdc++.h>
using namespace std;
int main()
{
		int n;
		cin>>n;
		int a[1001],d[1001],len;
		for(int i=1;i<=n;i++)
		{
			cin>>a[i];
		}
		d[1]=a[1];len=1;
		for(int i=2;i<=n;i++)
		{
			if(a[i]>d[len])d[++len]=a[i];
			else *lower_bound(d+1,d+len+1,a[i])=a[i];
		}
		cout<<len;
}
```
# 第二题
```cpp
#include<stdio.h>
#include<algorithm>
using namespace std;
struct node
{
    int north;
    int south;//先定义一个结构体，里面包含了north（北岸城市）和south（南岸城市）
};
node a[200005];
int n,i,d[200005],len,temp;
bool cmp(node x,node y)
{
    return x.north<y.north;//我们只需要对北岸排序求南岸的最长不下降子序列即可（可以反过来，对南岸排序求北岸的最长不下降子序列）
}
int main ()
{
    scanf("%d",&n);
    for(i=1;i<=n;i++)
    {
        scanf("%d",&a[i].north);
        scanf("%d",&a[i].south);
    }
    sort(a+1,a+1+n,cmp);
    d[++len]=a[1].south;
    for(i=2;i<=n;i++)
    {
        int dbzjrQwQ=upper_bound(d+1,d+len+1,a[i].south)-d;
        d[dbzjrQwQ]=a[i].south;
        if(dbzjrQwQ>len)
        {
            len++;
        }
    }
    printf("%d",len);
    return 0;
}
```
参考`luogu`题目[`P2782`](https://www.luogu.com.cn/problem/P2782)
