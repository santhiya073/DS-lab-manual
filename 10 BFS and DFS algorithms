#include <iostream>
#include <queue>
using namespace std;
int a[5][5]={{0,1,1,0,0},{1,0,0,1,0},{1,0,0,0,1},
             {0,1,0,0,1},{0,0,1,1,0}}, v[5];
void dfs(int x) {
    cout << x+1 << " ";
    v[x]=1;
    for(int i=0;i<5;i++)
        if(a[x][i] && !v[i]) dfs(i);
}
void bfs(int s) {
    queue<int> q;
    q.push(s); v[s]=1;
    while(!q.empty()) {
        int x=q.front(); q.pop();
        cout << x+1 << " ";
        for(int i=0;i<5;i++)
            if(a[x][i] && !v[i])
                v[i]=1, q.push(i);
    }
}
int main() {
    cout << "BFS: ";
    bfs(0);
    for(int i=0;i<5;i++) v[i]=0;
    cout << "\nDFS: ";
    dfs(0);
}
