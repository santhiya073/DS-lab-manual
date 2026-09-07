#include <iostream>
using namespace std;
#define N 4
#define INF 999
int main() {
    int g[N][N]={{0,10,6,5},{10,0,0,15},{6,0,0,4},{5,15,4,0}};
    int v[N]={0}, d[N], p[N], mst=0;
    // Prim's MST
    v[0]=1;
    cout<<"MST Edges: ";
    for(int k=0;k<N-1;k++){
        int m=INF,x=-1,y=-1;
        for(int i=0;i<N;i++) if(v[i])
            for(int j=0;j<N;j++)
                if(!v[j] && g[i][j] && g[i][j]<m)
                    m=g[i][j],x=i,y=j;
        v[y]=1; mst+=m;
        cout<<"("<<x+1<<"-"<<y+1<<") ";
    }
    cout<<"\nMST Cost: "<<mst;
    // Dijkstra
    for(int i=0;i<N;i++) d[i]=INF,v[i]=0;
    d[0]=0;
    for(int k=0;k<N;k++){
        int m=INF,x=-1;
        for(int i=0;i<N;i++)
            if(!v[i]&&d[i]<m) m=d[i],x=i;
        v[x]=1;
        for(int i=0;i<N;i++)
            if(g[x][i] && d[i]>d[x]+g[x][i])
                d[i]=d[x]+g[x][i];
    }
    cout<<"\nShortest paths from 1: ";
    for(int i=0;i<N;i++) cout<<d[i]<<" ";
    return 0;
}
