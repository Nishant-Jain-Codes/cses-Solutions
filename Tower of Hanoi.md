## Solution 
```cpp 

#include<iostream>
#include<bits/stdc++.h>
using namespace std;
#define lli long long int
const int M = 1000000007;
// time : O(2^n)
// space : O(2^n) // call stack 
// pattern : (dfs)
// time taken to solve : (3 min)
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

void toh(vector<pair<int,int>>& path , int n , int s , int a , int d){
	if(n==1)
	{
		path.push_back({s,d});
		return;
	}
	toh(path,n-1,s,d,a);
	path.push_back({s,d});
	toh(path,n-1,a,s,d);
}
void sol(){
	int n ; 
	cin>>n;
	vector<pair<int,int>> path; 
	toh(path,n,1,2,3);
	cout<<path.size()<<endl;
	for(int i = 0;i<path.size();i++){
		cout<<path[i].first<<" "<<path[i].second<<endl;
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
- basic toh problem 