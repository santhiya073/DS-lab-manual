#include <iostream>
#include <algorithm>
using namespace std;
struct Node {
    int key;
    Node *left, *right;
    int height;
};
int height(Node *N) {
    if (N == nullptr)
        return 0;
    return N->height;
}
int getBalance(Node *N) {
    if (N == nullptr)
        return 0;
    return height(N->left) - height(N->right);
}
Node* createNode(int key) {
    Node* node = new Node();
    node->key = key;
    node->left = nullptr;
    node->right = nullptr;
    node->height = 1;
    return node;
}
// Right Rotation - LL Case
Node* rightRotate(Node *y) {
    Node *x = y->left;
    Node *T2 = x->right;
    x->right = y;
    y->left = T2;
    y->height = 1 + max(height(y->left), height(y->right));
    x->height = 1 + max(height(x->left), height(x->right));
    return x;
}
// Left Rotation - RR Case
Node* leftRotate(Node *x) {
    Node *y = x->right;
    Node *T2 = y->left;
    y->left = x;
    x->right = T2;
    x->height = 1 + max(height(x->left), height(x->right));
    y->height = 1 + max(height(y->left), height(y->right));
    return y;
}
Node* insert(Node* node, int key) {
    if (node == nullptr)
        return createNode(key);
    if (key < node->key)
        node->left = insert(node->left, key);
    else if (key > node->key)
        node->right = insert(node->right, key);
    else
        return node;
    node->height = 1 + max(height(node->left),
                            height(node->right));
    int balance = getBalance(node);
    // LL Case
    if (balance > 1 && key < node->left->key)
        return rightRotate(node);
    // RR Case
    if (balance < -1 && key > node->right->key)
        return leftRotate(node);
    // LR Case
    if (balance > 1 && key > node->left->key) {
        node->left = leftRotate(node->left);
        return rightRotate(node);
    }
    // RL Case
    if (balance < -1 && key < node->right->key) {
        node->right = rightRotate(node->right);
        return leftRotate(node);
    }
    return node;
}
void inorder(Node* root) {
    if (root != nullptr) {
        inorder(root->left);
        cout << root->key << " ";
        inorder(root->right);
    }
}
int main() {
    Node* root = nullptr;
    int n, value;
    cout << "Enter number of elements: ";
    cin >> n;
    cout << "Enter elements: ";
    for (int i = 0; i < n; i++) {
        cin >> value;
        root = insert(root, value);
    }
    cout << "Inorder Traversal of AVL Tree: ";
    inorder(root);
    return 0;
}
