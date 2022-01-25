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
      cout<<temp->data<<" ";<br>
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
****3.Stack using linkedlist****<br>
   #include <iostream><br>
using namespace std;<br>
struct Node {<br>
   int data;<br>
   struct Node *next;<br>
};<br>
struct Node* top = NULL;<br>
void push(int val) {<br>
   struct Node* newnode = (struct Node*) malloc(sizeof(struct Node));<br>
   newnode->data = val;<br>
   newnode->next = top;<br>
   top = newnode;<br>
}<br>
void pop() {<br>
   if(top==NULL)<br>
   cout<<"Stack Underflow"<<endl;<br>
   else {<br>
      cout<<"The popped element is "<< top->data <<endl;<br>
      top = top->next;<br>
   }<br>
}<br>
void display() {<br>
   struct Node* ptr;<br>
   if(top==NULL)<br>
   cout<<"stack is empty";<br>
   else {<br>
      ptr = top;<br>
      cout<<"Stack elements are: ";<br>
      while (ptr != NULL) {<br>
         cout<< ptr->data <<" ";<br>
         ptr = ptr->next;<br>
      }<br>
      }<br>
      }<br>
      }<br>
      }<br>
   cout<<endl;<br>
      }<br>
}<br>
int main() {<br>
   int ch, val;<br>
   cout<<"1) Push in stack"<<endl;<br>
   cout<<"2) Pop from stack"<<endl;<br>
   cout<<"3) Display stack"<<endl;<br>
   cout<<"4) Exit"<<endl;<br>
   do {<br>
      cout<<"Enter choice: "<<endl;<br>
      cin>>ch;<br>
      switch(ch) {<br>
         case 1: {<br>
            cout<<"Enter value to be pushed:"<<endl;<br>
            cin>>val;<br>
            push(val);<br>
            break;<br>
         }<br>
         case 2: {<br>
            pop();<br>
            break;<br>
         }<br>
         case 3: {<br>
            display();<br>
            break;<br>
         }<br>
         case 4: {<br>
            cout<<"Exit"<<endl;<br>
            break;<br>
         }<br>
         default: {<br>
            cout<<"Invalid Choice"<<endl;<br>
         }<br>
      }<br>
   }while(ch!=4);<br>
   return 0;<br>
}<br>
<br>
**Output:-**<br>
 1) Push in stack<br>
2) Pop from stack<br>
3) Display stack<br>
4) Exit<br>
Enter choice: <br>
1<br>
Enter value to be pushed:<br>
2<br>
Enter choice: <br>
1<br>
Enter value to be pushed:<br>
4<br>
Enter choice: <br>
1<br>
Enter value to be pushed:<br>
6<br>
Enter choice: <br>
2<br>
The popped element is 6<br>
Enter choice: <br>
3<br>
Stack elements are: 4 2 <br>
Enter choice: <br>
4<br>
Exit<br>
<br>
<br>
 **4.Adding a 10 numbers using for loop**<br>
   #include <iostream> <br>
 using namespace std; <br>
 
int main() <br>
{ <br>
    int i,arr[10],sum=0; <br>
 
    cout<<"Enter 10 elements:"; <br>
    for(i=0;i<10;++i) <br>
        cin>>arr[i]; <br>
 
    for(i=0;i<10;++i) <br>
        sum=sum+arr[i]; <br>
    cout<<"Sum of numbers is:"<<sum; <br>
 
    return 0; <br>
} <br>
<br>
<br>
 **Output:-**<br>
  Enter 10 elements:1<br>
2<br>
3<br>
4<br>
6<br>
5<br>
7<br>
9<br>
8<br>
2<br>
Sum of numbers is:47<br>
<br>
 **5.Adding a positive number using while loop**<br>
 #include <iostream><br>
using namespace std;<br>
int main() {<br>
    int number;<br>
    int sum = 0;<br>
    cout << "Enter a number: ";<br>
    cin >> number;<br>

    while (number >= 0) {<br>
        sum += number;<br>
        cout << "Enter a number: ";<br>
        cin >> number;<br>
    }<br>
    cout << "\nThe sum is " << sum << endl;<br>
    return 0;<br>
}<br>
<br>
  **Output:-**<br>
 <br>
Enter a number: 0<br>
Enter a number: 6<br>
Enter a number: 9<br>
Enter a number: 13<br>
Enter a number: -25<br>
The sum is 28<br>
<br>
<br>
**6.Do while loop for adding number not equal to zero**<br>
#include <iostream><br>
using namespace std;<br>
int main()<br>
{<br>
	int num, sum = 0;<br>
	do {<br>
   cout << "Enter a number: ";<br>
   cin >> num;<br>
   sum += num;<br>
   } while (num != 0);<br>
	cout << "Sum is " << sum;<br>
   return 0;<br>
}<br>
<br>
**output:-**<br>
Enter a number: 1<br>
Enter a number: 3<br>
Enter a number: -4<br>
Enter a number: 2<br>
Enter a number: 0<br>
Sum is 2<br>
<br>
7. binary search<br>
	#include <iostream> 
 
using namespace std; 
 
int main() 
{ 
    int i,arr[10],sum1=0,sum2=0,sum3=0,n; 
     char ch;
    do{
 	 cout<<"ENTER CHOICE\n"<<"1.For\n"<<"2.While\n"<<"3.Do While\n";
    cout<<"Make a choice: ";
    cin>>n;
     
    switch(n)
    {
        case 1:  
        	cout<<"Enter 10 elements:\n"; 
    for(i=0;i<10;++i) 
      cin>>arr[i]; 
	  for(i=0;i<10;++i) 
        sum1=sum1+arr[i]; 
    
    cout<<"Sum of numbers is:"<<sum1; 
 
            
            break;
         
        case 2 : 
        	cout<<"Enter 10 elements:\n"; 
        i=0;
        while(i<10)
        {
        	cin>>arr[i];
        	i++;
		}
		i=0;
		while(i<10) 
		{
			sum2=sum2+arr[i];
			i++; 
		}
        cout<<"Sum of numbers is:"<<sum2; 
            
            break;
         
        case 3 : 
        cout<<"Enter 10 elements:\n"; 
        i=0;
        do{
        		cin>>arr[i];
        		i++;
		}while(i<10);
        
         i=0;
        do{
        		sum3=sum3+arr[i];
        		i++;
		}while(i<10);
		 cout<<"Sum of numbers is:"<<sum3; 
            break;
             
        default : 
            cout<<"Invalid Choice\n";
    }
     
    cout<<"\nDo you want to continue ? : ";
    cin>>ch;
 
    }while(ch=='Y'||ch=='y');
     
    return 0;
}<br>
<br>
output:-
<br>
ENTER CHOICE
1.For
2.While
3.Do While
Make a choice: 1
Enter 10 elements:
1
2

3
4
4
5
6
7
8
9
Sum of numbers is:49
Do you want to continue ? : y
ENTER CHOICE
1.For
2.While
3.Do While
Make a choice: 2
Enter 10 elements:
2
1
3
4
5
6
7
8
9
5
Sum of numbers is:50
Do you want to continue ? : y
ENTER CHOICE
1.For
2.While
3.Do While
Make a choice: 3
Enter 10 elements:
2
3
1
4
5
6
7
8
9
1
Sum of numbers is:46
Do you want to continue ? : \n

	


   
   
 
   
   

   
   
   
   

  
    
