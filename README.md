# linked-list
#include <iostream>
#include <cstdlib>
using namespace std;


struct Node
{
    int key;
    int value;
    Node *next;
};

void headInsert(Node *&head, int k, int v);
void printList(Node *head);

int main()
{
    Node *head = NULL;

    int n;
    cin >> n;
    int inputK, inputV;
    for (int i=0 ; i< n ; i++)
    {
        cin >> inputK >> inputV;
        headInsert(head, inputK, inputV);
    }
    printList(head);
}

void headInsert(Node *&head, int k, int v)
{
  Node *newnode=new Node;
  newnode ->next=NULL;
  newnode ->key=k;
  newnode ->value=v;
  newnode ->next=head;
  head = newnode;
  
}

void printList(Node *head)
{
    while(head!=NULL)
    {
      cout<<"key:"<<head->key<<","<<"value:"<<head->value<<endl;
      head=head->next;
    }
}
