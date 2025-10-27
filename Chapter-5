## 🧩 **Chapter 5 Practice — Looping (C++)**

### 1️⃣ **The while Loop**

**Example:**
Write a program that prints numbers from 10 down to 1 using a `while` loop.

**Solution:**

```cpp
#include <iostream>
using namespace std;

int main() {
    int num = 10;
    while (num >= 1) {
        cout << num << " ";
        num--;   // decrement control variable
    }
    return 0;
}
```

✅ *Explanation:*
The loop runs while `num >= 1`. Each iteration decrements `num`, ensuring the condition eventually becomes false.

---

### 2️⃣ **Input Validation Using while**

**Example:**
Ask the user to enter a positive integer. Repeat until they enter a number > 0.

**Solution:**

```cpp
int n;
cout << "Enter a positive integer: ";
cin >> n;

while (n <= 0) {
    cout << "Invalid! Enter again: ";
    cin >> n;
}
cout << "You entered: " << n;
```

✅ *Explanation:*
The loop continues until valid input is provided.

---

### 3️⃣ **Increment and Decrement Operators**

**Example:**
Predict the output.

```cpp
int x = 2, y = 3;
cout << ++x << " " << y++ << " " << y;
```

**Solution:**
Output → `3 3 4`
✅ *Explanation:*
`++x` increments before printing.
`y++` prints old value then increments.

---

### 4️⃣ **Counters and Running Totals**

**Example:**
Compute the sum of numbers 1 through 5 using a loop.

**Solution:**

```cpp
int sum = 0, i = 1;
while (i <= 5) {
    sum += i;
    i++;
}
cout << "Sum = " << sum;   // Output: 15
```

✅ *Concept:* Counter-controlled loop using accumulator `sum`.

---

### 5️⃣ **Sentinel-Controlled Loop**

**Example:**
Ask user for numbers; stop when they enter `-1`, then display total.

**Solution:**

```cpp
int total = 0, num;
cout << "Enter numbers (-1 to stop): ";
cin >> num;

while (num != -1) {
    total += num;
    cin >> num;
}

cout << "Total = " << total;
```

✅ *Concept:* `-1` is a *sentinel* — a special value marking end of input.

---

### 6️⃣ **do-while Loop**

**Example:**
Display a menu until the user chooses to quit.

**Solution:**

```cpp
char choice;
do {
    cout << "\nMenu:\n1. Play\n2. Quit\nChoice: ";
    cin >> choice;
} while (choice != '2');
```

✅ *Concept:* Executes at least once regardless of condition.

---

### 7️⃣ **for Loop**

**Example:**
Print even numbers from 2 to 10.

**Solution:**

```cpp
for (int i = 2; i <= 10; i += 2)
    cout << i << " ";
```

✅ *Concept:* Compact syntax for counter-controlled repetition.

---

### 8️⃣ **Nested Loops**

**Example:**
Display a 3×3 multiplication table.

**Solution:**

```cpp
for (int r = 1; r <= 3; r++) {
    for (int c = 1; c <= 3; c++) {
        cout << r * c << "\t";
    }
    cout << endl;
}
```

✅ *Concept:* Inner loop runs completely for each iteration of the outer loop.

---

### 9️⃣ **Break and Continue**

**Example:**
Find the first number divisible by 7 between 1–20.

**Solution:**

```cpp
for (int i = 1; i <= 20; i++) {
    if (i % 7 == 0) {
        cout << "Found: " << i;
        break;
    }
}
```

✅ *Concept:* `break` exits the loop immediately.

---

**Example (continue):**
Skip even numbers and print only odd ones.

```cpp
for (int i = 1; i <= 10; i++) {
    if (i % 2 == 0) continue;
    cout << i << " ";
}
```

---

### 🔟 **File Input and Output**

**Example:**
Write 5 numbers to a file and read them back.

**Solution:**

```cpp
#include <iostream>
#include <fstream>
using namespace std;

int main() {
    ofstream outFile("data.txt");
    for (int i = 1; i <= 5; i++) outFile << i << " ";
    outFile.close();

    ifstream inFile("data.txt");
    int num, sum = 0;
    while (inFile >> num)
        sum += num;
    cout << "Sum from file: " << sum;
    inFile.close();
}
```

✅ *Concept:* Use `<fstream>` with `ofstream` and `ifstream`.
Check for EOF using `while (inFile >> num)`.

---

### 11️⃣ **Creating Good Test Data**

**Example:**
Suppose you’re testing an input validation loop for an age (1–120).
Good test data includes:

* Normal: `25`
* Boundary: `1`, `120`
* Invalid: `-5`, `130`, `0`, `abc`

✅ *Concept:* Test data should cover **normal**, **boundary**, and **invalid** cases.

---

## 📘 **Summary Practice Challenge**

**Task:**
Write a C++ program that:

1. Prompts the user to enter test scores (0–100).
2. Uses input validation.
3. Uses a sentinel (-1) to stop input.
4. Calculates average score.
5. Outputs to a file named `report.txt`.

**Solution (complete):**

```cpp
#include <iostream>
#include <fstream>
using namespace std;

int main() {
    int score, total = 0, count = 0;

    cout << "Enter test scores (0–100), -1 to stop:\n";
    cin >> score;

    while (score != -1) {
        while (score < 0 || score > 100) {
            cout << "Invalid. Enter score (0–100): ";
            cin >> score;
        }
        total += score;
        count++;
        cin >> score;
    }

    if (count > 0) {
        double avg = static_cast<double>(total) / count;
        cout << "Average = " << avg << endl;

        ofstream outFile("report.txt");
        outFile << "Scores entered: " << count << endl;
        outFile << "Average score: " << avg << endl;
        outFile.close();
    } else {
        cout << "No scores entered.\n";
    }
}
```

✅ Covers: while loop, input validation, sentinel, counter, accumulator, file output.

---
