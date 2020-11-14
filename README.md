# -Assignment-1-



// a.creation : creates the link list

#include <stdio.h>

#include<stdlib.h>

struct node{
    int data;
    struct node *next;
};


//typedef struct node node;


int main(){
    struct node *head=NULL;
    struct node *first=NULL;
    struct node *second=NULL;

     
     printf("\n\n head:%p, first:%p, second:%p", head,first,second);
     
     head=(struct node*)malloc(sizeof(struct node));
     first=(struct node*)malloc(sizeof(struct node));
     second=(struct node*)malloc(sizeof(struct node));
     
     printf("\n\n head:%p, first:%p, second:%p", head,first,second);
     
     
     head->data=10;
     head->next=first;
     first->data=20;
     first->next=second;
     second->data=30;
     second->next=NULL;
     
    //  printf("\n\n  printing my list:");
     
     struct node *temp = head;
     
     while(temp!=NULL){
         printf("%d",temp->data);
         temp=temp->next;
         
     }
     return 0;
     
}




// b.Insertion : insert an element at the Beigning

#include <stdio.h>
#include<stdlib.h>
void insertAtBeigning (float val);
void insertAtend (float val);
struct node{
    float data;
    struct node *link ;
};


struct node *head=NULL;

void print(){
    struct node *temp;
    temp= head;
    while(temp!=NULL){
        printf("%.1f\n",temp->data);
        temp=temp->link;
    }
     printf("\n\n printing :\n");

}


void insertAtBeigning (float val){
    struct node *newnode = malloc(sizeof(struct node));
    newnode -> data = val;
    newnode ->link =head;
    head = newnode;
     while(newnode!=NULL){
        printf("%.1f\n",newnode->data);
        newnode=newnode->link;
    }

}




int main(){

    head = (struct node*)malloc(sizeof(struct node));
    head->data=1.3;
    head->link=(struct node*)malloc(sizeof(struct node));
    head->link->data=2.3;
    head->link->link=NULL;
    print();
    insertAtBeigning (5.7);
    
     return 0;
}




// c.Deletion :DELETES FIRST NODE

#include <stdio.h>
#include<stdlib.h>
void printList(); 
 void printLis();
struct node{
    int data;
    struct node *next ;
};

struct node *head;

int main(){
  head = (struct node*)malloc(sizeof(struct node));
 struct node  * first = (struct node*)malloc(sizeof(struct node));
 struct node   *second = (struct node*)malloc(sizeof(struct node));
 struct node   *third = (struct node*)malloc(sizeof(struct node));
 struct node   *fourth = (struct node*)malloc(sizeof(struct node));

    head ->data = 8;
    head->next = first;
    first->data= 2;
    first->next= second;
    second->data= 4;
    second->next= third;

    third->data = 3;
    third->next = fourth;
    fourth->data = 7;
    fourth->next = NULL;
    printList();
    
    
    
    struct node *temp;
    temp=head;
    head=head->next;
    free(temp);
    printLis();

}







    void printList (){

       
       
         printf("\n\n printing List:");
        struct node *temp= head;

        while(temp!=NULL){
            printf("%d,",temp->data);
            temp=temp->next;
        }
        printf("\n\n\n\n\n");
    }
    
    
      void printLis (){
          
          
           printf("\n\n Delete First Node(8):");
           
           
           
            struct node *temp= head;

        while(temp!=NULL){
            printf("%d,",temp->data);
            temp=temp->next;
        }
        printf("\n\n\n\n\n");
    }
    
    
  
  
  
  // d.Traversing :------


#include <stdio.h>

#include<stdlib.h>

struct node{
    int data;
    struct node *next;
};

int main(){
    struct node *head=NULL;
    struct node *first=NULL;
    struct node *second=NULL;

     
     printf("\n\n head:%p, first:%p, second:%p", head,first,second);
     
     head=(struct node*)malloc(sizeof(struct node));
     first=(struct node*)malloc(sizeof(struct node));
     second=(struct node*)malloc(sizeof(struct node));
     
     printf("\n\n head:%p, first:%p, second:%p", head,first,second);
     
     
     head->data=10;
     head->next=first;
     first->data=20;
     first->next=second;
     second->data=30;
     second->next=NULL;
     
     printf("\n\n  printing my list:");
     
     struct node *temp = head;
     int count_node=0;
     while(temp!=NULL){
        count_node++;
        temp=temp->next;
        }
         printf("\n\n Number of node: %d \n",count_node);
         
     }
    
    
  
  
//e. Search data :


#include <stdio.h>

#include<stdlib.h>

struct node{
    int data;
    struct node *next;
};


int main(){
    struct node *head=NULL;
    struct node *first=NULL;
    struct node *second=NULL;

     
     printf("\n\n head:%p, first:%p, second:%p", head,first,second);
     
     head=(struct node*)malloc(sizeof(struct node));
     first=(struct node*)malloc(sizeof(struct node));
     second=(struct node*)malloc(sizeof(struct node));
     
     printf("\n\n head:%p, first:%p, second:%p", head,first,second);
     
     
     head->data=10;
     head->next=first;
     first->data=20;
     first->next=second;
     second->data=30;
     second->next=NULL;
     
     printf("\n\n  printing my list:");
     
     struct node *temp = head;
     
     while(temp!=NULL){
       
        if(temp->data==10){
            printf("Found data: %d \n",temp->data);
        }
         temp=temp->next;
         
     }
     
    
     return 0;
     
}


  
// f. isEmpty(): returns true if the list is empty and false otherwise.
 
#include<stdio.h>
#include<stdbool.h>

#define CAPACITY 5

int ourQueue[CAPACITY];
int front = 0, rear = -1, totalItem = 0;


bool isEmpty(){
    if(totalItem == 0){
        return true;
    }
    return false;
}


int dequeue(){
    if(isEmpty()){
        printf("Sorry, the Queue is empty.\n");
        return -1;
    }
    int frontItem = ourQueue[front];
    ourQueue[front] = -1;
    front = (front + 1) % CAPACITY;
    totalItem--;
    return frontItem;
}

void printQueue(){
    int i;
    printf("Queue: ");
    for (i = 0; i < CAPACITY; i++){
        printf("%d ", ourQueue[i]);
    }
    printf("\n");
}

int main(){
    printf(" implement our Queue.\n\n");
    printf("Deque: %d\n", dequeue());
    printQueue();
    return 0;
}
 
 
 
 
 
 
 
 //g.insertFirst(int data) inserts data before the first
element in the list (if the list is non-empty) or simply adds
data to the list (if the list is empty).

#include <stdio.h>
#include<stdlib.h>
struct Node{
int data;
struct Node *next;};
struct Node *head;
void Insert(int x){
struct Node* temp=( struct Node*)malloc(sizeof(struct
Node));
temp->data=x;
temp->next=head;
head=temp;
}
void print(){
struct Node *temp;
temp= head;
printf(" printing :");while(temp!=NULL){
printf("%d\n",temp->data);
temp=temp->next;
}
printf("\n");
}
int main(){
head = NULL;
printf("HOW many NUmber?\n");
int n,i,x;
scanf("%d",&n);
for(i=0;i<n;i++){
printf("Enter the NUmber\n");
scanf("%d",&x);
Insert(x);
print();
}}
h.insertLast(data) inserts data after the last element in
the list (if the list is non-empty) or simply adds data to
the list.

#include <stdio.h>
#include <stdlib.h>
struct node {
int data;
struct node *next;
}*head;void createList(int n);
void insertNodeAtEnd(int data);
void displayList();
int main()
{
int n, data;
printf("Enter the total number of nodes: ");
scanf("%d", &n);
createList(n);
printf("\nData in the list \n");
displayList();printf("\nEnter data to insert at end of the list: ");
scanf("%d", &data);
insertNodeAtEnd(data);
printf("\nData in the list \n");
displayList();
return 0;
}
void createList(int n)
{
struct node *newNode, *temp;
int data, i;
head = (struct node *)malloc(sizeof(struct node));if(head == NULL)
{
printf("Unable to allocate memory.");
}
else
{
printf("Enter the data of node 1: ");
scanf("%d", &data);
head->data = data; // Link the data field with data
head->next = NULL; // Link the address field to NULL
temp = head;
for(i=2; i<=n; i++)
{newNode = (struct node *)malloc(sizeof(struct
node));
if(newNode == NULL)
{
printf("Unable to allocate memory.");
break;
}
else
{
printf("Enter the data of node %d: ", i);
scanf("%d", &data);
newNode->data = data;
newNode->next = NULL;
temp->next = newNode;
temp = temp->next;}
}
printf("SINGLY LINKED LIST CREATED
SUCCESSFULLY\n");
}
}
void insertNodeAtEnd(int data)
{
struct node *newNode, *temp;
newNode = (struct node*)malloc(sizeof(struct node));
if(newNode == NULL)
{
printf("Unable to allocate memory.");}
else
{
newNode->data = data;
newNode->next = NULL;
temp = head;
while(temp != NULL && temp->next != NULL)
temp = temp->next;
temp->next = newNode;
printf("DATA INSERTED SUCCESSFULLY\n");
}
}void displayList()
{
struct node *temp;
if(head == NULL)
{
printf("List is empty.");
}
else
{
temp = head;
while(temp != NULL)
{
printf("Data = %d\n", temp->data);
temp = temp->next;
}
}
}
 
 


m.deleteFirst(): deletes the first element of the list. It returns true if a deletion was performed.

#include <stdio.h>
#include<stdlib.h>
void printList(); 
struct node{
    int data;
    struct node *next ;
};

struct node *head;

int main(){
  head = (struct node*)malloc(sizeof(struct node));
 struct node  * first = (struct node*)malloc(sizeof(struct node));
 struct node   *second = (struct node*)malloc(sizeof(struct node));
 struct node   *third = (struct node*)malloc(sizeof(struct node));
 struct node   *fourth = (struct node*)malloc(sizeof(struct node));

    head ->data = 8;
    head->next = first;
    first->data= 2;
    first->next= second;
    second->data= 4;
    second->next= third;

    third->data = 3;
    third->next = fourth;
    fourth->data = 7;
    fourth->next = NULL;
    printList();





    struct node  *temp=head;
    head=head->next;
    free(temp);
    printList();
    return 0;
}



    void printList (){

        printf("\n\n printing List delete(8):");
        printf("\n\n printing List:");
        struct node *temp= head;

        while(temp!=NULL){
            printf("%d,",temp->data);
            temp=temp->next;
        }
        printf("\n\n\n\n\n");
    }








//n .deleteLast(): deletes the last element of the list. It returns true if a deletion was performed.


#include <stdio.h>
#include <stdlib.h>
 

struct Node {
    int data;
    struct Node* next;
};
 

void push(struct Node** head_ref, int data)
{
   
    struct Node* ptr1 = (struct Node*)malloc(sizeof(struct Node));
    ptr1->data = data;
    ptr1->next = *head_ref;
 
    
    if (*head_ref != NULL) {
       
        struct Node* temp = *head_ref;
        while (temp->next != *head_ref)
            temp = temp->next;
        temp->next = ptr1;
    }
    else
        ptr1->next = ptr1;
 
    *head_ref = ptr1;
}
 

void printList(struct Node* head)
{
    struct Node* temp = head;
    if (head != NULL) {
        do {
            printf("%d ", temp->data);
            temp = temp->next;
        } while (temp != head);
    }
 
    printf("\n");
}
 

void deleteNode(struct Node* head, int key)
{
    if (head == NULL)
        return;
 
   
    struct Node *curr = head, *prev;
    while (curr->data != key) 
    {
        if (curr->next == head)
        {
            printf("\nGiven node is not found"
                   " in the list!!!");
            break;
        }
 
        prev = curr;
        curr = curr->next;
    }
 
    
    if (curr->next == head) 
    {
        head = NULL;
        free(curr);
        return;
    }
 
   
    if (curr == head) 
    {
        prev = head;
        while (prev->next != head)
            prev = prev->next;
        head = curr->next;
        prev->next = head;
        free(curr);
    }
 
  
    else if (curr->next == head && curr == head) 
    {
        prev->next = head;
        free(curr);
    }
    else
    {
        prev->next = curr->next;
        free(curr);
    }
}
 

int main()
{
   
    struct Node* head = NULL;
 
    
    push(&head, 5);
    push(&head, 6);
    push(&head, 7);
    push(&head, 8);
    push(&head, 10);
 
    printf("List Before Deletion: ");
    printList(head);
 
    deleteNode(head, 5);
 
    printf("List After Deletion: ");
    printList(head);
 
    return 0;
}



o.deleteAt(int pos): deletes element at position pos in the list (the head is at position 0) if pos is within the bounds of the list. It returns true if a deletion was performed.




#include <stdio.h> 
#include <stdlib.h> 
  
struct Node 
{ 
    int data; 
    struct Node *next; 
}; 
  

void push(struct Node** head_ref, int new_data) 
{ 
    struct Node* new_node = (struct Node*) malloc(sizeof(struct Node)); 
    new_node->data  = new_data; 
    new_node->next = (*head_ref); 
    (*head_ref)    = new_node; 
} 
  

void deleteNode(struct Node **head_ref, int position) 
{ 
  
   if (*head_ref == NULL) 
      return; 
  struct Node* temp = *head_ref; 
  
    if (position == 0) 
    { 
        *head_ref = temp->next;   
        free(temp);               
        return; 
    } 
  
    for (int i=0; temp!=NULL && i<position-1; i++) 
         temp = temp->next; 
  
    if (temp == NULL || temp->next == NULL) 
         return; 
  
    
    struct Node *next = temp->next->next; 
    free(temp->next);  
    temp->next = next;  
} 
  

void printList(struct Node *node) 
{ 
    while (node != NULL) 
    { 
        printf(" %d ", node->data); 
        node = node->next; 
    } 
} 
  

int main() 
{ 
   
    struct Node* head = NULL; 
  
    push(&head, 2); 
    push(&head, 6); 
    push(&head, 5); 
    push(&head, 8); 
    push(&head, 10); 
  
    puts("Created Linked List: "); 
    printList(head); 
    deleteNode(&head, 0); 
    puts("\nLinked List after Deletion at position 0: "); 
    printList(head); 
    return 0; 
}











 
 3.Write a function which reverses the list. Print the reversed list.

#include <stdio.h>
#include <stdlib.h>
 

struct Node {
    int data;
    struct Node* next;
};
 

static void reverse(struct Node** head_ref)
{
    struct Node* prev = NULL;
    struct Node* current = *head_ref;
    struct Node* next = NULL;
    while (current != NULL) {
       
        next = current->next;
        current->next = prev;
        prev = current;
        current = next;
    }
    *head_ref = prev;
}
 

void push(struct Node** head_ref, int new_data)
{
    struct Node* new_node = (struct Node*)malloc(sizeof(struct Node));
    new_node->data = new_data;
    new_node->next = (*head_ref);
    (*head_ref) = new_node;
}
 

void printList(struct Node* head)
{
    struct Node* temp = head;
    while (temp != NULL) {
        printf("%d  ", temp->data);
        temp = temp->next;
    }
}
 

int main()
{
    struct Node* head = NULL;
    push(&head, 10);
    push(&head, 20);
    push(&head, 30);
    push(&head, 40);
    printf("Given linked list\n");
    printList(head);
    reverse(&head);
    printf("\nReversed Linked list \n");
    printList(head);
    getchar();
} 
 
 
 
 
 
4.How to make a linked list circular? Write the code. 
 
 #include <stdio.h>
#include <stdlib.h>


struct node {
    int data;
    struct node * next;
}*head;



void createList(int n);
void displayList();


int main()
{
    int n, data, choice=1;

    head = NULL;

   
    while(choice != 0)
    {
        printf("============================================\n");
        printf("CIRCULAR LINKED LIST PROGRAM\n");
        printf("============================================\n");
        printf("1. Create List\n");
        printf("2. Display list\n");
        printf("0. Exit\n");
        printf("--------------------------------------------\n");
        printf("Enter your choice : ");

        scanf("%d", &choice);

        switch(choice)
        {
            case 1:
                printf("Enter the total number of nodes in list: ");
                scanf("%d", &n);
                createList(n);
                break;
            case 2:
                displayList();
                break;
            case 0:
                break;
            default:
                printf("Error! Invalid choice. Please choose between 0-2");
        }

        printf("\n\n\n\n\n");
    }

    return 0;
}



void createList(int n)
{
    int i, data;
    struct node *prevNode, *newNode;

    if(n >= 1)
    {
       
        head = (struct node *)malloc(sizeof(struct node));

        printf("Enter data of 1 node: ");
        scanf("%d", &data);

        head->data = data;
        head->next = NULL;

        prevNode = head;

      
        for(i=2; i<=n; i++)
        {
            newNode = (struct node *)malloc(sizeof(struct node));

            printf("Enter data of %d node: ", i);
            scanf("%d", &data);

            newNode->data = data;
            newNode->next = NULL;

            
            prevNode->next = newNode;

            
            prevNode = newNode;
        }

        
        prevNode->next = head;

        printf("\nCIRCULAR LINKED LIST CREATED SUCCESSFULLY\n");
    }
}



void displayList()
{
    struct node *current;
    int n = 1;

    if(head == NULL)
    {
        printf("List is empty.\n");
    }
    else
    {
        current = head;
        printf("DATA IN THE LIST:\n");

        do {
            printf("Data %d = %d\n", n, current->data);

            current = current->next;
            n++;
        }while(current != head);
    }
}
 
    








2.Create two lists A and B, concatenate B at the end of A and then print.



#include<stdio.h>
#include<stdlib.h>

struct node
{
        int info;
        struct node *link;
};
struct node *create_list(struct node *);
struct node *concat( struct node *start1,struct node *start2);
struct node *addatbeg(struct node *start, int data);
struct node *addatend(struct node *start,int data);
void display(struct node *start);

int main()
{
        struct node *start1=NULL,*start2=NULL;
        start1=create_list(start1);
        start2=create_list(start2);
        printf("\nFirst list is  : ");
        display(start1);
        printf("\nSecond list is  : ");
        display(start2);
        start1=concat(start1, start2);
        printf("\nConcatenated list is  : ");
        display(start1);

        return 0;

}

struct node *concat( struct node *start1,struct node *start2)
{
        struct node *ptr;
        if(start1==NULL)
        {
                start1=start2;
                return start1;
        }
        if(start2==NULL)
                return start1;
        ptr=start1;
        while(ptr->link!=NULL)
                ptr=ptr->link;
        ptr->link=start2;
        return start1;
}
struct node *create_list(struct node *start)
{
        int i,n,data;
        printf("\nEnter the number of nodes :\n ");
        scanf("%d",&n);
        start=NULL;
        if(n==0)
                return start;

        printf("Enter the element to be inserted :\n ");
        scanf("%d",&data);
        start=addatbeg(start,data);

        for(i=2;i<=n;i++)
        {
                printf("Enter the element to be inserted :\n ");
                scanf("%d",&data);
                start=addatend(start,data);
        }
        return start;
}

void display(struct node *start)
{
        struct node *p;
        if(start==NULL)
        {
                printf("\nList is empty\n");
                return;
        }
        p=start;
        while(p!=NULL)
        {
                printf("%d ", p->info);
                p=p->link;
        }
        printf("\n");
}

struct node *addatbeg(struct node *start,int data)
{
        struct node *tmp;
        tmp=(struct node *)malloc(sizeof(struct node));
        tmp->info=data;
        tmp->link=start;
        start=tmp;
        return start;
}

struct node *addatend(struct node *start, int data)
{
        struct node *p,*tmp;
        tmp= (struct node *)malloc(sizeof(struct node));
        tmp->info=data;
        p=start;
        while(p->link!=NULL)
                p=p->link;
        p->link=tmp;
        tmp->link=NULL;
        return start;
}
