## 🧮 **Chapter 3 – Expressions and Interactivity**

### 1. Basic Input & Output

**Q1.**
Write a C++ program that asks the user for their name and age, and prints:

> "Hello [name], you are [age] years old."

**Solution**

```cpp
#include <iostream>
#include <string>
using namespace std;

int main() {
    string name;
    int age;
    cout << "Enter your name: ";
    getline(cin, name);
    cout << "Enter your age: ";
    cin >> age;
    cout << "Hello " << name << ", you are " << age << " years old.\n";
    return 0;
}
```

---

### 2. Mathematical Expressions

**Q2.**
Write a program to calculate the area and circumference of a circle given its radius.

**Solution**

```cpp
#include <iostream>
#include <cmath>
using namespace std;

int main() {
    const double PI = 3.14159;
    double r;
    cout << "Enter radius: ";
    cin >> r;
    double area = PI * pow(r, 2);
    double circumference = 2 * PI * r;
    cout << "Area: " << area << "\nCircumference: " << circumference;
}
```

---

### 3. Type Casting

**Q3.**
Write a program to compute the average of two integers but show the result as a floating-point value.

**Solution**

```cpp
#include <iostream>
using namespace std;

int main() {
    int a, b;
    cout << "Enter two integers: ";
    cin >> a >> b;
    double avg = static_cast<double>(a + b) / 2;
    cout << "Average = " << avg;
}
```

---

### 4. Overflow and Underflow

**Q4.**
What is the output?

```cpp
short num = 32767;
num = num + 1;
cout << num;
```

**Solution:**
Output → `-32768` (overflow occurs since short’s range is -32768 to 32767).

---

### 5. Named Constants

**Q5.**
Define a constant `TAX_RATE = 0.075` and compute the total price after tax for an input amount.

**Solution**

```cpp
#include <iostream>
using namespace std;

int main() {
    const double TAX_RATE = 0.075;
    double price;
    cout << "Enter price: ";
    cin >> price;
    cout << "Total with tax: " << price + (price * TAX_RATE);
}
```

---

### 6. String Input

**Q6.**
Differentiate between:

```cpp
cin >> name;
getline(cin, name);
```

**Solution:**

* `cin >> name;` reads a word (stops at space).
* `getline(cin, name);` reads the entire line (can include spaces).

---

### 7. Random Numbers

**Q7.**
Generate a random number between 1 and 6.

**Solution**

```cpp
#include <iostream>
#include <cstdlib>
#include <ctime>
using namespace std;

int main() {
    srand(time(0));
    int num = rand() % 6 + 1;
    cout << "Random number: " << num;
}
```

---

## 🤔 **Chapter 4 – Making Decisions**

### 1. Relational Operators

**Q8.**
Write expressions to check if `x` is greater than or equal to 10 and less than 20.

**Solution**

```cpp
if (x >= 10 && x < 20)
    cout << "x is in range [10,20)";
```

---

### 2. Simple if Statement

**Q9.**
Write a program that prints “You passed” if score ≥ 50.

**Solution**

```cpp
if (score >= 50)
    cout << "You passed!";
```

---

### 3. if/else Statement

**Q10.**
Write a program that prints “Even” if a number is even, otherwise “Odd”.

**Solution**

```cpp
if (num % 2 == 0)
    cout << "Even";
else
    cout << "Odd";
```

---

### 4. if/else if Ladder

**Q11.**
Categorize age as:

* 0–2 → Baby
* 3–12 → Child
* 13–19 → Teen
* 20+ → Adult

**Solution**

```cpp
if (age <= 2)
    cout << "Baby";
else if (age <= 12)
    cout << "Child";
else if (age <= 19)
    cout << "Teen";
else
    cout << "Adult";
```

---

### 5. Nested if

**Q12.**
If score < 100 and score > 90, assign grade ‘A’.

**Solution**

```cpp
if (score < 100)
    if (score > 90)
        grade = 'A';
```

---

### 6. Logical Operators

**Q13.**
Check if `x` is outside 0–100 range.

**Solution**

```cpp
if (x < 0 || x > 100)
    cout << "Invalid value";
```

---

### 7. Input Validation

**Q14.**
Asking the user to enter a positive number, and validate the number.

**Solution**

```cpp
cout << "Enter a positive number: ";
cin >> num;
if(num < 0){
    cout << "Invalid number!";
}else {
    cout << "valid number!";
}
```

---

### 8. switch Statement

**Q15.**
Menu:

1. Add
2. Subtract
3. Multiply
4. Divide

**Solution**

```cpp
#include <iostream>
using namespace std;

int main() {
    int choice, a, b;
    cout << "1.Add\n2.Subtract\n3.Multiply\n4.Divide\nChoice: ";
    cin >> choice;
    cout << "Enter two numbers: ";
    cin >> a >> b;

    switch (choice) {
        case 1: cout << a + b; break;
        case 2: cout << a - b; break;
        case 3: cout << a * b; break;
        case 4: cout << (b != 0 ? (a / (double)b) : 0); break;
        default: cout << "Invalid choice";
    }
}
```

---

### 9. Conditional (Ternary) Operator

**Q16.**
Rewrite the following using `?:`

```cpp
if (x > y)
    max = x;
else
    max = y;
```

**Solution**

```cpp
max = (x > y) ? x : y;
```

---

### 10. Character Testing

**Q17.**
Check if an input character is a letter or digit.

**Solution**

```cpp
#include <iostream>
#include <cctype>
using namespace std;

int main() {
    char ch;
    cin >> ch;
    if (isalnum(ch))
        cout << "Letter or digit";
    else
        cout << "Other";
}
```

---

✅ **Total Concepts Covered**

* `cin`, `cout`, `getline`, `cin.ignore`
* Arithmetic, precedence, and type casting
* Overflow & constants
* Compound assignment
* Formatting (`setw`, `setprecision`)
* Strings & C-strings
* Random numbers
* if / else / nested if / else-if chains
* Logical, relational, and conditional operators
* switch statements & menus
* Input validation
* Character testing (`isalpha`, `isdigit`, etc.)

---

