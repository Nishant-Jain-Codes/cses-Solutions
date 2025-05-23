## Solution

```cpp

#include<iostream>
#include<bits/stdc++.h>
using namespace std;
#define lli long long int
// time : O(N)
// space : O(1)
void sol(string s){
	lli maxLen = 0;
	char curChar = s[0];
	lli curLen = 1;
	for(lli i = 1 ; i< static_cast<lli>(s.length()) ;i++){

		if(curChar != s[i])
			{maxLen = max(maxLen,curLen);
		curLen=1;}
		else 
			curLen++;
		curChar = s[i];
	}
	maxLen = max(maxLen,curLen);
	cout<<maxLen;
}
int main(){
	string s; 
	cin>>s;
	sol(s);
	// while(t--){
	// 	sol(t);
	// }
	return 0;
}

```

- the solution can be cleaned up a bit , i dont need curChar , i can just keep a running max , and find the longes sequence by comparing current and previous character 