#include "stdio.h"
#include "stdlib.h"

typedef struct node {
	int data;
	struct node* next;
} Node;

void printList(Node* head);
void prependList(Node* head);
void apentList(Node* head);
Node* createNode(int data);

/** HOMEWORK
 * 1. Integrate the createNode function where necessary
 * 2. Split the different list operations into seperate functions
 * 3. Read and print integers from a file like so:
 * 		1 2 3 -5 -6
 */

int main()
{
	/*0x11111*/
	Node *n1,*n2,*n3;
	n1 = createNode(10);
	n2 = createNode(5);
	n3 = createNode(8);
	n1->next = n2;
	n2->next = n3;
	n3->next = NULL;
	Node* head = n1;

	printList(head);	

	printf("\n");
	

	
	
	prependList(head);
	printf("\n");
	

	
	
	
	apentList(head);
	
	
	
	
	


	return 0;
}

void printList(Node* head)
{
	/* List traversal (prospelasi listas) */
	Node* temp = head;
	while (temp != NULL)
	{
		printf("%d  ", temp->data);
		temp = temp->next;
	}
}
void prependList(Node* head){
	int newVal;
	
	scanf("%d", &newVal);

	/*Prepend to list*/
	Node* newNode = (Node*) malloc(sizeof(Node));
	
	
	newNode->data = newVal;
	newNode->next = head;
	head = newNode;
	printList(head);
	
}
void apentList(Node* head){
	/* Append to list */
	int newVal;
	printf("\n");
	scanf("%d", &newVal);
	Node* newNode = (Node*) malloc(sizeof(Node));
	
	newNode->data = newVal;
	Node* temp = head;
	while (temp->next != NULL)
	{
		temp = temp->next;
	}
	temp->next = newNode;
	newNode->next = NULL;

	printList(head);
}

Node* createNode(int data)
{
	Node* newNode = NULL;
	newNode = (Node*) malloc(sizeof(Node));
	newNode->data = data;
	return newNode;
}
