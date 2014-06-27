// Matrix Chain Multiplication Dynamic Problem
// Time Complexity O(N^3)
// Space Complexity O(N^2)
#include <cstdio>
#include <cstring>
#include <iostream>
using namespace std;
#define mx 100
#define memo(a,b) memset(a,b,sizeof(a))
int row[mx],col[mx];long long dp[mx][mx];
int N; // Number of matrixes
long long solve(int beg,int end)
{
    long long &ret = dp[beg][end];
    if(beg>=end) return ret = 0;
    if(ret!=-1) return ret;
    ret = 1<<30;
    for(int mid=beg;mid<end;mid++) // Divide the whole part in two parts
    {
        long long left = solve(beg,mid);
        long long right = solve(mid+1,end);
        long long  multiply_left_right = row[beg]*col[mid]*col[end];
        ret = min(ret,left+right+multiply_left_right);
    }
    return ret;
}
string printSolution(int beg,int end)
{
    string ans="";
    if(beg>=end)
    {
        ans=ans+'A';
        if(beg>9)
        {
            ans = ans + (char)(beg/10+48);
            ans = ans + (char)(beg%10+48);
        }
        else ans=ans+(char)(beg+48);
        return ans;
    }
    for(int mid=beg;mid<end;mid++)
    {
        if(dp[beg][end]==dp[beg][mid]+dp[mid+1][end]+row[beg]*col[mid]*col[end])
        {
            ans='(';
            string x = printSolution(beg,mid);
            string y = printSolution(mid+1,end);
            x=x+',';
            ans=ans+x+y+')';
            if(beg==1&&end==N) cout<<ans<<endl;
            else break; // If don't need to print few solutions than just write break . No need else condition .
        }
    }
    return ans;
}
int main()
{
    scanf("%d",&N);
    for(int i=1;i<=N;i++) scanf("%d%d",&row[i],&col[i]);
    memo(dp,-1);
    printf("%d\n",solve(1,N));
    printSolution(1,N);
    return 0;
}
/*
10
1 5
5 20
20 30
30 40
40 60
60 1
1 2
2 1
1 5
5 5
/*
4338
(((A1,(A2,(A3,(A4,(A5,A6))))),(A7,A8)),(A9,A10))
((((A1,(A2,(A3,(A4,(A5,A6))))),(A7,A8)),A9),A10)
*/
