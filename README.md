# linked-list
```c
#include <stdio.h>
#include <stdlib.h>

struct _Node{
	int data;
	struct _Node *link;
};

typedef struct _Node Node;

// create and return address
Node *getnode(){
	Node *address;

	// create address
	address = (Node*) malloc(sizeof(Node));

	// return address
	return address;
}

// create 
Node *create(int size){
	Node *ptr;
	Node *new;
	Node *prev;
	int data;

	// get address
	ptr = getnode();
	new = ptr;
	
	for(int index; index<size; index++){
		// get new initial address

		// store data new
		printf("Data: ");
		scanf("%d", &data);
		new->data = data;

		// old to new address
		prev = new;

		// get new address
		new = getnode();

		prev->link = new;
	}

	// last data link value NULL
	prev->link = 0;
	return ptr;
}

// delete node 
Node *delete(Node *p){
	printf("Deleted Address %p, value %d\n", p, p->data);
	p->data = '\0';
	p = p->link;
	return p;
}

void print(Node *p){
	Node *current;

	// address store new struct
	current = p;

	while(current != 0){
		printf("Current Address %p, Value %d, Next Address %p\n", current, current->data, current->link);
		current = current -> link;
	}

}

int main(){
	Node *n;
	n = create(6);
	
	printf("\n");
	print(n);

	printf("\n");
	n = delete(n);
	n = delete(n);
	n = delete(n);
	printf("\n");
	print(n);

	return 0;
}
```
