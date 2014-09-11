// Floyd Warshall transitive closure
// Dynamic Programming
// Time Complexity O(N^3)
// Space Complexity O(N^2)
// N -> Number of nodes
#include <cstdio>
int matrix[50][50];
void Floyd_Warshall(int N)
{
    for(int k=1;k<=N;k++) // k must be before i and j loops .
    {
        for(int i=1;i<=N;i++)
        {
            for(int j=1;j<=N;j++)
            {
                matrix[i][j] = matrix[i][j] || (matrix[i][k] && matrix[k][j]) ;
            }
        }
    }
}
int main()
{
    int N;
    scanf("%d",&N); // Number of nodes
    for(int i=1;i<=N;i++)
    {
        for(int j=1;j<=N;j++)
        {
            scanf("%d",&matrix[i][j]); // 1 indicates there is a edge from i to j . 0 indicates no edge from i to j .
        }
    }
    Floyd_Warshall(N);
    for(int i=1;i<=N;i++)
    {
        for(int j=1;j<=N;j++)
        {
            printf("%d ",matrix[i][j]); // 1 indicates there is a path exist from i to j . 0 indicates no path from i to j .
        }
        puts("");
    }
    return 0;
}
