#include <iostream>

using namespace std;

struct Folder
{
    string name; // folder name
    Folder *left, *right; // Stores the address of the left and right subfolder.
};

Folder* createFolder(string name) // creates a function that receives a folder name.
{
    Folder* newFolder = new Folder; // creates a new folder node in memory.
    newFolder->name = name; // stores the folder name.
    newFolder->left = NULL; // means there is no left subfolder initially.
    newFolder->right = NULL; // means there is no right subfolder initially.
    return newFolder;
}

void preorder(Folder* root)
{
    if (root == NULL)
        return;

    cout << root->name << " ";
    preorder(root->left);
    preorder(root->right);
}

void searchFolder(Folder* root, string key)
{
    if (root == NULL)
        return;

    if (root->name == key)
    {
        cout << "Folder found!";
    }
    else
    {
        searchFolder(root->left, key);
        searchFolder(root->right, key);
    }
}

int main()
{
    Folder* root = createFolder("Main");

    root->left = createFolder("Documents");
    root->right = createFolder("Pictures");

    root->left->left = createFolder("Assignments");
    root->left->right = createFolder("Notes");

    cout << "Folder Structure: ";
    preorder(root);

    cout << "\n\nSearching for Notes: ";
    searchFolder(root, "Notes");

    return 0;
}
