****Progarms****<br>
****1.Linkedlist program for inserting****<br>
#include <iostream><br>
using namespace std;<br>
struct Node <br>
{<br>
   int data;<br>
   struct Node *next;<br>
};<br>
struct Node* head = NULL;<br>
void insert(int newdata) <br>
{<br>
   struct Node *newnode = (struct Node *)malloc(sizeof(struct Node));<br>
   struct Node *ptr = head;<br>
   newnode->data = newdata;<br>
   newnode->next = head;<br>
   if (head!= NULL) <br>
   {<br>
      while (ptr->next != head)<br>
      ptr = ptr->next;<br>
      ptr->next = newnode;<br>
   } <br>
  else<br>
   newnode->next = newnode;<br>
   head = newnode;<br>
}<br>
void display() <br>
{<br>
   struct Node* ptr;<br>
   ptr = head;<br>
   do {<br>
      cout<<ptr->data <<" ";<br>
      ptr = ptr->next;<br>
   } while(ptr != head);<br>
}<br>
int main() <br>
{<br>

   insert(3);<br>
   insert(1);<br>
   insert(7);<br>
   insert(2);<br>
   insert(9);<br>
   cout<<"The circular linked list is: ";<br>
   display();<br>
   return 0;<br>
}
  <br>
  ****Output:-****<br>
  The circular linked list is: 9 2 7 1 3 
  <br>
  <br>
****2.Linkedlist program for queue****<br>
#include <iostream><br>
using namespace std;<br>
struct node {<br>
   int data;<br>
   struct node *next;<br>
};<br>
struct node* front = NULL;<br>
struct node* rear = NULL;<br>
struct node* temp;<br>
void Insert() {<br>
   int val;<br>
   cout<<"Insert the element in queue : "<<endl;<br>
   cin>>val;<br>
   if (rear == NULL) {<br>
      rear = (struct node *)malloc(sizeof(struct node));<br>
      rear->next = NULL;<br>
      rear->data = val;<br>
      front = rear;<br>
   } else {<br>
      temp=(struct node *)malloc(sizeof(struct node));<br>
      rear->next = temp;<br>
      temp->data = val;<br>
      temp->next = NULL;<br>
      rear = temp;<br>
   }<br>
}<br>
void Delete() {<br>
   temp = front;<br>
   if (front == NULL) {<br>
      cout<<"Underflow"<<endl;<br>
      return;<br>
   }<br>
   else<br>
   if (temp->next != NULL) {<br>
      temp = temp->next;<br>
      cout<<"Element deleted from queue is : "<<front->data<<endl;<br>
      free(front);<br>
      front = temp;<br>
   } else {<br>
      cout<<"Element deleted from queue is : "<<front->data<<endl;<br>
      free(front);<br>
      front = NULL;<br>
      rear = NULL;<br>
   }<br>
}<br>
void Display() {<br>
   temp = front;<br>
   if ((front == NULL) && (rear == NULL)) {<br>
      cout<<"Queue is empty"<<endl;<br>
      return;<br>
   }<br>
   cout<<"Queue elements are: ";<br>
   while (temp != NULL) {<br>
      cout<<temp->data<<"";<br>
      temp = temp->next;<br>
   }<br>
   cout<<endl;<br>
}<br>
int main() {<br>
   int ch;<br>
   cout<<"1) Insert element to queue"<<endl;<br>
   cout<<"2) Delete element from queue"<<endl;<br>
   cout<<"3) Display all the elements of queue"<<endl;<br>
   cout<<"4) Exit"<<endl;<br>
   do {<br>
      cout<<"Enter your choice : "<<endl;<br>
      cin>>ch;<br>
      switch (ch) {<br>
         case 1: Insert();<br>
         break;<br>
         case 2: Delete();<br>
         break;<br>
         case 3: Display();<br>
         break;<br>
         case 4: cout<<"Exit"<<endl;<br>
         break;<br>
         default: cout<<"Invalid choice"<<endl;<br>
      }<br>
   } while(ch!=4);<br>
   return 0;<br>
}<br>
****Output:-****<br>
  1) Insert element to queue<br>
2) Delete element from queue<br>
3) Display all the elements of queue<br>
4) Exit<br>
Enter your choice : <br>
1<br>
Insert the element in queue : <br>
3<br>
Enter your choice : <br>
1<br>
Insert the element in queue : <br>
5<br>
Enter your choice : <br>
1<br>
Insert the element in queue : <br>
7<br>
Enter your choice : <br>
1<br>
Insert the element in queue : <br>
9<br>
Enter your choice : <br>
 3<br>
Queue elements are: 3 5 7 9 <br>
Enter your choice : <br>
2<br>
Element deleted from queue is : 3<br>
Enter your choice : <br>
3<br>
Queue elements are: 5 7 9 <br>
Enter your choice : <br>
2<br>
Element deleted from queue is : <br>
  5<br>
Enter your choice : <br>
3<br>
Queue elements are: 7 9 <br>
Enter your choice : <br>
4<br>
Exit<br>


  
    
