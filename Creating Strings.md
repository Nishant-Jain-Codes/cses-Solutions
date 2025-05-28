## Solution 
```cpp

#include<iostream>
#include<bits/stdc++.h>
using namespace std;
#define lli long long int
const int M = 1000000007;
// time : O(n!)
// space : O(n!) 
// pattern : (try all ways)
// time taken to solve : (10 min )
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
vector<pair<int,int>> fourDirections = {
{
	0,-1
},{
	0,1
},{
	-1,0
},
{
	1,0
}

	};
void dfs(int row , int col , int totRows, int totCols , vector<vector<char>>& building){
	// cout<<"dfs->"<<row<<" "<<col<<endl;
	if(building[row][col]=='#' || row>=totRows || row<0 || col>= totCols || col<0)
		return;
	building[row][col] = '#';
	for(auto move : fourDirections){
		int rowNext = row+move.first;
		int colNext = col+move.second;
		if(rowNext>=0 && rowNext<totRows && colNext>=0 && colNext<totCols)
		dfs(rowNext,colNext,totRows,totCols,building);
	}
	return;
}
void getAllStrings(string &s , lli index , unordered_set<string> & set , vector<int>& freq){
	// cout<<s<<endl;
	if(index==(lli)s.length()){
		set.insert(s);
		return;
	}
	char curSIndexValue = s[index];
	for(int i = 0 ; i<26;i++){
		if(freq[i]>0){
			s[index] = i+'a';
			freq[i]--;
			getAllStrings(s,index+1,set,freq);
			s[index]=curSIndexValue;
			freq[i]++;
		}
	}
}
void sol(){
	string s ;
	cin>>s;
	unordered_set<string> set;
	vector<int> freq(26,0);
	for(lli i = 0 ;i<(lli)s.length();i++){
		freq[s[i]-'a']++;
	}
	string curString((lli)s.length(),'_');
	getAllStrings(curString,0,set,freq);
	cout<<set.size()<<endl;
	vector<string> vec(set.begin(),set.end());
	sort(vec.begin(),vec.end());
	for(auto x : vec){
		cout<<x<<endl;
	}
}
int main(){
	lli t;
	t=1;
	// cin>>t;
	while(t--){
	sol();
cout<<endl;
	}
	return 0;
}


```