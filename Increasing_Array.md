## Solution 
```cpp 

#include<iostream>
#include<bits/stdc++.h>
using namespace std;
#define lli long long int
// time : O(N)
// space : O(1)
void sol(lli n){
	lli prev , next , ans = 0;
	cin>>prev;
	for(lli i = 1;i<n ;i++){
		cin>>next;
		if(prev>next)
			ans+= (prev-next);

		prev = max(prev,next);
	}
	cout<<ans;
}
int main(){
	lli s; 
	cin>>s;
	sol(s);
	// while(t--){
	// 	sol(t);
	// }
	return 0;
}

```

- main thing to notice is that prev should be max of prev , next ( max since we have transfered the old number if needed)