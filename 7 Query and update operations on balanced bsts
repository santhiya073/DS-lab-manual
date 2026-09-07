#include <iostream>
#include <set>
using namespace std;
int main() {
    set<int> bst = {10, 20, 30, 40, 50};
    int x = 30;
    if (bst.find(x) != bst.end())
        cout << "Query: " << x << " Found\n";
    else
        cout << "Query: " << x << " Not Found\n";
    bst.erase(30);      // Update: delete old value
    bst.insert(35);     // Update: insert new value
    cout << "After Update: ";
    for (int x : bst)
        cout << x << " ";
    return 0;
}
