// 0/1 Knapsack Problem
// Recursive Technique
// Maximizing price by not taking more than weight W
#include <iostream>
#include <cstring>
using namespace std;
#define memo(a,b) memset(a,b,sizeof(a))
#define mx 1000
int price[mx],weight[mx],dp[mx][mx];
int solve(int index,int W,int N)
{
    if(index>N) return 0; // Base case
    if(dp[index][W]!=-1) return dp[index][W];
    int x = 0 , y = 0 ;
    if(weight[index]<=W) x = price[index]+solve(index+1,W-weight[index],N); // Takes the item
    y = solve(index+1,W,N); // Not take the item
    return dp[index][W] = max(x,y);
}
int main()
{
    int N,W; // N is the number of items and W is maximum weight
    cin>>N>>W;
    for(int i=1;i<=N;i++) cin>>price[i]>>weight[i];
    memo(dp,-1);
    cout<<solve(1,W,N)<<endl;
    return 0;
}
