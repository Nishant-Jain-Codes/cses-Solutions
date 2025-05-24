## Solution

```cpp
#include<iostream>
#include<bits/stdc++.h>
using namespace std;
#define lli long long int
const int M = 1000000007;
// time : O(logN)
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
lli log_custom(lli base , lli n ){
	if(n==0 || base == 0 || n/base == 0)
		return 0;
	return 1 + log_custom(base,n/base);
}
void sol(){
	lli n ; 
	cin>>n ; 
	lli total5 = 0;
	lli divisor = 5;
	while(n/divisor){
		total5 += n/divisor;
		divisor*=5;
	}
	cout<<total5;
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

## new learning 
1. n/5 tells us how many number between 1-n are divisible by 5 atleast once 
2. n/(5*5) tells us how many number between 1-n are divisble by 5 again 
... and so on 
3. so just dividing by 5 once wont give us the power of 5 in the prime factorisation of n! , since we would be missing the five obtined from step 2 