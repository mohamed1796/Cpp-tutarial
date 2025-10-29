## 🧩 **1. Modular Programming**

### **Example:**

```cpp
#include <iostream>
using namespace std;

void printWelcome();
void printGoodbye();

int main() {
    printWelcome();
    cout << "This program demonstrates modular design.\n";
    printGoodbye();
    return 0;
}

void printWelcome() {
    cout << "Welcome to the C++ modular program!\n";
}

void printGoodbye() {
    cout << "Goodbye! Thanks for using this program.\n";
}
```

✅ **Concept:** Splitting code into small, reusable functions.

---

## 🧩 **2. Function Definition and Call**

### **Example:**

```cpp
#include <iostream>
using namespace std;

void displayMessage() {
    cout << "This is a simple function call.\n";
}

int main() {
    displayMessage(); // Function call
    return 0;
}
```

✅ **Concept:** Functions are defined once and called where needed.

---

## 🧩 **3. Function Prototypes**

### **Example:**

```cpp
#include <iostream>
using namespace std;

void greetUser(); // Prototype

int main() {
    greetUser();   // Function call
    return 0;
}

void greetUser() { // Function definition
    cout << "Hello, User!\n";
}
```

✅ **Concept:** A prototype declares a function before its definition.

---

## 🧩 **4. Sending Data into a Function**

### **Example:**

```cpp
#include <iostream>
using namespace std;

void printSum(int a, int b) {
    cout << "Sum = " << a + b << endl;
}

int main() {
    printSum(4, 5);
    return 0;
}
```

✅ **Concept:** Arguments are passed to parameters.

---

## 🧩 **5. Passing Data by Value**

### **Example:**

```cpp
#include <iostream>
using namespace std;

void addTen(int num) {
    num += 10;
}

int main() {
    int x = 5;
    addTen(x);
    cout << "x after addTen: " << x << endl; // Still 5
    return 0;
}
```

✅ **Concept:** Pass-by-value does not modify original variables.

---

## 🧩 **6. The `return` Statement**

### **Example:**

```cpp
#include <iostream>
using namespace std;

void checkValue(int n) {
    if (n < 0) {
        cout << "Negative value!\n";
        return; // Stop execution
    }
    cout << "Value is non-negative.\n";
}
int main() {
    checkValue(-3);
    checkValue(10);
}
```

✅ **Concept:** `return` exits a function early.

---

## 🧩 **7. Returning a Value**

### **Example:**

```cpp
#include <iostream>
using namespace std;

int square(int n) {
    return n * n;
}

int main() {
    cout << "Square of 6 = " << square(6) << endl;
}
```

✅ **Concept:** Functions can return computed values.

---

## 🧩 **8. Returning a Boolean Value**

### **Example:**

```cpp
#include <iostream>
using namespace std;

bool isEven(int n) {
    return n % 2 == 0;
}

int main() {
    if (isEven(8)) cout << "Even\n";
    else cout << "Odd\n";
}
```

✅ **Concept:** Functions can return `true` or `false`.

---

## 🧩 **9. Functions in a Menu-Driven Program**

### **Example:**

```cpp
#include <iostream>
using namespace std;

void add();
void subtract();

int main() {
    int choice;
    cout << "1. Add\n2. Subtract\nChoose: ";
    cin >> choice;

    if (choice == 1) add();
    else if (choice == 2) subtract();
    else cout << "Invalid choice.\n";
}

void add() {
    int a, b;
    cout << "Enter two numbers: ";
    cin >> a >> b;
    cout << "Sum = " << a + b << endl;
}

void subtract() {
    int a, b;
    cout << "Enter two numbers: ";
    cin >> a >> b;
    cout << "Difference = " << a - b << endl;
}
```

✅ **Concept:** Each menu option is handled by a function.

---

## 🧩 **10. Local vs Global Variables**

### **Example:**

```cpp
#include <iostream>
using namespace std;

int globalVar = 100;

void showValues() {
    int localVar = 50;
    cout << "Local = " << localVar << ", Global = " << globalVar << endl;
}

int main() {
    showValues();
    cout << "Global accessible here too: " << globalVar << endl;
}
```

✅ **Concept:** Globals accessible everywhere; locals only within function.

---

## 🧩 **11. Static Local Variables**

### **Example:**

```cpp
#include <iostream>
using namespace std;

void counter() {
    static int count = 0;
    count++;
    cout << "Called " << count << " times.\n";
}

int main() {
    counter();
    counter();
    counter();
}
```

✅ **Concept:** Static variables retain value between calls.

---

## 🧩 **12. Default Arguments**

### **Example:**

```cpp
#include <iostream>
using namespace std;

int multiply(int a, int b = 2) {
    return a * b;
}

int main() {
    cout << multiply(5) << endl;     // Uses default b=2
    cout << multiply(5, 3) << endl;  // Uses provided value
}
```

✅ **Concept:** Default parameter values simplify calls.

---

## 🧩 **13. Passing by Reference**

### **Example:**

```cpp
#include <iostream>
using namespace std;

void swapValues(int &x, int &y) {
    int temp = x;
    x = y;
    y = temp;
}

int main() {
    int a = 10, b = 20;
    swapValues(a, b);
    cout << "a=" << a << ", b=" << b << endl;
}
```

✅ **Concept:** Pass-by-reference modifies original variables.

---

## 🧩 **14. Function Overloading**

### **Example:**

```cpp
#include <iostream>
using namespace std;

int add(int a, int b) { return a + b; }
double add(double a, double b) { return a + b; }

int main() {
    cout << add(3, 4) << endl;
    cout << add(2.5, 4.1) << endl;
}
```

✅ **Concept:** Multiple functions can share the same name but have different parameter lists.

---

## 🧩 **15. The `exit()` Function**

### **Example:**

```cpp
#include <iostream>
#include <cstdlib> // Required for exit()
using namespace std;

void terminateIfNegative(int x) {
    if (x < 0) {
        cout << "Error: Negative input.\n";
        exit(1);
    }
}

int main() {
    terminateIfNegative(-3);
    cout << "This line will never be reached.\n";
}
```

✅ **Concept:** Immediately terminates the program.

---

## 🧩 **16. Stubs and Drivers**

### **Example:**

```cpp
#include <iostream>
using namespace std;

// Stub for feature under development
void featureStub() {
    cout << "[Stub] This feature is not implemented yet.\n";
}

int main() {
    cout << "Testing feature...\n";
    featureStub();  // Driver calls the stub
}
```

✅ **Concept:** Used during development to test program flow.

---
