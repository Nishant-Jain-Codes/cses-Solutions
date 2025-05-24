## Solution
```cpp
#include<iostream>
#include<bits/stdc++.h>
using namespace std;
#define lli long long int
const int M = 1000000007;
// time : O(n)
// space : O(1)
// pattern : (greedy)
// time taken to solve : (8 min)
void printYorN(bool val,bool newLine=false){
	if(val)
		cout<<"YES";
	else
		cout<<"NO";
	if(newLine)
		cout<<endl;
}
template <typename T>
void printVec(vector<T> &vec){
	for(lli i =0 ;i < vec.size();i++)
		cout<<vec[i]<<" ";
	cout<<endl;
}
lli log_custom(lli base , lli n ){
	if(n==0 || base == 0 || n/base == 0)
		return 0;
	return 1 + log_custom(base,n/base);
}
void sol(){
	lli n ; 
	cin>>n ; 
	if(n==2 || n == 3)
		{
			cout<<"NO SOLUTION";
			return;
		}
	else{
		for(lli i = 2 ; i <= n ; i+=2){
			cout<<i<<" ";
		}
		for(lli i = 1 ; i <= n ; i+=2){
			cout<<i<<" ";
		}
	
	}
}
int main(){
	lli t; t=1;
	// cin>>t;
	while(t--){
	sol();
cout<<endl;
	}
	return 0;
}

```
- for n == 2 and 3 the answer dont exists , else for all it does exists .