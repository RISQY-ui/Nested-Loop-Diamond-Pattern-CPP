# Number Pattern (Diamond Shape) - C++

---

## 📌 Project Overview

A C++ program that demonstrates nested loop logic by creating a diamond-shaped number pattern. This project is designed to strengthen understanding of how outer and inner loops interact to generate structured output.

---

## 🧠 Key Concepts Practiced

| Concept | Description |
|---------|-------------|
| **Nested Loops** | Loops within loops — outer loop controls rows, inner loop controls columns/values |
| **Pattern Logic** | Building ascending and descending number sequences |
| **User Input** | Using `cin` to accept a number that determines the pattern size |
| **Output Formatting** | Using `cout` and `endl` for structured display |

---

## 📝 How It Works

The program asks the user to enter a number, which is stored in the variable `ris`.

```cpp
int ris;
cin >> ris;
```

### Example Input

```
5
```

Then:

```
ris = 5
```

This value `ris` becomes the limit for all loops.

---

## 🔼 1. Ascending Triangle (Number Pyramid)

### Code

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

### Output (if ris = 5)

```
1
12
123
1234
12345
```

### How It Works

| Element | Description |
|---------|-------------|
| **Outer loop (i)** | Determines the number of rows |
| **Inner loop (j)** | Determines how many numbers are printed per row |

### Step-by-Step Execution

| Row | i Value | Inner Loop Runs | Output |
|-----|---------|-----------------|--------|
| 1 | 1 | 1 time | `1` |
| 2 | 2 | 2 times | `12` |
| 3 | 3 | 3 times | `123` |
| 4 | 4 | 4 times | `1234` |
| 5 | 5 | 5 times | `12345` |

---

## 🔽 2. Descending Triangle

Add this code after the ascending triangle:

### Complete Code

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

    cout << endl;  // Empty line for spacing

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

### Output (if ris = 5)

```
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

### How the Descending Triangle Works

| Element | Description |
|---------|-------------|
| **Outer loop (k)** | Starts from `ris - 1` and decreases: 4, 3, 2, 1 |
| **Inner loop (l)** | Prints numbers from 1 to `k` |

### Step-by-Step Execution

| Row | k Value | Inner Loop Runs | Output |
|-----|---------|-----------------|--------|
| 1 | 4 | 4 times | `1234` |
| 2 | 3 | 3 times | `123` |
| 3 | 2 | 2 times | `12` |
| 4 | 1 | 1 time | `1` |

---

## 🔍 3. Why Use l <= k?

```cpp
for (int l = 1; l <= k; l++)
```

**Meaning:** While `l` is less than or equal to `k`, continue the loop.

### Example

- If `k = 4` → Output: `1234` (because the loop runs for 1, 2, 3, 4)
- If changed to `for (int l = 1; l <= 1; l++)` → Output becomes:
  ```
  1
  1
  1
  1
  ```
  Because the inner loop always runs only once, no matter the value of `k`.

---

## ⚖️ 4. Difference Between cout << l and cout << k

| Code | Output (if k = 4) | Explanation |
|------|-------------------|-------------|
| `cout << l;` | `1234` | Prints the **changing** value of `l` |
| `cout << k;` | `4444` | Prints the **fixed** value of `k` repeatedly |

### Visual Comparison

**Using cout << l:**
```cpp
for (int l = 1; l <= 4; l++)
    cout << l;  // Prints: 1234
```

**Using cout << k:**
```cpp
for (int l = 1; l <= 4; l++)
    cout << k;  // Prints: 4444 (if k = 4)
```

---

## 📊 Final Pattern: Diamond Shape

Combining both triangles creates a diamond/rhombus pattern:

```
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

## 🎨 Variations to Explore

### Variation 1: Reverse Numbers

```cpp
for (int j = i; j >= 1; j--) {
    cout << j;
}
```

**Output (if ris = 5):**
```
1
21
321
4321
54321
```

### Variation 2: Only Odd Numbers

```cpp
for (int j = 1; j <= i; j += 2) {  // Increment by 2
    cout << j;
}
```

**Output (if ris = 5):**
```
1
13
135
1357
13579
```

### Variation 3: Stars Instead of Numbers

```cpp
for (int j = 1; j <= i; j++) {
    cout << "*";
}
```

**Output (if ris = 5):**
```
*
**
***
****
*****
****
***
**
*
```

---

## 📌 Summary

| Element | Description |
|---------|-------------|
| **ris** | Stores user input; acts as the loop limit |
| **\n / endl** | Moves to the next line — does NOT change variable values |
| **Outer Loop** | Controls the number of rows |
| **Inner Loop** | Controls what gets printed in each row |
| **cout << l** | Prints a **changing** number |
| **cout << k** | Prints the **same** number repeatedly |

---

## 🧮 Tracing Through Example

**Input:** `ris = 3`

### Ascending Part

```
i=1: j loops (1 to 1)  → Output: 1
i=2: j loops (1 to 2)  → Output: 12
i=3: j loops (1 to 3)  → Output: 123
```

### Descending Part

```
k=2: l loops (1 to 2)  → Output: 12
k=1: l loops (1 to 1)  → Output: 1
```

### Final Output

```
1
12
123
12
1
```

---

## 💡 Learning Outcome

Practicing nested loops is one of the best ways to improve programming logic. This exercise helps develop a deeper understanding of:

- How loops interact with each other
- How structured output can be generated through simple control flow
- The relationship between loop variables and output
- Pattern recognition in programming

---

## 💻 How to Compile & Run

### Linux/Mac

```bash
# Compile
g++ diamond_pattern.cpp -o diamond_pattern

# Run
./diamond_pattern
```

### Windows

```bash
# Compile
g++ diamond_pattern.cpp -o diamond_pattern.exe

# Run
diamond_pattern.exe
```

### Termux (Android)

```bash
# Compile
g++ diamond_pattern.cpp -o diamond_pattern

# Run
./diamond_pattern
```

---

## ✅ Checklist

| Item | Status |
|------|--------|
| Understand nested loops | ✅ |
| Can write ascending pattern | ✅ |
| Can write descending pattern | ✅ |
| Understand loop variables | ✅ |
| Can create variations | ✅ |

---

**Last Updated:** June 2026

**Difficulty Level:** Beginner to Intermediate

**Time to Master:** 1-2 hours
