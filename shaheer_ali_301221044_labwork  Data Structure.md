### Question 1:
Write a C++ program to display "Hello, World!" on the console.

**Program:**
```cpp
#include<iostream>
using namespace std;
int main()
{
    cout<<"Hello, World!";
    return 0;
}
```

**Output:**

![1701865411741](image/shaheer_ali_301221044_labworkDataStructure/1701865411741.png)

---


### Question 2:
Write a C++ program to display "Hello, World!" twenty times using a for loop.

**Program:**
```cpp
#include<iostream>
using namespace std;
int main()
{
    int i;
    for(i=0;i<20;i++)
        cout<<"Hello, World!"<<endl;
    return 0;
}
```

**Output:**

![1701865666340](image/shaheer_ali_301221044_labworkDataStructure/1701865666340.png)
---

### Question 3:
Write a C++ program that takes an integer as input, displays the entered number, and then prints the double of that number.

**Program:**
```cpp
#include<iostream>
using namespace std;
int main()
{
    int i;
    cout<<"Enter an integer: ";
    cin>>i;
    cout<<"\nThe number entered is "<<i;
    cout<<"\nEntered number doubled: "<<i*2;
    return 0;
}
```

**Output:**
![1701865797097](image/shaheer_ali_301221044_labworkDataStructure/1701865797097.png)
---

### Question 4:
Write a C++ program that takes the number of elements as input, reads an array, and calculates and prints the sum of the elements.

**Program:**
```cpp
#include<iostream>
using namespace std;
int main()
{
    int i, n, s, x[10];
    cout<<"Enter number of elements: ";
    cin>>n;
    
    cout<<"\nEnter the elements: ";
    for(i=0; i<n; i++)
    {
        cin>>x[i];
    }
    
    s=0;
    
    for(int j=0; j<n; j++)
    {
        s=s+x[j];
    }
    
    cout<<"\nSum of elements of array = "<<s;
    return 0;
}
```

**Output:**
![1701868037161](image/shaheer_ali_301221044_labworkDataStructure/1701868037161.png)

---

### Question 5:
Write a C++ program to input ten integers into an array and find the smallest integer among them.

**Program:**
```cpp
#include<iostream>
using namespace std;
int main()
{
    int x[10], s;
    cout<<"Enter 10 integers: ";
    for(int i=0; i<=9; i++)
    {
        cin>>x[i];
    }
    s=x[0];
    for(int j=0; j<=9; j++)
    {
        if(s>x[j])
        {
            s=x[j];
        }
    }
    cout<<"\nThe smallest integer: "<<s;
    return 0;
}
```

**Output:**
![1701868222991](image/shaheer_ali_301221044_labworkDataStructure/1701868222991.png)


---

### Question 6:
Write a C++ program to input ten integers into an array and sort them in ascending order using the bubble sort algorithm.

**Program:**
```cpp
#include <iostream>
using namespace std;
int main()
{
    int x[10], t;
    cout<<"\nEnter 10 integers value:";
    for(int i=0; i<=9; i++)
    {
        cin>>x[i];
    }
    for(int p=1; p<9; p++)
    {
        for(int c=0; c<=9; c++)
        {
            if(x[c]>x[c+1])
            {
                t=x[c];
                x[c]=x[c+1];
                x[c+1]=t;
            }
        }
    }
    for(int j=0; j<=9; j++)
    {
        cout<<endl<<x[j];
    }
    return 0;
}
```

**Output:**
![1701868284085](image/shaheer_ali_301221044_labworkDataStructure/1701868284085.png)
---

### Question 7:
Write a C++ program to input ten integers into an array and sort them in ascending order using the selection sort algorithm.

**Program:**
```cpp
#include<iostream>
using namespace std;
int main()
{
    int x[10], k, s;
    cout<<"ENTER 10 INTEGERS VALUE";
    for(int i=0; i<=9; i++)
    {
        cin>>x[i];
    }
    for(int p=0; p<9; p++)
    {
        s=x[p];
        k=p;
        for(int c=p+1; c<=9; c++)
        {
            if(s>x[c])
            {
                s=x[c];
                k=c;
            }
        }
        int t=x[p];
        x[p]=x[k];
        x[k]=t;    
    }
    for(int i=0; i<=9; i++)
    {
        cout<<endl<<x[i];
    }
    return 0;
}

```

**Output:**
![1701868524247](image/shaheer_ali_301221044_labworkDataStructure/1701868524247.png)

---

### Question 8:
Write a C++ program to perform linear search in an array. It should take ten elements as input and search for a given item.

**Program:**
```cpp
//linear search
#include<iostream>
using namespace std;
int main()
{
    int x[10], item;
    cout<<"enter 10 elements:";
    for(int i=0; i<=9; i++)
    {
        cin>>x[i];
    }
    cout<<"\n enter item to search:";
    cin>>item;
    for(int j=0; j<=9; j++)
        if(item==x[j])
        {
            cout<<"\n successfully find:"<<"\n location"<<j+1;
            exit(1);
        }
    cout<<"\n unsuccessful:";
    return 0;
}
```

**Output:**
![1701868729032](image/shaheer_ali_301221044_labworkDataStructure/1701868729032.png)

---

### Question 9:
Write a C++ program to perform binary search in a sorted array. It should take ten elements as input and search for a given item.

**Program:**
```cpp
//binary searching
#include<iostream>
using namespace std;
int main()
{
    int x[10], mid, item, l=0, h=9;
    cout<<"enter 10 elements in sorted form:";
    for(int i=0; i<=9; i++)
    {
        cin>>x[i];
    }
    cout<<"\n enter item to search:";
    cin>>item;
    while(l<=h)
    {
        mid=(l+h)/2;
        if(item==x[mid])
        {
            cout<<"\n successfully found:"<<endl<<"location"<<mid+1;
            exit(1);
        }
        if(item<x[mid])
        {
            h=mid-1;
        }
        if(item>x[mid])
        {
            l=mid+1;
        }    
    }
    cout<<"unsuccessful:";
    return 0;
}
```

**Output:**
![1701868812313](image/shaheer_ali_301221044_labworkDataStructure/1701868812313.png)

---

### Question 10:
Write a C++ program to create a linked list by taking integers as input until 0 is

 entered. Display the elements of the linked list.

**Program:**
```cpp
//link list creation
#include<iostream>
#include<malloc.h>
using namespace std;

struct node //user defined
{
    int info;
    node *next;
};

node *start, *q;
int x;

int main()
{
    start = NULL; //initializes start pointer to NULL
    q = NULL; //initializes q pointer to NULL

    cout<<"Enter integers to create a linked list. Enter 0 to stop.\n";

    do
    {
        cin>>x;
        if (x!=0) //tab tak if statement chalegi jab tak '0' enter nahi kia jayega
        {
            if (start==NULL)
            {
                start = (node *)malloc(sizeof(node)); //memory allocate karky start pointer ky hawaly kardeta hai address
                q = start;
            }
            else
            {
                q->next = (node *)malloc(sizeof(node));
                q = q->next;
            }

            q->info = x;
            q->next = NULL;
        }
    } 
    while (x != 0);

    q = start; //traversing ky liye

    cout << "\nLinked list elements:\n";
    while (q != NULL)
    {
        cout << q->info << endl;
        q = q->next;
    }
    
    return 0;
}
```

**Output:**
![1701868925147](image/shaheer_ali_301221044_labworkDataStructure/1701868925147.png)

---

### Question 11:
Write a C++ program to create a linked list by taking integers as input until 0 is entered. Display the elements of the linked list and search for a specific item.

**Program:**
```cpp
//searching in linked list
#include<iostream>
#include<malloc.h>
using namespace std;

struct node
{
    int info;
    node *next;
};

node *start, *q;
int x;

int main()
{
    start = NULL;
    q = NULL;
    
    cout<<"Enter elements in linked list. Enter 0 to stop.\n";
    //agar cout ko loop mein daal deingy toh baar baar yeh print kardega

    do
    {
        cin>>x;
        if(x!=0)
        {
            if(start==NULL)
            {
                start = (node *)malloc(sizeof(node));
                q = start;
            }
            else
            {
                q->next=(node *)malloc(sizeof(node));
                q = q->next;
            }
            q->info = x;
            q->next = NULL;
        }
    }
    while(x!=0);
    q=start; //traversing ky liye
    
    cout<<"\nLinked List: \n";
    while(q!=NULL)
    {
        cout<<q->info<<endl;
        q = q->next;
    }
    
    int item;
    cout<<"\nEnter the item:";
    cin>>item;
    q=start;
    while(q!=NULL)
    {
        if(item==q->info)
        {
            cout<<"\nSuccessfull";
            exit(0);
        }
        else
        {
            q=q->next;
        }
    }
    cout<<"\nUnsuccessful";

    return 0;
}
```

**Output:**
![1701869583489](image/shaheer_ali_301221044_labworkDataStructure/1701869583489.png)

---

### Question 12:
Write a C++ program to create a linked list by taking integers as input until 0 is entered. Delete a specific item from the linked list and display the remaining elements.

**Program:**
```cpp
//program to delete from linked list
#include<iostream>
#include<malloc.h>
using namespace std;

struct node
{
    int info;
    node *next;
};

int x;
node *start, *q, *p;

int main()
{
    start = NULL;
    q = NULL;
    
    cout<<"Enter elements for linked list. Enter 0 to stop.\n";
    
    do
    {
        cin>>x;
        if(x!=0)
        {
            if(start==NULL)
            {
                start = (node *)malloc(sizeof(node));
                q = start;
            }
            else
            {
                q->next = (node *)malloc(sizeof(node));
                q = q->next;
            }
            q->info = x;
            q->next = NULL;
        }
    }
    while(x!=0);
    
    int item;
    cout<<"\nEnter item to be deleted: ";
    cin>>item;
    q=start;
    p=start;
    while(q!=NULL)
    {
        if(item==q->info)
        {
            p->next=q->next;
            q->next=NULL;
            free(q);
            break;
        }
        else
        {
            p=q;
            q=q->next;
        }
    }
    
    q=start;
    while(q!=NULL)
    {
        cout<<q->info<<endl;
        q=q->next;
    }
    return 0;
}
```

**Output:**
![1701869635170](image/shaheer_ali_301221044_labworkDataStructure/1701869635170.png)

---

### Question 13:
Write a C++ program to multiply two 2x2 matrices. It should take matrix elements as input and display the resultant matrix.

**Program:**
```cpp
//to multiply two 2x2 matrices
#include<iostream>
using namespace std;
int main() 
{
    int a[2][2], b[2][2], c[2][2], i, j;
    cout << "Enter elements of 1st matrix: \n";
    for (i = 0; i < 2; i++) 
    {
        for (j = 0; j < 2; j++) 
        {
            cin >> a[i][j];
        }
    }
    cout << "Enter elements of 2nd matrix: \n";
    for (i = 0; i < 2; i++) 
    {
        for (j = 0; j < 2; j++) 
        {
            cin >> b[i][j];
        }
    }
    for (i = 0; i < 2; i++) 
    {
        for (j = 0; j < 2; j++) 
        {
            c[i][j] = a[i][j] * b[i][j];
        }
    }
    cout << "Resultant matrix: \n";
    for (i = 0; i < 2; i++) 
    {
        for (j = 0; j < 2; j++) 
        {
            cout << c[i][j] << " ";
        }
        cout << endl;
    }
    return 0;
}
```

**Output:**
![1701869920629](image/shaheer_ali_301221044_labworkDataStructure/1701869920629.png)
---

### Question 14:
Write a C++ program to perform a linear search in an array of ten elements. It should search for a given element and display whether the search was successful along with the location.

**Program:**
```cpp
//to implement multiple linear search
#include<iostream>
using namespace std;
int main()
{
    int x[10], element;
    cout<<"Enter 10 elements: ";
    for(int i=0;i<=9;i++)
    {
        cin>>x[i];
    }
    cout<<"Enter the element to be found: ";
    cin>>element;
    for(int j=0;j<=9;j++)
    {
        if(element==x[j])
        {
            cout<<"Successfully find"<<"\nLocation: "<<j+1;
        }
    }
    return 0;
}
```

**Output:**
![1701870005639](image/shaheer_ali_301221044_labworkDataStructure/1701870005639.png)

---