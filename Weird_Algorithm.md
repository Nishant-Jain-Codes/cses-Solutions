### Solution : 
```cpp
#include<iostream>
using namespace std;
// time : O(N)
// space : O(N)

void sol(long long int n){
	// cout<<"working\n";
	cout<<n;
	if(n==1)
		return;
	cout<<" ";
	sol(n%2==0 ? n/2 : (n*3)+1);

}
int main(){
	long long int t; 
	cin>>t;
	sol(t);
	// while(t--){
	// 	sol(t);
	// }
	return 0;
}

```
-  has to use long long int because due to multiplicagtion the number was getting overflowed 
- we can reduce space to O(1) by using loop rather than recursion