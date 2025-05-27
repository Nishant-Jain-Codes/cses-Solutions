## Solution 
``` cpp 

#include<iostream>
#include<bits/stdc++.h>
using namespace std;
#define lli long long int
const int M = 1000000007;
// time : O(n^2)
// space : O(n^2 ) 
// pattern : (graph traversal , no . of islands counting )
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
void sol(){
	int n,m; 
	cin>>n>>m;
	vector<vector<char>> building(n,vector<char>(m,'#'));
	for(int i = 0;i<n;i++){
		for(int j = 0; j<m;j++){
			char inp; 
			cin>>inp;
			building[i][j] = inp;
		}
	}
	int rooms = 0;
	for(int i = 0;i<n;i++){
		for(int j = 0; j<m;j++){
			if(building[i][j]=='.'){
				// cout<<i<<" "<<j<<endl;
				rooms++;
				dfs(i,j,n,m,building);
			}
		}
	}
	cout<<rooms;
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