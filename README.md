# Number Pattern (Diamond Shape) - C++

📌 Project Overview

A C++ program that demonstrates nested loop logic by creating a diamond-shaped number pattern. This project is designed to strengthen understanding of how outer and inner loops interact to generate structured output.

---

🧠 Key Concepts Practiced

Concept Description
Nested Loops Loops within loops — outer loop controls rows, inner loop controls columns/values
Pattern Logic Building ascending and descending number sequences
User Input Using cin to accept a number that determines the pattern size
Output Formatting Using cout and endl for structured display

---

📝 How It Works

The program asks the user to enter a number, which is stored in the variable ris.

```cpp
int ris;
cin >> ris;
```

Example input:

```text
5
```

Then:

```text
ris = 5
```

This value ris becomes the limit for all loops.

---

🔼 1. Ascending Triangle (Number Pyramid)

Code

```cpp
#include <iostream>
using namespace std;

int main() {
    int ris;
    cout << "Enter a number: ";
    cin >> ris;

    // Ascending Triangle
    for (int i = 1; i <= ris; i++) {
        for (int j = 1; j <= i; j++) {
            cout << j;
        }
        cout << endl;
    }

    return 0;
}
```

Output (if ris = 5)

```text
1
12
123
1234
12345
```

How It Works

· Outer loop (i) → determines the number of rows.
· Inner loop (j) → determines how many numbers are printed per row.

Row i Value Inner Loop Runs Output
1 1 1 time 1
2 2 2 times 12
3 3 3 times 123
4 4 4 times 1234
5 5 5 times 12345

---

🔽 2. Descending Triangle

Add this code after the ascending triangle:

Complete Code

```cpp
#include <iostream>
using namespace std;

int main() {
    int ris;
    cout << "Enter a number: ";
    cin >> ris;

    // Ascending Triangle
    for (int i = 1; i <= ris; i++) {
        for (int j = 1; j <= i; j++) {
            cout << j;
        }
        cout << endl;
    }

    // Descending Triangle
    for (int k = ris - 1; k >= 1; k--) {
        for (int l = 1; l <= k; l++) {
            cout << l;
        }
        cout << endl;
    }

    return 0;
}
```

Output (if ris = 5)

```text
1
12
123
1234
12345
1234
123
12
1
```

How the Descending Triangle Works

· Outer loop (k) → starts from ris - 1 and decreases: 4, 3, 2, 1.
· Inner loop (l) → prints numbers from 1 to k.

Row k Value Inner Loop Runs Output
1 4 4 times 1234
2 3 3 times 123
3 2 2 times 12
4 1 1 time 1

---

🔍 3. Why Use l <= k?

```cpp
for (int l = 1; l <= k; l++)
```

This means: While l is less than or equal to k, continue the loop.

Example:

· If k = 4 → Output: 1234 (because the loop runs for 1, 2, 3, 4).

If changed to:

```cpp
for (int l = 1; l <= 1; l++)
```

The output becomes:

```text
1
1
1
1
```

Because the inner loop always runs only once, no matter the value of k.

---

⚖️ 4. Difference Between cout << l and cout << k

Code Output (if k = 4) Explanation
cout << l; 1234 Prints the changing value of l
cout << k; 4444 Prints the fixed value of k repeatedly

---

📊 Final Pattern: Diamond Shape

Combining both triangles creates a diamond/rhombus pattern:

```text
1
12
123
1234
12345
1234
123
12
1
```

---

📌 Summary

Element Description
ris Stores user input; acts as the loop limit
\n / endl Moves to the next line — does NOT change variable values
Outer Loop Controls the number of rows
Inner Loop Controls what gets printed in each row
cout << l Prints a changing number
cout << k Prints the same number repeatedly

---

💡 Learning Outcome

Practicing nested loops is one of the best ways to improve programming logic. This exercise helps develop a deeper understanding of how loops interact and how structured output can be generated through simple control flow.

---

💻 How to Compile & Run

```bash
# Compile
g++ diamond_pattern.cpp -o diamond_pattern

# Run
./diamond_pattern
