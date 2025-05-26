## Solution 
```cpp
    #include<iostream>
#include<bits/stdc++.h>
using namespace std;
#define lli long long int
const int M = 1000000007;
// time : O(n)
// space : O(nlogn ) 
// pattern : (sorting)
// time taken to solve : (10 min)
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
	int n ; cin>>n;
	vector<lli> s(n,0);
	for(int j = 0;j<n;j++){
		lli num;
		cin>>num;
		s[j] = num;
	}
	sort(s.begin(),s.end());
	// cout<<s.size();
	int i = 1;
	int diff = 1; 
	while(i<n){
		if(s[i]!=s[i-1])
			diff++;
		i++;
	}
	cout<<diff;
}
int main(){
	lli t;
	t=1;
	// cin>>t;
	while(t--){
	sol();
// cout<<endl;
	}
	return 0;
}


```

- initialy i used hashing via set ( but that caused tle ) becuase ther were maybe too many collisions while hasing 