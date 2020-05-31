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
