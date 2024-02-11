# Object Oriented Programming with C++, Lab CS102391

# Experiment 01

## 1. Write a Program to check whether number is prime or no

```c++

#include <iostream>
using namespace std;

class prime{
    int num, count;

public:
    void input(){
        cout << "enter number" << endl;
        cin >> num;
    }

    void check(){
        count = 0;

        for(int i = 1; i <= num; i ++){
            if(num %i == 0){
                count ++;
            }
        }

        if(count == 2){
            cout << num << " is prime number ";
        }else{
            cout << num << " not prime number";
        }
    }
};

int main() {

    prime test;
    test.input();
    test.check();

    return 0;
}

//    output
//    enter number
//    17
//    17 is prime number

```

# Experiment 02

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
    double n1, n2, n3, n4;

    cout << "Enter three numbers: ";
    cin >> n1 >> n2 >> n3 >> n4;

    int a = 75, b = 18, c = 25, d = 98;
    int left_max = max(n1, n2);
    int right_max = max(n3, n4);
    int final_max = max(left_max, right_max);
    cout << "Largest number: " << final_max;
}
```

---

# Experiment 03

## Write a program to find sum of first natural number: sum = 1+2+3 ... 100 by using for and while loop

1 For loop

```cpp

#include <iostream>
using namespace std;

class Natural{
private:
    int res;

public:
    void loop(){
        res = 0;
        for(int i = 1; i<=100; i++){
            res = res + i;
        }

        cout << "The sum of all natural number is " << res;
    }
};


int main(){
    Natural obj;
    obj.loop();
    return 0;
}

// output
// The sum of all natural number is 5050
```

2. While loop

```cpp
#include <iostream>
using namespace std;

class Natural{
private:
    int res;

public:
    void loop(){
        int i = 1;
        res = 0;

        while(i <= 100){
            res = res + i;
            i++;
        }

        cout << "The sum of all natural number is " << res;
    }
};


int main(){
    Natural obj;
    obj.loop();
    return 0;
}

// output
// The sum of all natural number is 5050
```

---

# Experiment 04

## Write a program using switch statement for number calculation:

```cpp
// Program to build a simple calculator using switch Statement
#include <iostream>
using namespace std;

class Claculator{
private:
    char oper;
    float num1, num2;

public:
void input() {
    cout << "Enter an operator (+, -, *, /): ";
    cin >> oper;
    cout << "Enter two numbers: " << endl;
    cin >> num1 >> num2;
}

void process(){
    switch (oper) {
        case '+':
            cout << num1 << " + " << num2 << " = " << num1 + num2;
            break;
        case '-':
            cout << num1 << " - " << num2 << " = " << num1 - num2;
            break;
        case '*':
            cout << num1 << " * " << num2 << " = " << num1 * num2;
            break;
        case '/':
            cout << num1 << " / " << num2 << " = " << num1 / num2;
            break;
        default:
            // operator is doesn't match any case constant (+, -, *, /)
            cout << "Error! The operator is not correct";
            break;
    }

}
};

int main() {
    Claculator obj;
    obj.input();
    obj.process();



    return 0;
}

// Enter an operator (+, -, *, /):+
//  Enter two numbers:
// 5
// 5
// 5 + 5 = 10
```

# Experiment 05

## Write a program to read the element of the given two matrix and to perform the matrix multiplication

```cpp
#include <iostream>
using namespace std;

class Matrix{
private:
    int a[10][10], b[10][10], mul[10][10];
    int r, c, i, j, k;

public:
    void process(){
        cout << "Enter the number of Row = " << endl;
        cin >> r;

        cout << "Enter the number of Column = " << endl;
        cin >> c;

        cout << "Enter the first matrix element = " << endl;
        for(i=0; i<r; i++){
            for(j=0; j<c; j++){
                cin >> a[i][j];
            }
        }

        cout << "Enter the second matrix element " << endl;
        for(i=0; i<r; i++){
            for(j=0; j<c; j++){
                cin >> b[i][j];
            }
        }

        cout << "Multiply of the matrix: " << endl;

        for( i=0; i<r; i++){
            for(j=0; j<c; j++){
                mul[i][j] = 0;
                for(k=0; k<c; k++){
                    mul[i][j] += a[i][k] * b[k][j];
                }
            }
        }


        for(i=0; i<r; i++){
            for(j=0; j<c; j++){
                cout << mul[i][j] << " ";
            }
            cout << endl;
        }
    }
};

int main(){
    Matrix obj;
    obj.process();
    return 0;
}

// output
//    Enter the number of Row =
//    3
//    Enter the number of Column =
//    3
//    Enter the first matrix element =
//    1
//    2
//    3
//    4
//    5
//    6
//    7
//    8
//    9
//    Enter the second matrix element
//    1
//    2
//    3
//    4
//    5
//    6
//    7
//    8
//    9
//    Multiply of the matrix:
//    30 36 42
//    66 81 96
//    102 126 150
```

# Experiment 06

## Write a program to exchange the content of two variable by using a: call by value. b:call by reference

a) Call by value

```cpp
#include <iostream>
using namespace std;

void swap(int , int);

int main(){
    int a, b;
    cout << "Enter the value of a and b " << endl;
    cin >> a >> b;
    cout << "Before swapping: " << endl;
    cout << "The value of a is " << a << endl;
    cout << "The value of b is " << b << endl;

    swap(a, b);


    return 0;
}

void swap(int a, int b){
    int temp = a;
    a = b;
    b = temp;

    cout << "After swapping: " << endl;
    cout << "The value of a is " << a << endl;
    cout << "The value of b is " << b << endl;
}

// output
//    Enter the value of a and b
//    1
//    2
//    Before swapping:
//    The value of a is 1
//    The value of b is 2
//    After swapping:
//    The value of a is 2
//    The value of b is 1
```

---

b) Call by reference

```cpp
#include <iostream>
using namespace std;

void swap(int& , int&);

int main(){
    int a, b;
    cout << "Enter the value of a and b " << endl;
    cin >> a >> b;
    cout << "Before swapping: " << endl;
    cout << "The value of a is " << a << endl;
    cout << "The value of b is " << b << endl;

    swap(a, b);
    cout << "After swapping: " << endl;
    cout << "The value of a is " << a << endl;
    cout << "The value of b is " << b << endl;

    return 0;
}

void swap(int &a, int &b){
    int temp = a;
    a = b;
    b = temp;


}

// output
//    Enter the value of a and b
//    1
//    2
//    Before swapping:
//    The value of a is 1
//    The value of b is 2
//    After swapping:
//    The value of a is 2
//    The value of b is 1
```

# Experiment 07

## Write a program to perform the following arithmetic operations of a complex number using a structure

1. addition of 2 complex number
1. subtraction of 2 complex number
1. multiplication of 2 complex number
1. division of 2 complex number

```cpp
#include<iostream>
using namespace std;

struct Cp{
    float real;
    float img;
};

class Complex{
    Cp a, b, three;

public:
    void input();
    void addition();
    void subtraction();
    void divide();
    void multiply();
    void output();
};

void Complex::input() {
    cout << "Enter real point of 1st number = " << endl;
    cin >> a.real;
    cout << "Enter Imaginary part of 1st number = " << endl;
    cin >> a.img;
    cout << "Your first number is: " << a.real << " i" << a.img << endl;
    cout << "Enter real point part of 2nd number = " << endl;
    cin >> b.real;
    cout << "Enter Imaginary part of 2nd number = ";
    cin >> b.img;
    cout << "Your 2nd number is: " << b.real << " i" << b.img << endl;
}


void Complex::addition() {
    three.real = a.real + b.real;
    three.img = a.img + b.img;
}

void Complex::subtraction() {
    three.real = a.real - b.real;
    three.img = a.img - b.img;
}

void Complex::multiply() {
    three.real = a.real * b.real;
    three.img = a.img * b.img;
}

void Complex::divide() {
    float demo = (b.real * b.real) - (b.img * b.img);
    Cp num;
    num.real = (a.real * b.real) + (a.img * b.real);
    three.real = num.real / demo;
    num.img = (a.img * b.real) - (a.real * b.img);
    three.img = num.img / demo;
}

void Complex::output() {
    cout << "Real part of output is " << three.real << endl;
    cout << "Imaginary part of output is " << three.img << endl;
    cout << "Your output number is: " << three.real << " i" << three.img << endl;
}

int main(){

    Complex obj;
    obj.input();
    int a;
    cout << "What is your choice" << endl;
    cout << "1. Add" << endl << "2. Subtraction" << endl << "3. Multiply" << endl << "4. Divide" << endl;
    cin >> a;
    switch(a){
        case 1: obj.addition();
            break;
        case 2: obj.subtraction();
            break;
        case 3: obj.multiply();
            break;
        case 4: obj.divide();
            break;
    }

    obj.output();

    return 0;

}


// output
//    Enter real point of 1st number =
//    2
//    Enter Imaginary part of 1st number =
//    3
//    Your first number is: 2 i3
//            Enter real point part of 2nd number =
//    5
//    Enter Imaginary part of 2nd number =4
//    Your 2nd number is: 5 i4
//            What is your choice
//    1. Add
//    2. Subtraction
//    3. Multiply
//    4. Divide
//    1
//    Real part of output is 7
//    Imaginary part of output is 7
//    Your output number is: 7 i7
```

# Experiment 08

## Write an OOP using C++ to exchange the private data member of 2 different function using friend function

```cpp
#include<iostream>
using namespace std;

class BDA;

class AI{
private:
    int a;

public:
    AI(){
        a = 30;
    }

    void display1(){
        cout << a << endl;
    }

    friend void swap(AI&, BDA&);
};

class BDA{
private:
    int b;

public:
    BDA(){
        b = 25;
    }

    void display2(){
        cout << b << endl;
    }

    friend void swap(AI&, BDA&);
};


void swap(AI& obj1, BDA& obj2){
    int temp;
    temp = obj1.a;
    obj1.a = obj2.b;
    obj2.b = temp;
}

int main(){
    AI AIobj;
    BDA BDobj;

    cout << "The data before swapping" << endl;
    cout << "AIML data is: " ;
    AIobj.display1();
    cout << endl;
    cout << "BDA data is: ";
    BDobj.display2();
    swap(AIobj, BDobj);
    cout << "The data after swapping " << endl;
    cout << "AI data is ";
    AIobj.display1();
    cout << endl;
    cout << "BDA data is ";
    BDobj.display2();
    return 0;

}

//
//    The data before swapping
//    AIML data is: 30
//    BDA data is: 25
//    The data after swapping
//    AI data is 25
//    BDA data is 30
```

# Experiment 09

## Write an OOP using C++ to count how many time a particular function of class is called

```cpp
#include <iostream>
using namespace std;

class Check{
public:
    static int count;

    void process(){
        count++;
    }
};

int Check::count = 0;

int main(){
    Check obj;
    obj.process();
    obj.process();
    obj.process();
    obj.process();

    Check obj1;
    obj1.process();
    obj1.process();
    obj1.process();
    obj1.process();

    cout << Check::count << endl;
    return 0;
}

void swap(int &a, int &b){
    int temp = a;
    a = b;
    b = temp;


}

// output
// 8
```

# Experiment 10

## Write an OOP using C++ to define a constructor for a "Data" class that initialize the data object with initialize value In case initial value are not provided, it should initialize the objects with default values

```cpp
#include <iostream>
using namespace std;

class Date{
    int dd, mm, yy;
public:
    Date(){
        dd = 24;
        mm = 12;
        yy = 23;
    }

    void input(){
        cout << "enter date: ";
        cin >> dd;

        cout << "enter month: ";
        cin >> mm;

        cout << "enter year: ";
        cin >> yy;
    }

    void output(){
        cout << "DD-MM-YY :: " << dd << "-" << mm << "-" << yy << endl;
    }
};

int main(){
    Date obj;
    obj.input();
    obj.output();
    return 0;
}


// output
//    enter date:6
//    enter month:12
//    enter year:2023
//    DD-MM-YY :: 6-12-2023
```
