# Object Oriented Programming with C++, Lab CS102391

<img src="notes/oops1.png" width="400">   
<img src="notes/oops2.png" width="400">  
<br>
<br>

## 1. Write a Program to check whether number is prime or no

A prime number is a natural number that has only one and itself as factors. This C++ program used to demonstrates how to find out whether a natural number is prime or not.

Examples: 2, 3, 13 are prime numbers.

```c++
#include <iostream>
using namespace std;

int main()
{
    /* variable definition and initialization */
    int n, i, c = 0;

    /* Get user input */
    cout << "Enter any number n: ";
    cin>>n;

    /*logic*/
    for (i = 1; i <= n; i++)
    {
        if (n % i == 0)
        {
           c++;
        }
    }
    if (c == 2)
    {
       cout << "n is a Prime number" << endl;
    }
    else
    {
         cout << "n is not a Prime number" << endl;
    }
    return 0;
}
```

First of all, you have to include the iostream header file using the "include" preceding by # which tells that hat the header file needs to be process before compilation, hence named preprocessor directive. Now, for removing naming conflict you can use namespace statement within a program.

Next, you have to declare three integer type variables 'n', 'i', 'c' and initialize c as 0. Now tell the user to enter any natural number n, using the cout<<""; statement. The 'cin<<' statement will take value from the input device, (here keyboard) and store it to the variable n. Now you have to implement a for - loop which will count from 1 up to n. And within this loop checks whether n divides with i gives value equals to 0 or not. If the condition becomes true increments the value of c.

Now when c == 2, prints that "n is a Prime number" and if c is having value other than 2, prints that "n is not a Prime number". And finally the return 0; statement is used to return an integer type value back to main().

## 2. Write a Program to read number and to display the largest value between:

(a) Two number

```c++
// C++ Program to Find Largest of Two Numbers
#include <iostream>
using namespace std;
int main(){
    int x, y;

    // Asking for input
    cout << "Enter the first number: ";
    cin >> x;
    cout << "Enter the second number: ";
    cin >> y;

    if (x > y){
        cout << x << " is greater than " << y;
    }
    else if (y > x){
        cout << y << " is greater than " << x;
    }
    else{
        cout << "Both are equal";
    }
    return 0;
}
```

---

(b)Three Numbers

```c++
// C++ Program to Find Largest of Three Numbers

#include <iostream>
using namespace std;

int main() {

    double n1, n2, n3;

    cout << "Enter three numbers: ";
    cin >> n1 >> n2 >> n3;

    // check if n1 is the largest number
    if(n1 >= n2 && n1 >= n3)
        cout << "Largest number: " << n1;

    // check if n2 is the largest number
    else if(n2 >= n1 && n2 >= n3)
        cout << "Largest number: " << n2;

    // if neither n1 nor n2 are the largest, n3 is the largest
    else
        cout << "Largest number: " << n3;

    return 0;
}
```

---

(c) Four

```c++
// C++ Program to Find Largest of Four Numbers

#include <iostream>
using namespace std;
int max(int x, int y){
    if(x > y){
        return x;
    }else{
        return y;
    }
}
int main(){
    int a = 75, b = 18, c = 25, d = 98;
    int left_max = max(a, b);
    int right_max = max(c, d);
    int final_max = max(left_max, right_max);
    cout << final_max;
}
```
