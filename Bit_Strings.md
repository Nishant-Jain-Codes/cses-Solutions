## Solution 
```cpp 
#include<iostream>
#include<bits/stdc++.h>
using namespace std;
#define lli long long int
const int M = 1000000007;
// time : O(N)
// space : O(1)
// pattern : (maths)
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
void sol(){
	int n ; 
	cin>>n ; 
	lli ans = 1; 
	for( int i = 0;i<n;i++){
		ans = ( ans * 2 ) % mod;
	}
	cout<<ans;
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
- not using direct formula because then it may cause overflow since 2^10^9 , wil definitely cause overflow , so just implement the power function locally and doing the mod at every step 