## Solution
```cpp

#include<iostream>
#include<bits/stdc++.h>
using namespace std;
#define lli long long int
const int M = 1000000007;
// time : O(2^n)
// space : O(2^n) 
// pattern : (backtracking)
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
bool isValid(int n ,int row , int col, vector<vector<char>>& board){
	// vertical 
	for(int r = row-1 ; r>=0;r--){
		if(board[r][col]=='Q')
			return false;
	}
	for(int r = row-1,c = col-1; r>=0&&c>=0;r--,c--){
		if(board[r][c]=='Q')
			return false;
	}
	for(int r = row-1,c=col+1;r>=0&&c<n;r--,c++){
		if(board[r][c]=='Q')
			return false;
	}
	return true;
}
lli nQueens(int n ,int row, vector<vector<char>> & board){
	if(row>=n){
		return 1;
	}
	lli ans = 0;
	for(int col = 0;col<n;col++){
		if(board[row][col]=='.'){
			board[row][col]='Q';
			if(isValid(n,row,col,board)){
				ans+=nQueens(n,row+1,board);
			}
			board[row][col]='.';
		}
	}
	return ans;
}
void sol(){
	int n = 8 ; 
	vector<vector<char>> board(n,vector<char>(n,'_'));
	for(int i = 0 ; i<n;i++){
		for(int j = 0 ; j<n;j++){
			cin>>board[i][j];
			// cout<<board[i][j];
		}
		// cout<<endl;
	}
	cout<<nQueens(n,0,board);
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

- just returning 1 ,when i have reached a row which is outside my board , that means i have come up with a valid posistion for the queen .