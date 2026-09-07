#include <iostream>
using namespace std;
int main() {
    int a[5]={10,20,30,40,50}, key=30, l=0,h=4,m=(l+h)/2;
    // Binary Search
    while(l<=h && a[m]!=key) {
        if(key>a[m]) l=m+1;
        else h=m-1;
        m=(l+h)/2;
    }
    cout << "Binary Search: " << (l<=h ? "Found" : "Not Found") << endl;
    // Hashing
    int t[10]={0}, x=30, i=x%10;
    while(t[i] && t[i]!=x) i=(i+1)%10;
    t[i]=x;
    cout << "Hashing: Element " << x << " stored at index " << i;
    return 0;
}
