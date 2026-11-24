#include <iostream>
#include <string>
using namespace std;

struct Node
{
    string filename;
    Node *left, *right;
};

Node* createNode(string name)
{
    Node* newNode = new Node;
    newNode->filename = name;
    newNode->left = NULL;
    newNode->right = NULL;
    return newNode;
}

Node* insert(Node* root, string name)
{
    if (root == NULL)
        return createNode(name);

    if (name < root->filename)
        root->left = insert(root->left, name);
    else if (name > root->filename)
        root->right = insert(root->right, name);

    return root;
}

void inorder(Node* root)
{
    if (root == NULL)
        return;

    inorder(root->left);
    cout << root->filename << endl;
    inorder(root->right);
}

bool search(Node* root, string key)
{
    if (root == NULL)
        return false;

    if (root->filename == key)
        return true;

    if (key < root->filename)
        return search(root->left, key);
    else
        return search(root->right, key);
}

int main()
{
    Node* root = NULL;
    int n;
    string name, key;

    cout << "Enter number of files: ";
    cin >> n;

    for (int i = 0; i < n; i++)
    {
        cout << "Enter file name: ";
        cin >> name;
        root = insert(root, name);
    }

    cout << "\nFile names in alphabetical order:\n";
    inorder(root);

    cout << "\nEnter file name to search: ";
    cin >> key;

    if (search(root, key))
        cout << "File found!";
    else
        cout << "File not found!";

    return 0;
}
