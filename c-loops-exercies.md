# C Loops Exercises


## 1. Print a Growing Triangle of Asterisks (using a `for` loop)
**Level: Easy**  

**Goal:**  
Ask the user for a positive integer `n`, then use a `for` loop to print a “triangle” of asterisks where the first row has 1 `*`, the second row has 2 `*`, and so on up to `n` rows.

<details>
<summary>Instructions:</summary>

  1. Prompt the user to enter a positive integer `n`.
  2. Use a `for` loop that runs from `i = 1` up to `i = n`.
  3. Inside the loop, use another `for` loop (or any method you prefer) to print `i` asterisks on one line.
  4. After printing each row of asterisks, move to a new line.
</details>

* **Example:**

  ```c
  Enter a positive number: 3
  *
  **
  ***
  ```

---

### 2. Print a Shrinking Triangle of Asterisks (using a `for` loop)
**Level: Easy**

**Goal:**  
Building on Exercise 1, ask the user for a positive integer `n` and then use a `for` loop to print a triangle of asterisks that starts with `n` asterisks on the first line, then `n–1` on the next, down to 1.


<details>
<summary>Instructions:</summary>

  1. Prompt the user to enter a positive integer `n`.
  2. Use a `for` loop that runs from `i = n` down to `i = 1`.
  3. Inside that loop, print `i` asterisks on one line.
  4. After printing each row, move to a new line.
</details>

* **Example:**

  ```c
  Enter a positive number: 4
  ****
  ***
  **
  *
  ```

---

### 3. Keep Asking Until a Positive Number Is Entered (using a `do–while` loop)
**Level: Easy**

**Goal:**  
Write a program that forces the user to enter a positive integer. If they enter zero or a negative number, the program must ask again. Use a `do–while` loop so that the prompt always appears at least once.

* **Instructions:**

  1. Declare an integer variable `num`.
  2. <details>
     <summary>Hint 1: hot to use do-while loop</summary>

      Use a `do { … } while (condition);` structure:
      ```c
      do {
        // code to be executed
      } while (condition);
      ```
      * Inside the `do` block, print a message like `"Please enter a positive integer: "` and read `num`.  
      * The `while` condition should check if `num <= 0`. If it is, the loop repeats.
     </details>
  3. When the user finally enters something greater than 0, exit the loop and print a confirmation message, like:  
     `"You entered: [num]"`.

* **Example Run:**

  ```c
  Please enter a positive integer: -5
  Invalid input. Please enter a positive integer: 0
  Invalid input. Please enter a positive integer: 7
  You entered: 7
  ```

---

### 4. Sum Numbers Until the User Enters 0 (using a `while` loop)
**Level: Easy**  

**Goal:**  
Continuously read integer values from the user and keep a running sum. Stop asking when the user enters `0`, then print the total sum (excluding the final `0`). Use a `while` loop.

<details>
<summary>Instructions:</summary>

  1. Initialize two integer variables: `sum = 0` and `value`.
  2. Prompt the user with `"Enter an integer (0 to finish): "` before the loop.
  3. Use a `while` loop that continues as long as `value` is not `0`.

     * Inside the loop, add `value` to `sum`.
     * Then prompt again and read the next `value`.
  4. Once `value` is `0`, exit the loop and print `"Total sum is: [sum]"`.
</details>

* **Example Run:**

  ```
  Enter an integer (0 to finish): 5
  Enter an integer (0 to finish): -2
  Enter an integer (0 to finish): 10
  Enter an integer (0 to finish): 0
  Total sum is: 13
  ```

---

### 5. Mini Calculator Menu (using a `while` loop + `switch`)
**Level: Medium**  

**Goal:**  
Build a simple calculator that keeps asking the user to choose an operator until they enter `0` to exit. Supported operators are:

* `1` => add `a + b`
* `2` => subtract `a - b`
* `3` => multiply `a * b`

If the user picks an operator outside `0–3`, print a “Supported operators” message and loop again. Whenever they choose `1, 2, or 3`, prompt for two numbers `a` and `b`, perform the calculation, display the result, and then ask for the operator again.


<details>
<summary>Instructions:</summary>

  1. In `main`, declare three integers: `operator`, `a`, and `b`.
  2. Use a `while (1)` loop to keep the menu running until the user picks `0`.
  3. At the top of the loop, print:

     ```
     Please enter the operator:
     ```

     then read `operator`.
  4. Use a `switch (operator)` (or `if–else` chain) to handle each case:

     * **Case 0:**

       * Print `"Bye!"` and use `break` (or `return 0;`) to exit the loop/program.
     * **Case 1, 2, 3:**

       * Print `"Please enter a and b:"`, then read `a` and `b`.
       * Compute the result:

         * If `operator == 1`, do `res = a + b`, then print `"The result of a + b is: [res]"`.
         * If `operator == 2`, do `res = a - b`, then print `"The result of a - b is: [res]"`.
         * If `operator == 3`, do `res = a * b`, then print `"The result of a * b is: [res]"`.
       * After printing, loop back to ask for the operator again.
     * **Default (anything else):**

       * Print exactly:

         ```
         Supported operators: 0 => exit calculator, 1 => a + b, 2 => a - b, 3 => a * b
         ```
       * Then loop back to ask for the operator again.
</details>
* **Example Run:**

  ```
  Please enter the operator:
  1
  Please enter a and b:
  3 5
  The result of 3 + 5 is: 8
  Please enter the operator:
  2
  Please enter a and b:
  2 8
  The result of 2 - 8 is: -6
  Please enter the operator:
  3
  Please enter a and b:
  3 6
  The result of 3 * 6 is: 18
  Please enter the operator:
  7
  Supported operators: 0 => exit calculator, 1 => a + b, 2 => a - b, 3 => a * b
  Please enter the operator:
  0
  Bye!
  ```

---

**Tips for Beginners:**

* Always include `#include <stdio.h>` at the top of your `.c` file so you can use `printf` and `scanf`.
* Don’t forget to check that loops have the correct starting and ending conditions—off‐by‐one errors are common when you’re new.
* When you nest loops (Exercise 1 and 2), make sure the inner loop’s variable doesn’t interfere with the outer loop’s variable. For example, use `for (int i = 1; …)` in the outer loop and `for (int j = 1; …)` in the inner loop.
* For Exercise 5, you can use a `switch` statement on `operator`, or an `if–else if–else` chain—either is fine for now.

Good luck, and have fun practicing your loops!
