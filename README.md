# Dheeksha-data-structure-18
#include<stdio.h>
#include<stdlib.h>

struct node{
    int data;
    struct node *left,*right;
};

struct node* create(int data){
    struct node* n=(struct node*)malloc(sizeof(struct node));
    n->data=data;
    n->left=n->right=NULL;
    return n;
}

struct node* insert(struct node* root,int data){
    if(root==NULL)
        return create(data);

    if(data < root->data)
        root->left=insert(root->left,data);
    else
        root->right=insert(root->right,data);

    return root;
}

void inorder(struct node* root){
    if(root){
        inorder(root->left);
        printf("%d ",root->data);
        inorder(root->right);
    }
}

int main(){
    struct node* root=NULL;

    root=insert(root,200);
    root=insert(root,150);
    root=insert(root,250);

    printf("Product IDs in AVL Tree: ");
    inorder(root);

    return 0;
}
Product IDs in AVL Tree: 150 200 250
