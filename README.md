# Data-Structure<br>
**1.Write a C++ program to implement a single linked list **<br>
#include<iostream> <br>
#include<cstdlib> <br>
using namespace std; <br><br>
struct node 
{ <br>
 int info; <br>
 struct node *next; <br>
}*start; <br>
class single_llist <br>
{ <br>
 public: <br>
 node* create_node(int); <br>
 void insert_begin(); <br>
 void insert_last(); <br>
 void insert_pos(); <br>
 void delete_begin(); <br>
 void delete_last(); <br>
 void delete_pos(); <br>
 void update_begin(); <br>
 void update_last(); <br>
 void update_pos(); <br>
 void sort(); <br>
 void reverse(); <br>
 void search(); <br>
 void display(); <br>
 single_llist() <br>
 { <br>
 start = NULL; <br>
 } <br>
}; <br>
int main() <br>
{ <br>
 int choice; <br>
 single_llist sl,s2; <br>
 start = NULL; <br>
 do <br>
 { <br>
 cout<<"---------------------------------"<<endl; <br>
 cout<<"Operations on singly linked list"<<endl; <br>
 cout<<"---------------------------------"<<endl; <br>
 cout<<"1.Insert at first"<<endl; <br>
 cout<<"2.Insert at last"<<endl; <br>
 cout<<"3.Insert at position"<<endl; <br>
 cout<<"4.Delete at first"<<endl; <br>
 cout<<"5.Delete at Last"<<endl; <br>
 cout<<"6.Delete at position"<<endl; <br>
 cout<<"7.Update at first"<<endl; <br>
 cout<<"8.Update at last"<<endl; <br>
 cout<<"9.Update at position"<<endl; <br>
 cout<<"10.Ascending order"<<endl; <br>
 cout<<"11.Descending order"<<endl; <br>
 cout<<"12.Search"<<endl; <br>
 cout<<"13.Display"<<endl; <br>
 cout<<"14.Exit "<<endl;<br> 
 cout<<"Enter your choice :"; <br>
 cin>>choice; <br>
 switch(choice) <br>
 { <br>
 case 1: sl.insert_begin(); <br>
 sl.display(); <br>
 break; <br>
 case 2: sl.insert_last(); <br>
 sl.display(); <br>
 break; <br>
 case 3: sl.insert_pos(); <br>
 sl.display(); <br>
 break; <br>
 case 4: s2.delete_begin(); <br>
 sl.display(); <br>
 break; <br>
 case 5: s2.delete_last(); <br>
 sl.display(); <br>
 break; <br>
 case 6: sl.delete_pos(); <br>
 sl.display(); <br>
 break; <br>
 case 7: sl.update_begin(); <br>
 sl.display(); <br>
 break; <br>
 case 8: sl.update_last(); <br>
 sl.display(); <br>
 break; <br>
 case 9: sl.update_pos(); <br>
 sl.display(); <br>
 break; <br>
 case 10:sl.sort(); <br>
 sl.display(); <br>
 break; <br>
 case 11:sl.reverse();<br> 
 sl.display();<br> 
 break; <br>
 case 12:sl.search();<br> 
 sl.display();<br>
 break; <br>
 case 13:sl.display(); <br>
 break; <br>
 case 14:exit(0); <br>
 break; <br>
 default:cout<<"Wrong choice...???"<<endl; <br>
 break; <br>
 } <br>
 } <br>
 while(choice != 14); <br>
} <br>
node *single_llist::create_node(int value) <br>
{ <br>
 struct node *temp, *s; <br>
 temp = new(struct node); <br>
 if (temp == NULL) <br>
 { <br>
 cout<<"Memory not allocated"<<endl; <br>
 return 0; <br>
 } <br>
 else <br>
 { <br>
 temp->info = value; <br>
 temp->next = NULL; <br>
 return temp; <br>
 } <br>
} <br>
void single_llist::insert_begin() <br>
{ <br>
 int value; <br>
 cout<<"Enter the value to be inserted : "; <br>
 cin>>value; <br>
 struct node *temp, *s; <br>
 temp = create_node(value); <br>
 if (start == NULL) <br>
 { <br>
 start = temp; <br>
 start->next = NULL; <br>
 cout<<temp->info<<" is inserted at first in the empty list"<<endl; <br>
 } <br>
 else <br>
 { <br>
 s = start; <br>
 start = temp; <br>
 start->next = s; <br>
 cout<<temp->info<<" is inserted at first"<<endl; <br>
 } <br>
} <br>
void single_llist::insert_last() <br>
{ <br>
 int value; <br>
 cout<<"Enter the value to be inserted : "; <br>
 cin>>value; <br>
 struct node *temp, *s; <br><br>
 temp = create_node(value); <br>
 if (start == NULL) <br>
 { <br>
 start = temp; <br>
 start->next = NULL; <br>
 cout<<temp->info<<" is inserted at last in the empty list"<<endl; <br>
 } <br>
 else <br>
 { <br>
 s = start; <br>
 while (s->next != NULL) <br>
 { <br>
 s = s->next; <br>
 } <br>
 temp->next = NULL; <br>
 s->next = temp; <br>
 cout<<temp->info<<" is inserted at last"<<endl; <br>
 } <br>
} <br>
void single_llist::insert_pos() <br>
{ <br>
 int value, pos, counter = 0, loc = 1; <br>
 struct node *temp, *s, *ptr; <br>
 s = start; <br>
 while (s != NULL) <br>
{<br>
 s = s->next; <br>
 counter++; <br>
 } <br>
 if(counter == 0)<br>
 { } <br>
 else <br>
 { <br>
 cout<<"Enter the postion from "<<loc<<" to "<<counter+1<<" : "; <br>
 cin>>pos; <br>
 s = start;<br> 
 if(pos == 1)<br> 
 { <br>
 cout<<"Enter the value to be inserted : ";<br> 
 cin>>value; <br>
 temp = create_node(value); <br>
 start = temp;<br> 
 start->next = s;<br>
 cout<<temp->info<<" is inserted at first"<<endl; <br>
 } <br>
 else if (pos > 1 && pos <= counter) <br>
 { <br>
 cout<<"Enter the value to be inserted : "; <br>
 cin>>value; <br>
 temp = create_node(value);<br> 
 for (int i = 1; i < pos; i++) <br>
 { <br>
 ptr = s;<br> 
 s = s->next; <br>
 } <br>
 ptr->next = temp;<br> 
 temp->next = s; <br>
 cout<<temp->info<<" is inserted at position "<<pos<<endl; <br>
 } <br>
 else if (pos == counter+1)<br> 
 { <br>
 cout<<"Enter the value to be inserted : "; <br>
 cin>>value; <br>
 temp = create_node(value); <br>
 while (s->next != NULL) <br>
 { <br>
 s = s->next; <br>
 } <br>
 temp->next = NULL; <br>
 s->next = temp; <br>
 cout<<temp->info<<" is inserted at last"<<endl; <br>
 } <br>
 else<br> 
 { <br>
 cout<<"Positon out of range...!!!"<<endl; <br>
 } <br>
 } <br>
} <br>
void single_llist::delete_begin() <br>
{ <br>
 if (start == NULL){} <br>
 else <br>
 { <br>
 struct node *s, *ptr; <br>
 s = start; <br>
 start = s->next; <br>
 cout<<s->info<<" deleted from first"<<endl; <br>
 free(s); <br>
 } <br>
} <br>
void single_llist::delete_last() <br>
{ <br>
 int i, counter = 0; <br>
 struct node *s, *ptr;<br> 
 if (start == NULL){} <br>
 else <br>
 { <br>
 s = start; <br>
 while (s != NULL) <br>
 { <br>
 s = s->next; <br>
 counter++; <br>
 } <br>
 s = start;<br> 
 if (counter == 1) <br>
 { <br>
 start = s->next; <br>
 cout<<s->info<<" deleted from last"<<endl; <br>
 free(s); <br>
 } <br>
 else <br>
 { <br>
 for (i = 1;i < counter;i++) <br>
 { <br>
 ptr = s; <br>
 s = s->next; <br>
 } <br>
 ptr->next = s->next; <br>
 cout<<s->info<<" deleted from last"<<endl; <br>
 free(s); <br>
 } <br>
 } <br>
} <br>
void single_llist::delete_pos() <br>
{ <br>
 int pos, i, counter = 0, loc = 1; <br>
 struct node *s, *ptr; <br>
 s = start;<br> 
 while (s != NULL) <br>
 { <br>
 s = s->next; <br>
 counter++; <br>
 } <br>
 if (counter == 0){} <br>
 else <br>
 { <br>
 if (counter == 1) <br>
 { <br>
 cout<<"Enter the postion [ SAY "<<loc<<" ] : "; <br>
 cin>>pos; <br>
 s = start; <br>
 if (pos == 1) <br>
 { <br>
 start = s->next;<br> 
 cout<<s->info<<" deleted from first"<<endl; <br>
 free(s); <br>
 } <br>
 else <br>
 cout<<"Position out of range...!!!"<<endl; <br>
 } <br>
 else <br>
 { <br>
 cout<<"Enter the postion from "<<loc<<" to "<<counter<<" : "; <br>
 cin>>pos; <br>
 s = start;<br> 
 if (pos == 1) <br>
 { <br>
 start = s->next; <br>
 cout<<s->info<<" deleted from first"<<endl; <br>
 free(s); <br>
 } <br>
 else if (pos > 1 && pos <= counter) <br>
 { <br>
 for (i = 1;i < pos;i++) <br>
 { <br>
 ptr = s; <br>
 s = s->next; <br>
 } <br>
 ptr->next = s->next; <br>
 if(pos == counter) <br>
 {<br>
 cout<<s->info<<"deleted from last<<endl;<br>
 free(s);} <br>
 else <br>
 {cout<<s->info<<" deleted from postion "<<pos<<endl; <br>
 free(s);} <br>
 } <br>
 else <br>
 cout<<"Position out of range...!!!"<<endl; <br>
 } <br>
 } <br>
} <br>
void single_llist::update_begin() <br>
{ <br>
 int value, pos=1, i,counter = 0; <br>
 struct node *s, *ptr; <br>
 s = start; <br>
 while (s != NULL) <br>
 { <br>
 s = s->next; <br>
 counter++; <br>
 } <br>
 if (counter == 0){} <br>
 else if (pos == 1) <br>
 { <br>
 cout<<"Enter the new node : "; <br>
 cin>>value; <br>
 start->info = value; <br>
 cout<<"Node updated at first position : "<<pos<<" = "<<start->info<<endl; <br>
 } <br>
} <br>
void single_llist::update_last() <br>
{ <br>
 int value, pos, i,counter = 0; <br>
 struct node *s, *ptr; <br>
 s = start; <br>
 while (s != NULL) <br>
 { <br>
 s = s->next; <br>
 counter++; <br>
 } <br>
 s=start; <br>
 if (counter == 0){} <br>
 else <br>
 { <br>
 cout<<"Enter the new node : "; <br>
 cin>>value; <br>
 for (i = 1; i < counter ; i++) <br>
 { <br>
 s = s->next; <br>
 } <br>
 s->info = value; <br>
 cout<<"Node updated at last position : "<<counter<<" = "<<s->info<<endl; <br>
 } <br>
} <br>
void single_llist::update_pos() <br>
{ <br>
 int value, pos, i,counter = 0, loc = 1; <br>
 struct node *s, *ptr; <br>
 s = start; <br>
 while (s != NULL) <br>
 { <br>
 s = s->next; <br>
 counter++; <br>
 } <br>
 if (counter == 0){} <br>
 else <br>
 { <br>
 if (counter == 1) <br>
 { <br>
 cout<<"Enter the postion [ SAY "<<loc<<" ] : ";<br> 
 cin>>pos; <br>
 s = start; <br>
 if (pos == 1) <br>
 { <br>
 cout<<"Enter the new node : "; <br>
 cin>>value; <br>
 start->info = value; <br>
 cout<<"Node updated at position : "<<pos<<" = "<<start->info<<endl; <br>
 } <br>
 else <br>
 cout<<"Position out of range...!!!"<<endl; <br>
 } <br>
 else <br>
 { <br>
 cout<<"Enter the postion from "<<loc<<" to "<<counter<<" : "; <br>
 cin>>pos; <br>
 s = start; <br>
 if (pos == 1) <br>
 { <br>
 cout<<"Enter the new node : "; <br>
 cin>>value; <br>
 start->info = value; <br>
 cout<<"Node updated at position : "<<pos<<" = "<<start->info<<endl; <br>
 } <br>
 else if (pos > 1 && pos <= counter) <br>
 { <br>
 cout<<"Enter the new node : "; <br>
 cin>>value; <br>
 for (i = 1; i < pos ; i++) <br>
 { <br>
 s = s->next; <br>
 } <br>
 s->info = value; <br>
 cout<<"Node updated at position : "<<pos<<" = "<<s->info<<endl; <br>
 } <br>
 else <br>
 cout<<"Position out of range...!!!"<<endl; <br>
 } <br>
 } <br>
} <br>
void single_llist::sort() <br>
{ <br>
 struct node *ptr, *s; <br>
 int value; <br>
 if (start == NULL){} <br>
 else <br>
 { <br>
 ptr = start; <br>
 while (ptr != NULL) <br>
 { <br>
 for (s = ptr->next;s !=NULL;s = s->next) <br>
 { <br>
 if (ptr->info > s->info) <br>
 { <br>
 value = ptr->info; <br>
 ptr->info = s->info; <br>
 s->info = value; <br>
 } <br>
 } <br>
 ptr = ptr->next; <br>
 } <br>
 } <br>
} <br>
void single_llist::reverse() <br>
{ <br>
 struct node *ptr, *s; <br>
 int value; <br>
 if (start == NULL){} <br>
 else <br>
 { <br>
 ptr = start; <br>
 while (ptr != NULL) <br>
 { <br>
 for (s = ptr->next;s !=NULL;s = s->next) <br>
 { <br>
 if (ptr->info < s->info) <br>
 { <br>
 value = ptr->info; <br>
 ptr->info = s->info;<br>
 s->info = value; <br>
 } <br>
 } <br>
 ptr = ptr->next; <br>
 } <br>
 } <br>
} <br>
void single_llist::search() <br>
{ <br>
 int value, loc = 0, pos = 0, counter = 0; <br>
 struct node *s; <br>
 s = start; <br>
 while (s != NULL) <br>
 { <br>
 s = s->next; <br>
 counter++; <br>
 } <br>
 if (start == NULL){} <br>
 else <br>
 { <br>
 cout<<"Enter the value to be searched : "; <br>
 cin>>value; <br>
 struct node *s; <br>
 s = start; <br>
 while (s != NULL) <br>
 { <br>
 pos++; <br>
 if (s->info == value) <br>
 { <br>
 loc++; <br>
 if(loc == 1) <br>
 cout<<"Element "<<value<<" is found at position "<<pos; <br>
 else if(loc <= counter) <br>
 cout<<" , "<<pos; <br>
 } <br>
 s = s->next; <br>
 } <br>
 cout<<endl; <br>
 if (loc == 0) <br>
 cout<<"Element "<<value<<" not found in the list"<<endl; <br>
 } <br>
} <br>
void single_llist::display() <br>
{ <br>
 struct node *temp; <br>
 if (start == NULL) <br>
 cout<<"Linked list is empty...!!!"<<endl; <br>
 else <br>
 { <br>
 cout<<"Linked list contains : "; <br>
 temp = start; <br>
 while (temp != NULL)<br>
 { <br>
 cout<<temp->info<<" "; <br>
 temp = temp->next; <br>
 } <br>
 cout<<endl; <br>
 } <br>
}<br>
**OUTPUT**<br>
![image](https://user-images.githubusercontent.com/97940850/154896268-1322fe75-eec8-4bdb-bd39-a9284a3d21ab.png)<br>
![image](https://user-images.githubusercontent.com/97940850/154896356-d2715411-39ff-4769-bbba-1550a0a34abb.png)<br>
![image](https://user-images.githubusercontent.com/97940850/154896412-04e252ef-4ea2-4969-afe6-d70eb6560d44.png)<br>
![image](https://user-images.githubusercontent.com/97940850/154896460-a8bfc12a-6419-45c5-b70e-0e7d5c386c3a.png)<br>
![image](https://user-images.githubusercontent.com/97940850/154896519-87b5cf4e-ba88-457c-846c-653b7b1d4a1f.png)<br>
![image](https://user-images.githubusercontent.com/97940850/154896573-45ae784c-ec6b-4c1a-8018-41c8713fb98b.png)<br>
![image](https://user-images.githubusercontent.com/97940850/154896650-4ffd5e3f-9752-43fb-924a-d4bf1613073f.png)<br>
![image](https://user-images.githubusercontent.com/97940850/154896708-5b95f103-27e4-4835-9f4f-ce427b1d4d01.png)<br>
![image](https://user-images.githubusercontent.com/97940850/154896779-e4da56c0-61f5-4510-90f9-bbd9a31fd82f.png)<br>

 
 **2.Write a C++ program to split the linked list into two halves such that the element ‘e’ should be the first element of second list. **<br>
 #include<iostream><br>
using namespace std;<br>
struct Node{<br>
int value;<br>
struct Node *next;<br>
};<br>
struct Node* head = NULL;<br>
struct Node* sHead = NULL;<br>
struct Node* temp = NULL;<br>
void insert(int new_data){<br>
struct Node* new_node = new Node(); //(struct Node*)malloc(sizeof(struct Node));<br>
new_node->value = new_data;<br>
new_node->next = head;<br>
head = new_node;<br>
}<br>
int n;<br>
int ele;<br>
int splitIndex;<br>
int main(){<br>
int i;<br>
cout<<"Enter number of elements you want in the list\t";<br>
cin>>n;<br>
cout<<"Enter elements :" <<endl;<br>
for(i=0;i<n;i++){<br>
cin>>ele;<br>
insert(ele);<br>
}<br>
cout<<"\nList of elements : "<<endl;<br>
Node *t;<br>
t = head;<br>
while(t != NULL){<br>
cout<<t->value<<"\t";<br>
t = t->next;<br>
}<br>
cout<<"\n\nEnter the position you want the list to split ";<br>
cin>>splitIndex;<br>
while(splitIndex < 0 || splitIndex > n-1){<br>
cout<<"Invalid position. Try again."<<endl;<br>
cin>>splitIndex;<br>
}<br>
temp = head;<br>
for(i=0;i<=splitIndex;i++){<br>
if(i==splitIndex-1){<br>
Node *tN;<br>
tN = temp->next;<br>
sHead = tN;<br>
temp->next = NULL;<br>
break;<br>
}<br>
temp = temp->next;<br>
}<br>
temp = head;<br>
if(temp == NULL){<br>
cout<<"\nFirst list is empty"<<endl;<br>
}else{<br>
cout<<"\n\nFirst list element "<<endl;<br>
while(temp != NULL){<br>
cout<<temp->value<<"\t";<br>
temp = temp->next;<br>
}<br>
}<br>
temp = sHead;<br>
if(temp == NULL){<br>
cout<<"\nSecond list is empty"<<endl;<br>
}else{<br>
cout<<"\n\nSecond list elements "<<endl;<br>
while(temp != NULL){<br>
cout<<temp->value<<"\t";<br>
temp = temp->next;<br>
}<br>
}<br>
return 0;<br>
}<br>
**OUTPUT**<br>
![image](https://user-images.githubusercontent.com/97940850/154897558-5782c729-8fe7-431b-8983-ed77247066b8.png)<br>

 **3. Write a c++ program to spliting of arrays.**<br>
#include<iostream><br>
using namespace std;<br>
int main()<br>
{<br>
	int a[20],i,n,a1[20],a2[20],k1=0,k2=0,pos;<br>
	cout<<"Enter the size of an array: "<<endl;<br>
	cin>>n;<br>
	cout<<"Enter array elements: "<<endl;<br>
	for(i=0;i<n;i++)<br>
	{<br>
		cin>>a[i];<br>
	}<br>
	cout<<"Enter the position to split the array into 2"<<endl;<br>
	cin>>pos;<br>
	for(i=0;i<n;i++)<br>
	{<br>
		if(i<pos)<br>
		a1[k1++]=a[i];<br>
		else<br>
		a2[k2++]=a[i];<br>
	}<br>
		cout<<"\nArray elements of array1 \n";<br>
			for(i=0;i<k1;i++)<br>
			{<br>
				 
               			 cout<<a1[i]<<endl;<br>
			}<br>
			
			cout<<"\nArray elements of array2 \n";<br>
			for(i=0;i<k2;i++)<br>
			{<br>
				 
             		  cout<<a2[i]<<endl;<br>
			}<br>
		
			cout<<"\n";<br>
			return 0;<br>
		}<br>
			<br>
**OUTPUT**<br>
![image](https://user-images.githubusercontent.com/97940850/164607660-689653b6-02ee-49f2-8278-60fdcd0a937a.png)<br>

<br>	
	
 **4.write a C++ program to implement addition of two arrays **<br>
#include<iostream><br>
using namespace std;<br>
int main()<br>
{<br>
	int size, i, arr1[10], arr2[10], add[10];<br>
	
cout << "\nPlease Enter the Array Size =  ";<br>
cin >> size;<br>
	
cout << "\nPlease Enter the First Array Items =  ";<br>
for(i = 0; i < size; i++)<br>
{<br>
cin >> arr1[i];<br>
}<br>
cout << "\nPlease Enter the Second Array Items =  ";<br>
for(i = 0; i < size; i++)<br>
{<br>
cin >> arr2[i];<br>
}<br>
for(i = 0; i < size; i++)<br>
{<br>
add[i] = arr1[i] + arr2[i];<br>
cout << arr1[i] << " + " << arr2[i] << " = " << add[i] << "\n";<br>
}<br>
cout << "\nThe Final Result of adding 2 One Dimensional Arrays = ";<br>
for(i = 0; i < size; i++)<br>
{<br>
cout << add[i] << " ";<br>
}<br>

 return 0;<br>
}<br>
**OUTPUT**<br>
 ![image](https://user-images.githubusercontent.com/97940850/154901723-e6259951-33e2-4f3f-9d73-23398c59a006.png)<br>
	
**5. Write a c++ program to implement reverse order of the array element.**<br>
#include<iostream><br>
using namespace std;<br>
int main()<br>
{<br>
    int arr[10], i;<br>
    cout<<"Enter 10 Array Elements: ";<br>
    for(i=0; i<10; i++)<br>
        cin>>arr[i];<br>
    cout<<"\nThe Original Array is:\n";<br>
    for(i=0; i<10; i++)<br>
        cout<<arr[i]<<" ";<br>
    cout<<"\n\nThe Reverse of Given Array is:\n";<br>
    for(i=(10-1); i>=0; i--)<br>
        cout<<arr[i]<<" ";<br>
    cout<<endl;<br>
    return 0;<br>
}<br>
**OUTPUT**<br>
![image](https://user-images.githubusercontent.com/97940850/154902782-c9f796fd-b2a5-4e6f-b50b-e082f7ed7da3.png)<br>
	
**6. Write a C++ program stack using array.**<br>
//eg5 Stack using array<br>
#include <iostream><br>
using namespace std;<br>
int stack[100], n=100, top=-1;<br>
void push(int val) {<br>
   if(top>=n-1)<br>
   cout<<"Stack Overflow"<<endl;<br>
   else {<br>
      top++;<br>
      stack[top]=val;<br>
   }<br>
}<br>
void pop() {<br>
   if(top<=-1)<br>
   cout<<"Stack Underflow"<<endl;<br>
   else {<br>
      cout<<"The popped element is "<< stack[top] <<endl;<br>
      top--;<br>
   }<br>
}<br>
void display() {<br>
   if(top>=0) {<br>
      cout<<"Stack elements are:";<br>
      for(int i=top; i>=0; i--)<br>
      cout<<stack[i]<<" ";<br>
      cout<<endl;<br>
   } else<br>
   cout<<"Stack is empty";<br>
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
         case 2: {
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
**OUTPUT**<br>
![image](https://user-images.githubusercontent.com/97940850/154903861-ff79a97d-0112-4351-9911-02ae4959034b.png)<br>

**7. write a C++ program to binary search element**<br>
//eg4 binary search<br>
#include<iostream><br>
using namespace std;<br>
int main()<br>
{<br>
    int i, arr[10], num, first, last, middle;<br>
    cout<<"Enter 10 Elements (in ascending order): ";<br>
    for(i=0; i<10; i++)<br>
        cin>>arr[i];<br>
    cout<<"\nEnter Element to be Search: ";<br>
    cin>>num;<br>
    first = 0;<br>
    last = 9;<br>
    middle = (first+last)/2;<br>
    while(first <= last)<br>
    {<br>
        if(arr[middle]<num)<br>
            first = middle+1;<br>
        else if(arr[middle]==num)<br>
        {<br>
            cout<<"\nThe number, "<<num<<" found at Position "<<middle+1;<br>
            break;<br>
        }<br>
        else<br>
            last = middle-1;<br>
        middle = (first+last)/2;<br>
    }<br>
    if(first>last)<br>
        cout<<"\nThe number, "<<num<<" is not found in given Array";<br>
    cout<<endl;<br>
    return 0;<br>
}	<br>
**OUTPUT**<br>
![image](https://user-images.githubusercontent.com/97940850/154904981-d74c8b7b-0635-43a5-8a11-ce208c6eea2e.png)<br>

**8. Adding 10 numbers using for,while,dowhile. using switch case.**<br>
#include<iostream><br>
using namespace std;<br>
int main()<br>
{<br>
	int ch,val;<br>
	cout<<"1 Adding 10 no. using for"<<endl;<br>
	cout<<"2 Adding 10 no. using While"<<endl;<br>
	cout<<"3 Adding 10 no. using Dowhile"<<endl;<br>
	cout<<"4 Exit"<<endl;<br>
	do{<br>
		cout<<"Enter a choice"<<endl;<br>
		cin>>ch;<br>
		switch(ch)<br>
		{<br>
			case 1:<br>
				{<br>
    			int i, n, num, sum=0;<br>
    			cout<<"How many numbers you want to enter ? ";<br>
    			cin>>n;<br>
   				 cout<<"Enter "<<n<<" numbers: ";<br>
   				 for(i=0; i<n; i++)<br>
    				{<br>
       					 cin>>num;<br>
       					 sum = sum+num;<br>
    				}<br>
   				 cout<<"\nSum of all "<<n<<" numbers is "<<sum;<br>
   			 	cout<<endl;<br>
				break;<br>
				}<br>
				
case 2:<br>
	{<br>
   	 int n, i=0, num, sum=0;<br>
   	 cout<<"Enter the value of n: ";<br>
   	 cin>>n;<br>
   	 cout<<"Enter "<<n<<" numbers: ";<br>
   	 while(i<n)<br>
    	{<br>
       	 cin>>num;<br>
       	sum = sum+num;<br>
        	i++;<br>
    		}<br>
    		cout<<"\nSum = "<<sum;<br>
    		cout<<endl;<br>
    					break;<br>
				}<br>
		
case 3:{<br>
					int	i=0,sum=0,num,n;<br>
   			 		cout<<"enter the value of n: ";<br>
   				 cin>>n;<br>
					cout<<"Enter the 10 numbers: ";<br>
					do<br>
					{<br>
					cin>>num;<br>
					sum=sum+num;<br>
					i++;<br>
					}<br>
					while (i < n);<br>
					cout<<"sum= "<<sum<<endl;<br>
					
break;<br>
}<br>
case 4:{<br>
		cout<<"Exit";<br>
		break;<br>
	}<br>
	default:<br>
	cout<<"Invalid choice"<<endl;<br>
			
}<br>
	}<br>
	while(ch!=4);<br>
	return 0;<br>
	}<br>
**OUTPUT**<br>
![image](https://user-images.githubusercontent.com/97940850/155065823-90d755c2-c517-4e71-8849-012bcdc25b98.png)<br>
					     
**9./* Write a C++ program to implement BST to support the following operations<br>
Assume no duplicate elements while constructing the BST<br>
1.Given a key perform a search in the BST, if the key is found then display "key found"<br>
2.Insert an element into a BST<br>
3.Delete an element from a BST<br>
Display the tree using Inorder,Preorder and Postorder traversal methods*/**<br>
	
# include <iostream> <br>
# include <cstdlib> <br>
using namespace std; <br>
struct node <br>
{ <br>
 int info; <br>
 struct node *left; <br>
 struct node *right; <br>
}*root; <br>
class BST <br>
{ <br>
 public: 
 void find(int, node **, node **); <br>
 void insert(node *, node *); <br>
 void del(int); <br>
 void case_a(node *,node *); <br>
 void case_b(node *,node *); <br>
 void case_c(node *,node *); <br>
 void preorder(node *); <br>
 void inorder(node *); <br>
 void postorder(node *); <br>
 void display(node *, int); <br>
 BST() <br>
 { <br>
 root = NULL; <br>
 } <br>
}; <br>
int main() <br>
{ <br>
 int choice, num; <br>
 BST bst; <br>
 node *temp; <br>
 while (1) <br>
 { <br>
 cout<<"-----------------"<<endl; <br>
 cout<<"Operations on BST"<<endl; <br>
 cout<<"-----------------"<<endl; <br>
 cout<<"1.Insert Element "<<endl; <br>
 cout<<"2.Delete Element "<<endl; <br>
 cout<<"3.Inorder Traversal"<<endl; <br>
 cout<<"4.Preorder Traversal"<<endl; <br>
 cout<<"5.Postorder Traversal"<<endl; <br>
 cout<<"6.Display"<<endl; <br>
 cout<<"7.Quit"<<endl; <br>
 cout<<"Enter your choice : "; <br>
 cin>>choice; <br>
 switch(choice) <br>
 { <br>
 case 1: <br>
 temp = new node; <br>
 cout<<"Enter the number to be inserted : "; <br>
 cin>>temp->info; <br>
 bst.insert(root, temp); <br>
 break; <br>
 case 2: <br>
 if (root == NULL) <br>
 { <br>
 cout<<"Tree is empty, nothing to delete"<<endl; <br>
 continue; <br>
 } <br>
 cout<<"Enter the number to be deleted : "; <br>
 cin>>num; <br>
 bst.del(num); <br>
 break; <br>
 case 3: <br>
 cout<<"Inorder Traversal of BST:"<<endl; <br>
 bst.inorder(root); <br>
 cout<<endl; <br>
 break; <br>
 case 4: <br>
 cout<<"Preorder Traversal of BST:"<<endl; <br>
 bst.preorder(root); <br>
 cout<<endl; <br>
 break; <br>
 case 5: <br>
 cout<<"Postorder Traversal of BST:"<<endl; <br>
 bst.postorder(root); <br>
 cout<<endl; <br>
 break; <br>
 case 6: <br>
 cout<<"Display BST:"<<endl; <br>
 bst.display(root,1); <br>
 cout<<endl; <br>
 break; <br>
 case 7: <br>
 exit(1); <br>
 default: <br>
 cout<<"Wrong choice"<<endl; <br>
 } <br>
 } <br>
} <br>
void BST::find(int item, node **par, node **loc) <br>
{ <br>
 node *ptr, *ptrsave; <br>
 if (root == NULL) <br>
 { <br>
 *loc = NULL; <br>
 *par = NULL; <br>
 return; <br>
 } <br>
 if (item == root->info) <br>
 { <br>
 *loc = root; <br>
 *par = NULL; <br>
 return; <br>
 } <br>
 if (item < root->info) <br>
 ptr = root->left; <br>
 else <br>
 ptr = root->right; <br>
 ptrsave = root; <br>
 while (ptr != NULL) <br>
 { <br>
 if (item == ptr->info) <br>
 { <br>
 *loc = ptr; <br>
 *par = ptrsave; <br>
 return; <br>
 } <br>
 ptrsave = ptr; <br>
 if (item < ptr->info) <br>
 ptr = ptr->left; <br>
 else <br>
 ptr = ptr->right; <br>
 } <br>
 *loc = NULL; <br>
 *par = ptrsave; <br>
} <br>

void BST::insert(node *tree, node *newnode) <br>
{ <br>
 if (root == NULL) <br>
 { <br>
 root = new node; <br>
 root->info = newnode->info; <br>
 root->left = NULL; <br>
 root->right = NULL; <br>
 cout<<"Root Node is Added"<<endl; <br>
 return; <br>
 } <br>
 if (tree->info == newnode->info) <br>
 { <br>
 cout<<"Element already in the tree"<<endl; <br>
 return; <br>
 } <br>
 if (tree->info > newnode->info) <br>
 { <br>
 if (tree->left != NULL) <br>
 { <br>
 insert(tree->left, newnode); <br>
 } <br>
 else <br>
 { <br>
 tree->left = newnode; <br>
 (tree->left)->left = NULL; <br>
 (tree->left)->right = NULL; <br>
 cout<<"Node Added To Left"<<endl; <br>
 return; <br>
 } <br>
 } <br>
 else <br>
 { <br>
 if (tree->right != NULL) <br>
 { <br>
 insert(tree->right, newnode); <br>
 } <br>
 else <br>
 { <br>
 tree->right = newnode; <br>
 (tree->right)->left = NULL; <br>
 (tree->right)->right = NULL; <br>
 cout<<"Node Added To Right"<<endl; <br>
 return; <br>
 } <br>
 } <br>
} <br>

void BST::del(int item) <br>
{ <br>
 node *parent, *location; <br>
 if (root == NULL) <br>
 { <br>
 cout<<"Tree empty"<<endl; <br>
 return; <br>
 } <br>
 find(item, &parent, &location); <br>
 if (location == NULL) <br>
 { <br>
 cout<<"Item not present in tree"<<endl; <br>
 return; <br>
 } <br>
 if (location->left == NULL && location->right == NULL) <br>
 case_a(parent, location); <br>
 if (location->left != NULL && location->right == NULL) <br>
 case_b(parent, location); <br>
 if (location->left == NULL && location->right != NULL) <br>
 case_b(parent, location); <br>
 if (location->left != NULL && location->right != NULL) <br>
 case_c(parent, location); <br>
 free(location); <br>
} <br>
 

void BST::case_a(node *par, node *loc ) <br>
{ <br>
 if (par == NULL) <br>
 { <br>
 root = NULL; <br>
 } <br>
 else <br>
 { <br>
 if (loc == par->left) <br>
 par->left = NULL; <br>
 else <br>
 par->right = NULL; <br>
 } <br>
} <br>
 

void BST::case_b(node *par, node *loc) <br>
{ <br>
 node *child; <br>
 if (loc->left != NULL) <br>
 child = loc->left; <br>
 else <br>
 child = loc->right; <br>
 if (par == NULL) <br>
 { <br>
 root = child; <br>
 } <br>
 else <br>
 { <br>
 if (loc == par->left) <br>
 par->left = child; <br>
 else <br>
 par->right = child; <br>
 } <br>
} <br>
 

void BST::case_c(node *par, node *loc) <br>
{ <br>
 node *ptr, *ptrsave, *suc, *parsuc; <br>
 ptrsave = loc; <br>
 ptr = loc->right; <br>
 while (ptr->left != NULL) <br>
 { <br>
 ptrsave = ptr; <br>
 ptr = ptr->left; <br>
 } <br>
 suc = ptr; <br>
 parsuc = ptrsave; <br>
 if (suc->left == NULL && suc->right == NULL) <br>
 case_a(parsuc, suc); <br>
 else<br>
case_b(parsuc,suc);<br>
 if (par == NULL) <br>
 { <br>
 root = suc; <br>
 } <br>
 else <br>
 { <br>
 if (loc == par->left) <br>
 par->left = suc; <br>
 else <br>
 par->right = suc; <br>
 } <br>
 suc->left = loc->left; <br>
 suc->right = loc->right; <br>
} <br>
 
 
void BST::preorder(node *ptr) <br>
{ <br>
 if (root == NULL) <br>
 { <br>
 cout<<"Tree is empty"<<endl; <br>
 return; <br>
 } <br>
 if (ptr != NULL) <br>
 { <br>
 cout<<ptr->info<<" "; <br>
 preorder(ptr->left); <br>
 preorder(ptr->right); <br>
 } <br>
} <br>

void BST::inorder(node *ptr) <br>
{ <br>
 if (root == NULL) <br>
 { <br>
 cout<<"Tree is empty"<<endl; <br>
 return; <br>
 } <br>
 if (ptr != NULL) <br>
 { <br>
 inorder(ptr->left); <br>
 cout<<ptr->info<<" "; <br>
 inorder(ptr->right); <br>
 } <br>
} <br>
 
void BST::postorder(node *ptr) <br>
{ <br>
 if (root == NULL) <br>
 { <br>
 cout<<"Tree is empty"<<endl; <br>
 return; <br>
 } <br>
 if (ptr != NULL) <br>
 { <br>
 postorder(ptr->left); <br>
 postorder(ptr->right); <br>
 cout<<ptr->info<<" "; <br>
 } <br>
} <br>
 
void BST::display(node *ptr, int level) <br>
{ <br>
 int i; <br>
 if (ptr != NULL) <br>
 { <br>
 display(ptr->right, level+1); <br>
 cout<<endl; <br>
 if (ptr == root) <br>
 cout<<"Root->: "; <br>
 else <br>
 { <br>
 for (i = 0;i < level;i++) <br>
 cout<<" "; <br>
 } <br>
 cout<<ptr->info; <br>
 display(ptr->left, level+1);<br> 
 } <br>
}<br>
**OUTPUT**<br>
![image](https://user-images.githubusercontent.com/97940850/155076861-0a7ac5bd-93a1-45bf-82fb-6a85e04e323a.png)<br>
![image](https://user-images.githubusercontent.com/97940850/155077112-a0a643b1-1c0a-4c3d-a49d-db565e4f5763.png)<br>
![image](https://user-images.githubusercontent.com/97940850/155077212-18bfce06-978d-41e0-b16b-5bb3026c9632.png)<br>

**10. //Write a C++ program to implement minimum heap.**<br>
//Write a C++ program to implement minimum heap.<br>
#include <iostream><br>
#include <conio.h><br>
using namespace std;<br>
void min_heap(int *a, int m, int n){<br>
   int j, t;<br>
   t= a[m];<br>
   j = 2 * m;<br>
   while (j <= n) {<br>
      if (j < n && a[j+1] < a[j])<br>
         j = j + 1;<br>
      if (t < a[j])<br>
         break;<br>
      else if (t >= a[j]) {<br>
         a[j/2] = a[j];<br>
         j = 2 * j;<br>
      }<br>
   }<br>
   a[j/2] = t;<br>
   return;<br>
}<br>
void build_minheap(int *a, int n) {<br>
   int k;<br>
   for(k = n/2; k >= 1; k--) {<br>
      min_heap(a,k,n);<br>
   }<br>
}<br>
int main() <br>
{<br>
   int n, i;<br>
   cout<<"enter no of elements of array\n";<br>
   cin>>n;<br>
   int a[30];<br>
   for (i = 1; i <= n; i++) {<br>
      cout<<"enter element"<<" "<<(i)<<endl;<br>
      cin>>a[i];<br>
   }<br>
   build_minheap(a, n);<br>
   cout<<"Min Heap\n";<br>
   for (i = 1; i <= n; i++) {<br>
      cout<<a[i]<<endl;<br>
   }<br>
   getch();<br>
}<br>
**OUTPUT**<br>
![image](https://user-images.githubusercontent.com/97940850/155930803-c5d4e853-4f8b-4e89-adb4-7c27b56b5179.png)<br>
	       
**11.//Write a C++ program to implement maximum heap.**<br>
#include <iostream><br>
using namespace std;<br>
void max_heap(int *a, int m, int n) {<br>
   int j, t;<br>
   t = a[m];<br>
   j = 2 * m;<br>
   while (j <= n) {<br>
      if (j < n && a[j+1] > a[j])<br>
         j = j + 1;<br>
      if (t > a[j])<br>
         break;<br>
      else if (t <= a[j]) {<br>
         a[j / 2] = a[j];<br>
         j = 2 * j;<br>
      }<br>
   }<br>
   a[j/2] = t;<br>
   return;<br>
}<br>
void build_maxheap(int *a,int n) {<br>
   int k;<br>
   for(k = n/2; k >= 1; k--) {<br>
      max_heap(a,k,n);<br>
   }<br>
}<br>
int main() {<br>
   int n, i;<br>
   cout<<"enter no of elements of array\n";<br>
   cin>>n;<br>
   int a[30];
   for (i = 1; i <= n; i++) {<br>
      cout<<"enter elements"<<" "<<(i)<<endl;<br>
      cin>>a[i];<br>
   }<br>
   build_maxheap(a,n);<br>
   cout<<"Max Heap\n";<br>
   for (i = 1; i <= n; i++) {<br>
      cout<<a[i]<<endl;<br>
   }<br>
}<br>
**OUTPUT**	<br>
![image](https://user-images.githubusercontent.com/97940850/156985379-70a13c84-6a1d-49fe-9576-4023593ee59a.png)<br>
	       
**12.Find a subset of given set,s={s1,s2,s3....sn} of n positive integer whose sum=a,given positive integer d.**<br>
#include <iostream><br>
using namespace std;<br>
void displaySubset(int subSet[], int size)<br>
{<br>
   for(int i = 0; i < size; i++) <br>
   {<br>
      cout << subSet[i] << "  ";<br>
   }<br>
   cout << endl;<br>
}<br>

void subsetSum(int set[], int subSet[], int n, int subSize, int total, int nodeCount ,int sum) <br>
{<br>
   if( total == sum) <br>
   {<br>
      displaySubset(subSet, subSize);    <br> 
      subsetSum(set,subSet,n,subSize-1,total-set[nodeCount],nodeCount+1,sum);    <br> 
      return;<br>
   }<br>
   else <br>
   {<br>
      for( int i = nodeCount; i < n; i++ ) <br>
	  {     <br>
         subSet[subSize] = set[i];<br>
         subsetSum(set,subSet,n,subSize+1,total+set[i],i+1,sum);   <br>  
      }<br>
   }<br>
}<br>

void findSubset(int set[], int size, int sum)<br>
 {<br>
   int *subSet = new int[size];   <br>  
   subsetSum(set, subSet, size, 0, 0, 0, sum);<br>
   delete[] subSet;<br>
}<br>

int main()<br>
{<br>
   int weights[] = {4,6,3,7,5,8,1};<br>
   int size = 7;<br>
   findSubset(weights, size, 11);<br>
}<br>

**OUTPUT**<br>
![image](https://user-images.githubusercontent.com/97940850/157186615-bf022f29-a9bd-484f-ba85-44cfe525d621.png)<br>

**/*13..Write a program to store k keys into an array of size n at the location compute using a hash function, <br>
loc=key%n, where k<=n and  key takes values from [1 to m], m>n. Handle the collision using Linear Probing technique.*/**<br>
#include<iostream><br>
#include<limits.h><br>
using namespace std;<br>
void Insert(int ary[],int hFn, int Size)<br>
{<br>
    int element,pos,n=0;<br>
	cout<<"Enter key element to insert\n";v
	cin>>element;<br>
	pos = element%hFn; <br>
	while(ary[pos]!= INT_MIN)<br>
 	{  <br>
		if(ary[pos]== INT_MAX)<br>
     	break;<br>
		pos = (pos+1)%hFn;<br>
		n++;<br>
		if(n==Size)<br>
   		 break;   <br>  
	}<br>
	if(n==Size)<br>
    cout<<"Hash table was full of elements\nNo Place to insert this element\n\n";<br>
	else<br>
    ary[pos] = element; <br>   
}<br>
void display(int ary[],int Size)<br>
{<br>
	int i;<br>
	cout<<"Index\tValue\n";<br>
	for(i=0;i<Size;i++)<br>
    cout<<i<<"\t"<<ary[i]<<"\n";<br>
}<br>
int main()<br>
{<br>
	int Size,hFn,i,choice;<br>
	cout<<"Enter size of hash table\n";<br>
	cin>>Size;<br>
	 hFn=Size;<br>
	int ary[Size];<br>
	for(i=0;i<Size;i++)<br>
     ary[i]=INT_MIN; <br>
	do<br>
	{<br>
		cout<<"Enter your choice: ";<br>
		cout<<" 1-> Insert\n 2-> Display\n 0-> Exit\n";<br>
		cin>>choice;<br>
		switch(choice)<br>
		{<br>
		case 1:<br>
			Insert(ary,hFn,Size);<br>
			break;<br>
		case 2:<br>
			display(ary,Size);<br>
			break;<br>
		default:<br>
			cout<<"Enter correct choice\n";<br>
		break;<br>
		}<br>
	}<br>
while(choice);<br>
return 0;<br>
}<br>
	<br>
**OUTPUT**	<br>
![image](https://user-images.githubusercontent.com/97940850/162888607-083eb423-d86f-4124-9544-98f32e0d8f5d.png)<br>
<br>
<br>
	
	
**14. /*Write a C++ program to implement merge sort technique using divide and conquer method.*/**<br>
#include <iostream><br>
#include<conio.h><br>
using namespace std;<br>
void Merge(int *a, int low, int high, int mid)<br>
{<br>
	int i, j, k, temp[high-low+1];<br>
	i = low;<br>
	k = 0;<br>
              j = mid + 1;<br>
             while (i <= mid && j <= high)<br>
	{<br>
		if (a[i] < a[j])<br>
		{<br>
			temp[k] = a[i];<br>
			k++;<br>
			i++;<br>
		}<br>
		else<br>
		{<br>
			temp[k] = a[j];<br>
			k++;<br>
			j++;<br>
		}<br>
	}<br>
	while (i <= mid)<br>
	<br>
	{<br>
		temp[k] = a[i];<br>
		k++;<br>
		i++;<br>
	}<br>
	while (j <= high)<br>
	{<br>
		temp[k] = a[j];<br>
		k++;<br>
		j++;<br>
	}<br>
	for (i = low; i <= high; i++)<br>
	{<br>
		a[i] = temp[i-low];<br>
	}<br>
}<br>
void MergeSort(int *a, int low, int high)<br>
{<br>
	int mid;<br>
	if (low < high)<br>
	{<br>
		mid=(low+high)/2;<br>
			MergeSort(a, low, mid);<br>
		              MergeSort(a, mid+1, high);<br>
			Merge(a, low, high, mid);<br>
	}<br>
}<br>
int main()<br>
{<br>
	int n, i;<br>
	cout<<"\n Enter the number of data element to be sorted: ";<br>
	cin>>n;<br>
 int arr[n];<br>
for(i = 0; i < n; i++)<br>
{<br>
	cout<<"Enter element "<<i+1<<": ";<br>
	cin>>arr[i];<br>
}<br>
     MergeSort(arr, 0, n-1);<br>
	cout<<"\nSorted Data ";<br>
	for (i = 0; i < n; i++)<br>
        cout<<"->"<<arr[i];<br>
 
 getch();<br>
}<br>
<br>					
**OUTPUT**<br>
![image](https://user-images.githubusercontent.com/97940850/162889023-188b1519-5788-4ab3-bed5-22b8b855260d.png)<br>
				
**15. Write a c++ program to implement doubly Linked list.**<br>
#include<iostream><br>
#include<cstdio><br>
#include<cstdlib><br>
using namespace std;<br>
struct node<br>
{<br>
    int info;<br>
    struct node *next;<br>
    struct node *prev;<br>
}*start;<br>
class double_llist<br>
{<br>
    public:<br>
        void create_list(int value);<br>
        void add_begin(int value);<br>
        void add_after(int value, int position);<br>
        void delete_element(int value);<br>
        void search_element(int value);<br>
        void display_dlist();<br>
        void count();<br>
        void reverse();<br>
        double_llist()<br>
        {<br>
            start = NULL;  <br>
        }<br>
};<br>
 int main()<br>
{<br>
    int choice, element, position;<br>
    double_llist dl;<br>
    while (1)<br>
    {<br>
        cout<<endl<<"----------------------------"<<endl;<br>
        cout<<endl<<"Operations on Doubly linked list"<<endl;<br>
        cout<<endl<<"----------------------------"<<endl;   <br>   
        cout<<"1.Create Node"<<endl;<br>
        cout<<"2.Add at begining"<<endl;<br>
        cout<<"3.Add after position"<<endl;<br>
        cout<<"4.Delete"<<endl;<br>
        cout<<"5.Display"<<endl;<br>
        cout<<"6.Count"<<endl;<br>
        cout<<"7.Reverse"<<endl;<br>
        cout<<"8.Quit"<<endl;<br>
        cout<<"Enter your choice : ";<br>
        cin>>choice;<br>
        switch ( choice )<br>
        {<br>
        case 1:<br>
            cout<<"Enter the element: ";<br>
            cin>>element;<br>
            dl.create_list(element);<br>
            cout<<endl;<br>
            break;<br>
        case 2:<br>
            cout<<"Enter the element: ";<br>
            cin>>element;<br>
            dl.add_begin(element);<br>
            cout<<endl;<br>
            break;<br>
        case 3:<br>
            cout<<"Enter the element: ";<br>
            cin>>element;<br>
            cout<<"Insert Element after postion: ";<br>
            cin>>position;<br>
            if(position<=0)<br>
            {<br>
            	cout<<"\n Position cant be less than 1. "<<endl;<br>
            break;<br>
			}<br>
            dl.add_after(element, position);<br>
            cout<<endl;<br>
            break;<br>
        case 4:<br>
            if (start == NULL)<br>
            {                    <br>  
                cout<<"List empty,nothing to delete"<<endl;  <br>
                break;<br>
            }<br>
            cout<<"Enter the element for deletion: ";<br>
            cin>>element;<br>
            dl.delete_element(element);<br>
            cout<<endl;<br>
            break;<br>
        case 5:<br>
            dl.display_dlist();<br>
            cout<<endl;<br>
            break;<br>
        case 6:<br>
            dl.count();<br>
            break;  <br>  
        case 7:<br>
            if (start == NULL)<br>
            {<br>
                cout<<"List empty,nothing to reverse"<<endl;<br>
                break;<br>
            }<br>
            dl.reverse();<br>
            cout<<endl;<br>
            break;<br>
        case 8:<br>
            exit(1);<br>
        default:<br>
            cout<<"Wrong choice"<<endl;<br>
        }<br>
    }<br>
    return 0;<br>
}<br>
 void double_llist::create_list(int value)<br>
{<br>
    struct node *s, *temp;<br>
    temp = new(struct node);<br>
    temp->info = value;<br>
    temp->next = NULL;<br>
    if (start == NULL)<br>
    {<br>
        temp->prev = NULL;<br>
        start = temp;<br>
    }<br>
    else<br>
    {<br>
        s = start;<br>
        while (s->next != NULL)<br>
            s = s->next;<br>
        s->next = temp;<br>
        temp->prev = s;<br>
    }<br>
}<br>
 void double_llist::add_begin(int value)<br>
{<br>
    if (start == NULL)<br>
    {<br>
        cout<<"First Create the list."<<endl;<br>
        return;<br>
    }<br>
    struct node *temp;<br>
    temp = new(struct node);<br>
    temp->prev = NULL;<br>
    temp->info = value;<br>
    temp->next = start;<br>
    start->prev = temp;<br>
    start = temp;<br>
    cout<<"Element Inserted"<<endl;<br>
}<br>
void double_llist::add_after(int value, int pos)<br>
{<br>
    if (start == NULL)<br>
    {<br>
        cout<<"First Create the list."<<endl;<br>
        return;<br>
    }<br>
    struct node *tmp, *q;<br>
    int i;<br>
    q = start;<br>
    for (i = 0;i < pos - 1;i++)<br>
    {<br>
        q = q->next;<br>
        if (q == NULL)<br>
        {<br>
            cout<<"There are less than ";<br>
            cout<<pos<<" elements."<<endl;<br>
            return;<br>
        }<br>
    }<br>
    tmp = new(struct node);<br>
    tmp->info = value;<br>
    if (q->next == NULL)<br>
    {<br>
        q->next = tmp;<br>
        tmp->next = NULL;<br>
        tmp->prev = q;    <br>  
    }<br>
    else<br>
    {<br>
        tmp->next = q->next;<br>
        tmp->next->prev = tmp;<br>
        q->next = tmp;<br>
        tmp->prev = q;<br>
    }<br>
    cout<<"Element Inserted"<<endl;<br>
}<br>
 void double_llist::delete_element(int value)<br>
{<br>
    struct node *tmp, *q;<br>
        if (start->info == value)<br>
    {<br>
        tmp = start;<br>
        start = start->next;  <br>
        start->prev = NULL;<br>
        cout<<"Element Deleted"<<endl;<br>
        free(tmp);<br>
        return;<br>
    }<br>
    q = start;<br>
    while (q->next->next != NULL)<br>
    {  <br>
               if (q->next->info == value)  <br>
        {<br>
            tmp = q->next;<br>
            q->next = tmp->next;<br>
            tmp->next->prev = q;<br>
            cout<<"Element Deleted"<<endl;<br>
            free(tmp);<br>
            return;<br>
        }<br>
        q = q->next;<br>
    }<br>
        if (q->next->info == value)  <br>  
    {<br>
        tmp = q->next;<br>
        free(tmp);<br>
        q->next = NULL;<br>
        cout<<"Element Deleted"<<endl;<br>
        return;<br>
    }<br>
    cout<<"Element "<<value<<" not found"<<endl;<br>
}<br>
 void double_llist::display_dlist()<br>
{<br>
    struct node *q;<br>
    if (start == NULL)<br>
    {<br>
        cout<<"List empty,nothing to display"<<endl;<br>
        return;<br>
    }<br>
    q = start;<br>
    cout<<"The Doubly Link List is :"<<endl;<br>
    while (q != NULL)<br>
    {<br>
        cout<<q->info<<" <-> ";<br>
        q = q->next;<br>
    }<br>
    cout<<"NULL"<<endl;<br>
}<br>
 void double_llist::count()<br>
{<br>
    struct node *q = start;<br>
    int cnt = 0;<br>
    while (q != NULL)<br>
    {<br>
        q = q->next;<br>
        cnt++;<br>
    }<br>
    cout<<"Number of elements are: "<<cnt<<endl;<br>
}<br>
 void double_llist::reverse()<br>
{<br>
    struct node *p1, *p2;<br>
    p1 = start;<br>
    p2 = p1->next;<br>
    p1->next = NULL;<br>
    p1->prev = p2;<br>
    while (p2 != NULL)<br>
    {<br>
        p2->prev = p2->next;<br>
        p2->next = p1;<br>
        p1 = p2;<br>
        p2 = p2->prev;<br>
    }<br>
    start = p1;<br>
    cout<<"List Reversed"<<endl;<br>
}<br>	
<br>	
**OUTPUT**<br>
![image](https://user-images.githubusercontent.com/97940850/163925823-3a5f14c6-7a35-4b6b-b938-65c6637fe5a2.png)<br>
![image](https://user-images.githubusercontent.com/97940850/163925915-56cb951c-b09b-445e-8835-03d1a7112d98.png)<br>
![image](https://user-images.githubusercontent.com/97940850/163926042-c912ec96-1226-4520-8477-3a9f9c382dd6.png)<br>
![image](https://user-images.githubusercontent.com/97940850/163926125-0f99da44-5330-43ba-a4b3-2dd9456d7bfa.png)<br>
![image](https://user-images.githubusercontent.com/97940850/163926257-5cfb44bb-76f9-4155-87b9-751b66ca5687.png)<br>

**16. Write a C++ program to solve N-Queue problem using backtracking method. **<br>
#include<iostream><br>
using namespace std;<br>
int grid[10][10];<br>
//print the solution<br>
void print(int n)
{<br>
    for (int i = 0;i <= n-1; i++)<br>
	 {<br>
        for (int j = 0;j <= n-1; j++)<br>
		 {<br>
            
                cout <<grid[i][j]<< " ";<br>
            
        }<br>
        cout<<endl;<br>
    }<br>
    cout<<endl;<br>
    cout<<endl;<br>
}<br>
//function for check the position is safe or not<br>
//row is indicates the queen no. and col represents the possible positions<br>
bool isSafe(int col, int row, int n) <br>
{<br>
  //check for same column<br>
    for (int i = 0; i < row; i++)<br>
	 {<br>
        if (grid[i][col])<br>
		 {<br>
            return false;<br>
        }<br>
    }<br>
    //check for upper left diagonal<br>
    for (int i = row,j = col;i >= 0 && j >= 0; i--,j--) <br>
	{<br>
    	 if (grid[i][j]) <br>
		 {<br>
            return false;<br>
        }<br>
    }<br>
    //check for upper right diagonal<br>
    for (int i = row, j = col; i >= 0 && j < n; j++, i--) <br>
	{<br>
        if (grid[i][j]) <br>
		{<br>
            return false;<br>
        }<br>
    }<br>
    return true;<br>
}<br>
//function to find the position for each queen<br>
//row is indicates the queen no. and col represents the possible positions<br>
bool solve (int n, int row) <br>
{<br>
    if (n == row) <br>
	{<br>
        print(n);<br>
        return true;<br>
    }<br>
    //variable res is use for possible backtracking <br>
    bool res = false;<br>
    for (int i = 0;i <=n-1;i++) <br>
	{<br>
        if (isSafe(i, row, n)) <br>
		{<br>
            grid[row][i] = 1;<br>
            //recursive call solve(n, row+1) for next queen (row+1)<br>
            res = solve(n, row+1) || res;//if res ==false then backtracking will occur <br>
            //by assigning the grid[row][i] = 0<br>
            
            grid[row][i] = 0;<br>
        }<br>
    }<br>
    return res;<br>
}<br>
int main()<br>
{<br>
  ios_base::sync_with_stdio(false);<br>
    cin.tie(NULL);<br>
        int n;<br>
        cout<<"Enter the number of queen"<<endl;<br>
        cin >> n;<br>
        for (int i = 0;i < n;i++) <br>
		{<br>
            for (int j = 0;j < n;j++) <br>
			{<br>
                grid[i][j] = 0;<br>
            }<br>
        }<br>
        bool res = solve(n, 0);<br>
        if(res == false) <br>
		{<br>
            cout << -1 << endl; //if there is no possible solution<br>
        } else <br>
		{<br>
            cout << endl;<br>
        }<br>
  return 0;<br>
}<br>
	<br>
**OUTPUT**<br>
![image](https://user-images.githubusercontent.com/97940850/163940155-348b853a-c87d-4d81-85a7-eb185157e372.png)<br>

	
**17. Write a C++ program to find  MST Using  Kruskal's algorithm.**<br>
#include<bits/stdc++.h><br>
using namespace std;<br>
typedef pair<int, int> iPair;<br>
struct Graph<br>
{<br>
	int V, E;<br>
	vector< pair<int, iPair> > edges;<br>
	Graph(int V, int E)<br>
	{<br>
	this->V = V;<br>
	this->E = E;<br>
	}<br>
	void addEdge(int u, int v, int w)<br>
	{<br>
		edges.push_back({w, {u, v}});<br>
	}	<br>
	int kruskalMST();<br>
};<br>
<br>
struct DisjointSets<br>
{<br>
	int *parent, *rnk;<br>
	int n;<br>
	DisjointSets(int n)<br>
	{	<br>
		this->n = n;<br>
		parent = new int[n+1];<br>
		rnk = new int[n+1];<br>
		for (int i = 0; i <= n; i++)<br>
		{<br>
			rnk[i] = 0;<br>
			parent[i] = i;<br>
		}<br>
	}<br>
	int find(int u)<br>
	{<br>
		if (u != parent[u])<br>
		parent[u] = find(parent[u]);<br>
		return parent[u];<br>
	}<br>
	void merge(int x, int y)<br>
	{<br>
		x = find(x), y = find(y);<br>
		if (rnk[x] > rnk[y])<br>
		parent[y] = x;<br>
		else // If rnk[x] <= rnk[y]<br>
		parent[x] = y;<br>
		if (rnk[x] == rnk[y])<br>
		rnk[y]++;<br>
	}<br>
};<br>
int Graph::kruskalMST()<br>
{<br>
	int mst_wt = 0; <br>
	sort(edges.begin(), edges.end());<br>
	DisjointSets ds(V);<br>
	vector< pair<int, iPair> >::iterator it;<br>
	for (it=edges.begin(); it!=edges.end(); it++)<br>
	{<br>
		int u = it->second.first;<br>
		int v = it->second.second;<br>
		int set_u = ds.find(u);<br>
		int set_v = ds.find(v);<br>
		if (set_u != set_v)<br>
		{<br>
			cout << u << " - " << v << endl;<br>
			mst_wt += it->first;<br>
			ds.merge(set_u, set_v);<br>
		}<br>
	}<br>		
	return mst_wt;<br>
}<br>
int main()<br>
{<br>
	int V = 9, E = 14;<br>
	Graph g(V, E);<br>
	g.addEdge(0, 1, 4);<br>
	g.addEdge(0, 7, 8);<br>
	g.addEdge(1, 2, 8);<br>
	g.addEdge(1, 7, 11);<br>
	g.addEdge(2, 3, 7);<br>
	g.addEdge(2, 8, 2);<br>
	g.addEdge(2, 5, 4);<br>
	g.addEdge(3, 4, 9);<br>
	g.addEdge(3, 5, 14);<br>
	g.addEdge(4, 5, 10);<br>
	g.addEdge(5, 6, 2);<br>
	g.addEdge(6, 7, 1);<br>
	g.addEdge(6, 8, 6);<br>
	g.addEdge(7, 8, 7);<br>
	cout << "Edges of MST are \n";<br>
	int mst_wt = g.kruskalMST();<br>
	cout << "\nWeight of MST is " << mst_wt;<br>
	return 0;<br>
}<br>
	<br>
**OUTPUT**<br>
![image](https://user-images.githubusercontent.com/97940850/165230800-bb45de63-9fac-4176-a319-755c346b52e5.png)<br>
<br>
	
**18.  Write a C++ program to find   MST using Prim's algorithm..**<br>
#include <bits/stdc++.h><br>
using namespace std;<br>
#define V 5<br>
int minKey(int key[], bool mstSet[])<br>
{<br>
	int min = INT_MAX, min_index;<br>
	for (int v = 0; v < V; v++)<br>
	if (mstSet[v] == false && key[v] < min)<br>
	min = key[v], min_index = v;<br>
	return min_index;<br>
}<br>
void printMST(int parent[], int graph[V][V])<br>
{<br>
	cout<<"Edge \tWeight\n";<br>
	for (int i = 1; i < V; i++)<br>
	cout<<parent[i]<<" - "<<i<<" \t"<<graph[i][parent[i]]<<" \n";<br>
}<br>
<br>
void primMST(int graph[V][V])<br>
{<br>
	int parent[V];<br>
	int key[V];<br>
	bool mstSet[V];<br>
	for (int i = 0; i < V; i++)<br>
	key[i] = INT_MAX, mstSet[i] = false;<br>
	key[0] = 0;<br>
	parent[0] = -1; // First node is always root of MST<br>
	for (int count = 0; count < V - 1; count++)<br>
	{<br>
		int u = minKey(key, mstSet);<br>
		mstSet[u] = true;<br>
		for (int v = 0; v < V; v++)<br>
		if (graph[u][v] && mstSet[v] == false && graph[u][v] < key[v])<br>
		parent[v] = u, key[v] = graph[u][v];<br><br>
	}<br>
	printMST(parent, graph);<br>
}<br>
int main()<br>
{<br>
	int graph[V][V] = { { 0, 2, 0, 6, 0 },<br>
	{ 2, 0, 3, 8, 5 },<br>
	{ 0, 3, 0, 0, 7 },<br>
	{ 6, 8, 0, 0, 9 },<br>
	{ 0, 5, 7, 9, 0 } };<br>
	primMST(graph);<br>
	return 0;<br>
}<br>

<br>
**OUTPUT**<br>
![image](https://user-images.githubusercontent.com/97940850/165226736-8ef50d16-3446-41de-97ff-acbf1a77f4d9.png)<br>
		<br>						      
**19.Write a c++ program to implement DFS. **<br>
#include<iostream><br>
#include<conio.h><br>
#include<stdlib.h><br>
using namespace std;<br>
int cost[10][10],i,j,k,n,stk[10],top,v,visit[10],visited[10];<br>
int main()<br>
{<br>
    int m;<br>
    cout <<"Enter no of vertices:";<br>
    cin >> n;<br>
    cout <<"Enter no of edges:";<br>
    cin >> m;<br>
    cout <<"\nEDGES \n";<br>
    for(k=1; k<=m; k++)<br>
    {<br>
        cin >>i>>j;<br>
        cost[i][j]=1;<br>
    }<br>
    cout <<"Enter initial vertex to traverse from:";<br>
    cin >>v;<br>
    cout <<"DFS ORDER OF VISITED VERTICES:";<br>
    cout << v <<" ";<br>
    visited[v]=1;<br>
    k=1;<br>
    while(k<n)<br>
    {<br>
        for(j=n; j>=1; j--)<br>
            if(cost[v][j]!=0 && visited[j]!=1 && visit[j]!=1)<br>
            {<br>
                visit[j]=1;<br>
                stk[top]=j;<br>
                top++;<br>
            }<br>
        v=stk[--top];<br>
        cout<<v << " ";<br>
        k++;<br>
        visit[v]=0;<br>
        visited[v]=1;<br>
    }<br>
    return 0;<br>
}<br>
<br>
**OUTPUT**<br>
![image](https://user-images.githubusercontent.com/97940850/165233433-8cf4800a-c017-462e-9fb6-ffd239571dc4.png)<br>
	<br>
**20. Write a c++ program to implement BFS.**<br>
	#include<iostream><br>
#include<conio.h><br>
#include<stdlib.h><br>
using namespace std;<br>
 int cost[10][10],qu[10],front,rare,visit[10],visited[10];<br>
int main()<br>
{<br>

   int m,n,j,i,v,k;<br>
    cout <<"Enter no of vertices:";<br>
    cin >> n;<br>
    cout <<"Enter no of edges:";<br>
    cin >> m;<br>
    cout <<"\nEDGES \n";<br>
    for(k=1; k<=m; k++)<br>
    {<br>
        cin >>i>>j;<br>
        cost[i][j]=1;<br>
    }<br>
    cout <<"Enter initial vertex to traverse from:";<br>
    cin >>v;<br>
    cout <<"Visitied vertices:";<br>
    cout <<v<<" ";<br>
    visited[v]=1;<br>
    k=1;<br>
    while(k<n)<br>
    {<br>
        for(j=1; j<=n; j++)<br>
            if(cost[v][j]!=0 && visited[j]!=1 && visit[j]!=1)<br>
            {<br>
                visit[j]=1;<br>
                qu[rare++]=j;<br>
            }<br>
        v=qu[front++];<br>
        cout<<v <<" ";<br>
        k++;<br>
        visit[v]=0;<br>
        visited[v]=1;<br>
    }<br>
    return 0;<br>
}<br>
	<br>
**OUTPUT**<br>
![image](https://user-images.githubusercontent.com/97940850/165234476-4157cf74-79a1-4f45-97c4-1d9df46f91f2.png)<br>
<br>

**21.Write a C++ Program to find minimum and maximum element from an unsorted array using Divide and Conquer method. **	<br>
#include <iostream><br>
#include <stdio.h><br>
#include <stdlib.h><br>
#include <conio.h>
using namespace std;
void findMinAndMax(int arr[], int low, int high, int &min, int &max)
{
	if (low == high)	
	{
		if (max < arr[low])
		{	
			max = arr[low];
		}	

		if (min > arr[high])
		{
			min = arr[high];
		}
	return;
	}
	if (high - low == 1)	
	{
		if (arr[low] < arr[high])	
		{		
			if (min > arr[low])
 			{
				min = arr[low];
			}				

			if (max < arr[high])
			{
				max = arr[high];
			}				
		}
		else 
		{
			if (min > arr[high])
			{
				min = arr[high];
			}

			if (max < arr[low])
 			{			
				max = arr[low];
			}
		}	
		return;
	}
	int mid = (low + high) / 2;
	findMinAndMax(arr, low, mid, min, max);
	findMinAndMax(arr, mid + 1, high, min, max);
}
int main()
{

	int arr[] = { 7, 2, 9, 3, 6, 7, 8, 4 };
	int n = sizeof(arr) / sizeof(arr[0]);
	int max = arr[0], min = arr[0];

	findMinAndMax(arr, 0, n - 1, min, max);

	cout << "The minimum array element is " << min << endl;
	cout << "The maximum array element is " << max;

	return 0;
}
						      
**OUTPUT**<br>
![image](https://user-images.githubusercontent.com/97940850/165238668-00e742ef-3270-408e-b5fd-4cf67d4f2a12.png)<br>

