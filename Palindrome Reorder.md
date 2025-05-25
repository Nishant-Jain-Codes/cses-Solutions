## Solution 
```cpp

#include<iostream>
#include<bits/stdc++.h>
using namespace std;
#define lli long long int
const int M = 1000000007;
// time : O(n)
// space : O(n) 
// pattern : (2 pointer and hashing)
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

void sol(){
	unordered_map<char,int> freq;
	string inp; 
	cin>>inp;
	for(auto x:inp){
		freq[x]++;
	}
	int oddCount = 0;
	for(auto x : freq){
		if(x.second%2!=0)
			oddCount++;
	}
	if(oddCount>1)
	{
		cout<<"NO SOLUTION";
		return;
	}
	else{
		string output(inp.length(),'_');
		int start = 0;
		int end = inp.length()-1;
		for(auto x : freq){
			int curFreq = x.second;
			char curChar = x.first;
			if(curFreq%2!=0){
				int middle = inp.length()/2;
				output[middle]=curChar;
				curFreq--;
			}
			while(curFreq>0){
				output[start]=curChar;
				output[end]=curChar;
				start++;
				end--;
				curFreq-=2;
			}
		}
		cout<<output;
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

- if more than 1 odd freq character then the string cant be palindrome 
- and if there is 1 odd freq character then we have to put one of it's instance in center 