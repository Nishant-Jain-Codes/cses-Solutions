```cpp
#include<iostream>
using namespace std;
#define lli long long int
// time : O(N)
// space : O(1)
void sol(lli n){
	lli maxSum = n*(n+1)/2;
	lli curSum = 0;
	for(lli i = 0 ; i<n - 1; i++ ){
		lli input ; cin>>input ; 
		curSum+=input;
	}
	cout<<maxSum-curSum;

}
int main(){
	lli t; 
	cin>>t;
	sol(t);
	// while(t--){
	// 	sol(t);
	// }
	return 0;
}
```
- here rather than adding the input into `curSum` , we can just subtract the values of `input[i]` from `maxSum` thus after the loop we would be left with the ans