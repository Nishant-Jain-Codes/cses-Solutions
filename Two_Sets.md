## Solution 
```cpp 
#include<iostream>
#include<bits/stdc++.h>
using namespace std;
#define lli long long int
// time : O(N)
// space : O(N)
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
void sol(lli n){
	lli sum = n*(n+1)/2;
	if(sum%2==0){
		printYorN(true,true);
		lli target = sum/2;
		vector<lli> vec1,vec2;
		for(lli i = n;i>0;i--){
			if(target>=i){
				target-=i;
				vec1.push_back(i);
			}
			else{
				vec2.push_back(i);
			}
		}
		cout<<vec1.size()<<endl;
		printVec<lli>(vec1);
		cout<<vec2.size()<<endl;
		printVec<lli>(vec2);
	}
	else
		printYorN(false);
}
int main(){
	lli s; 
	cin>>s;
	sol(s);
	return 0;
}
```

1. first realization , if `sum_of_n_natural_numbers(n)` is even , then the bifercation into 2 sets is possible 
2. now after this we can start making set by using the largest values first and subtracting them from target and then adding the values in the set 