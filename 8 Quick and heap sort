#include <iostream>
#include <algorithm>
using namespace std;
void quick(int a[], int l, int r) {
    if (l >= r) return;
    int i = l, j = r, p = a[(l + r) / 2];
    while (i <= j) {
        while (a[i] < p) i++;
        while (a[j] > p) j--;
        if (i <= j) swap(a[i++], a[j--]);
    }
    quick(a, l, j);
    quick(a, i, r);
}
void heap(int a[], int n, int i) {
    int m = i, l = 2*i+1, r = 2*i+2;
    if (l < n && a[l] > a[m]) m = l;
    if (r < n && a[r] > a[m]) m = r;
    if (m != i) {
        swap(a[i], a[m]);
        heap(a, n, m);
    }
}
void heapsort(int a[], int n) {
    for (int i = n/2-1; i >= 0; i--) heap(a,n,i);
    for (int i = n-1; i > 0; i--) {
        swap(a[0],a[i]);
        heap(a,i,0);
    }
}
int main() {
    int n, a[50], b[50];
    cout << "Enter number of elements: ";
    cin >> n;
    cout << "Enter elements: ";
    for(int i=0;i<n;i++) {
        cin >> a[i];
        b[i] = a[i];
    }
    quick(a,0,n-1);
    heapsort(b,n);
    cout << "Quick Sort: ";
    for(int i=0;i<n;i++) cout << a[i] << " ";
    cout << "\nHeap Sort: ";
    for(int i=0;i<n;i++) cout << b[i] << " ";
    return 0;
}
