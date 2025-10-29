1. Write a function to check if a year is a leap year
2. Create an overloaded function to find minimum values
3. Write a function using reference parameters to find quotient and remainder
4. Create a function with default arguments for calculating compound interest 
5. Write a function that uses static variables to count vowels across multiple calls 
6. Create overloaded functions to calculate volume of different shapes 
7. Write functions to validate user input with boolean returns
8. Implement a menu-driven program using functions 
---

### ✅ **Full Solution**

```cpp
#include <iostream>
#include <cmath>
#include <string>
using namespace std;

// 1. Function to check if a year is a leap year
bool isLeapYear(int year) {
    return ((year % 4 == 0 && year % 100 != 0) || (year % 400 == 0));
}

// 2. Overloaded function to find minimum values
int findMin(int a, int b) {
    return (a < b) ? a : b;
}
double findMin(double a, double b) {
    return (a < b) ? a : b;
}
int findMin(int a, int b, int c) {
    return min(min(a, b), c);
}

// 3. Function using reference parameters to find quotient and remainder
void divide(int dividend, int divisor, int &quotient, int &remainder) {
    quotient = dividend / divisor;
    remainder = dividend % divisor;
}

// 4. Function with default arguments for calculating compound interest
double compoundInterest(double principal, double rate = 5.0, int time = 2) {
    // CI = P * (1 + r/100)^t - P
    return principal * pow((1 + rate / 100), time) - principal;
}



// 5. Function using static variable to count vowels across multiple calls
int countVowels(const string &text) {
    static int totalVowels = 0;  // persists across calls
    for (char ch : text) {
        ch = tolower(ch);
        if (ch == 'a' || ch == 'e' || ch == 'i' || ch == 'o' || ch == 'u')
            totalVowels++;
    }
    return totalVowels;
}

// 6. Overloaded functions to calculate volume of different shapes
double volume(double radius) {  // Sphere
    return (4.0 / 3.0) * M_PI * pow(radius, 3);
}
double volume(double radius, double height) {  // Cylinder
    return M_PI * pow(radius, 2) * height;
}
double volume(double length, double width, double height) {  // Box
    return length * width * height;
}

// 7. Functions to validate user input with boolean returns
bool isValidPositive(int n) {
    return n > 0;
}
bool isValidRange(int n, int minVal, int maxVal) {
    return n >= minVal && n <= maxVal;
}

// 8. Menu-driven program using functions
void showMenu() {
    cout << "\nMenu:\n";
    cout << "1. Check Leap Year\n";
    cout << "2. Find Minimum\n";
    cout << "3. Divide Two Numbers\n";
    cout << "4. Calculate Compound Interest\n";
    cout << "5. Count Vowels in String\n";
    cout << "6. Calculate Volume\n";
    cout << "7. Validate Input\n";
    cout << "8. Exit\n";
}

int main() {
    int choice;
    do {
        showMenu();
        cout << "Enter choice: ";
        cin >> choice;

        switch (choice) {
            case 1: {
                int year;
                cout << "Enter year: ";
                cin >> year;
                cout << (isLeapYear(year) ? "Leap Year" : "Not Leap Year") << endl;
                break;
            }
            case 2: {
                int a, b, c;
                cout << "Enter three integers: ";
                cin >> a >> b >> c;
                cout << "Minimum value: " << findMin(a, b, c) << endl;
                break;
            }
            case 3: {
                int dividend, divisor, q, r;
                cout << "Enter dividend and divisor: ";
                cin >> dividend >> divisor;
                divide(dividend, divisor, q, r);
                cout << "Quotient: " << q << ", Remainder: " << r << endl;
                break;
            }
            case 4: {
                double principal, rate;
                int time;
                cout << "Enter principal, rate(%), and time(years): ";
                cin >> principal >> rate >> time;
                cout << "Compound Interest: " << compoundInterest(principal, rate, time) << endl;
                break;
            }
            case 5: {
                string text;
                cout << "Enter text: ";
                cin.ignore();
                getline(cin, text);
                cout << "Total vowels (all calls): " << countVowels(text) << endl;
                break;
            }
            case 6: {
                cout << "Choose shape: 1.Sphere 2.Cylinder 3.Box: ";
                int shape;
                cin >> shape;
                if (shape == 1) {
                    double r;
                    cout << "Enter radius: ";
                    cin >> r;
                    cout << "Volume of Sphere: " << volume(r) << endl;
                } else if (shape == 2) {
                    double r, h;
                    cout << "Enter radius and height: ";
                    cin >> r >> h;
                    cout << "Volume of Cylinder: " << volume(r, h) << endl;
                } else if (shape == 3) {
                    double l, w, h;
                    cout << "Enter length, width, height: ";
                    cin >> l >> w >> h;
                    cout << "Volume of Box: " << volume(l, w, h) << endl;
                } else {
                    cout << "Invalid choice.\n";
                }
                break;
            }
            case 7: {
                int num;
                cout << "Enter number to validate (1-100): ";
                cin >> num;
                if (isValidPositive(num) && isValidRange(num, 1, 100))
                    cout << "Valid input.\n";
                else
                    cout << "Invalid input.\n";
                break;
            }
            case 8:
                cout << "Exiting program.\n";
                break;
            default:
                cout << "Invalid choice. Try again.\n";
        }
    } while (choice != 8);

    return 0;
}
```

---

### 🧩 **Explanation by Question**

| # | Concept                  | Explanation                                                               |
| - | ------------------------ | ------------------------------------------------------------------------- |
| 1 | **Leap year check**      | Uses divisibility rules: divisible by 4, not by 100, unless by 400.       |
| 2 | **Function overloading** | Demonstrates overloaded `findMin()` for `int` and `double`.               |
| 3 | **Reference parameters** | Passes `quotient` and `remainder` by reference to modify values directly. |
| 4 | **Default arguments**    | Function `compoundInterest()` works even if rate/time are not passed.     |
| 5 | **Menu-driven**          | Uses a `do-while` loop to repeatedly execute based on user choice.        |
| 6 | **Static variable**      | Keeps count of vowels across multiple calls, not reset after each.        |
| 7 | **Overloading again**    | Calculates volume of sphere, cylinder, and box with different signatures. |
| 8 | **Boolean validation**   | Returns `true` or `false` for positive/range checks.                      |

---

### 📚 References

* [C++ Reference – Functions](https://en.cppreference.com/w/cpp/language/functions)
* [C++ Reference – Function Overloading](https://en.cppreference.com/w/cpp/language/overload_resolution)
* [C++ Reference – Static Variables](https://en.cppreference.com/w/cpp/language/storage_duration#Static_local_variables)
* [C++ Reference – Default Arguments](https://en.cppreference.com/w/cpp/language/default_arguments)

---
