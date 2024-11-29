
# GeminiScript Documentation - Version 1.2

**Update Name:** "Equinox"

Version 1.2 of GeminiScript, codename *Equinox*, introduces several significant improvements to the language. This update addresses bug fixes, enhances variable type-checking, optimizes constant handling, and refines variable declaration controls. Additionally, it improves the flow control mechanism, increasing the readability and robustness of the language.

---

## **Major Changes**

### **1. Variable Typing and Assignments**
- **Type Checking Fixes**: Prior to version 1.2, the type of a variable was not strictly enforced, which led to type errors during execution. Now, the language checks whether the value assigned to a variable matches the expected type. For example, a `Number` variable can only hold valid integer numbers.

  - **Before**: 
    ```plaintext
    let Number age = "30"  # Accepted string
    ```
  - **After**:
    ```plaintext
    let Number age = "30"  # Error: Expected a valid Number
    ```

### **2. Constant Reassignment**
- **Improved Constant Control**: Variables declared with `let` are now treated as constants, preventing their reassignment after declaration. If a programmer attempts to reassign a constant, an error is thrown.

  - **Before**:
    ```plaintext
    let Number age = 25
    age = 30  # Allowed reassignment
    ```
  - **After**:
    ```plaintext
    let Number age = 25
    age = 30  # Error: Cannot reassign value to constant age
    ```

### **3. Variable Declaration and Typing**
- **Explicit Type Declarations**: Variables now need to be explicitly declared with a specific type like `Number`, `String`, or `Boolean`, and values of incorrect types will trigger informative error messages.

  - **Supported Types**:
    - `Number`: For integer numbers.
    - `String`: For text (must be enclosed in quotes).
    - `Boolean`: For `True` or `False` values.

  - **Before**:
    ```plaintext
    let z = "string"  # Type not specified
    ```
  - **After**:
    ```plaintext
    let Number z = "string"  # Error: Invalid value for z of type Number
    ```

### **4. Flow Control and Conditional Blocks**
- **Optimized Flow Control (if/else)**: The `if` and `else` blocks are now accurately identified and controlled by a stack that ensures proper conditional execution. This improves the understanding of control flow and avoids logical errors.

  - **Before**:
    ```plaintext
    if (True)
        print("True block")
    else
        print("False block")
    ```
  - **After**:
    ```plaintext
    if (True)
        print("True block")
    else
        print("False block")
    # Now the flow is properly validated, and the else block only executes after a clear check.
    ```

### **5. Strict Operation Validation**
- **List Manipulation (push/pop)**: Operations like `push` and `pop` on lists were refined to ensure that the list is defined and exists before attempting to modify its values.

  - **Before**:
    ```plaintext
    let List myList = []
    push(myList, 10)  # Accepted without validation
    ```
  - **After**:
    ```plaintext
    let List myList = []
    push(myList, 10)  # Now the operation checks if myList is a defined list
    ```

### **6. Enhanced Error Messages**
- **Type and Definition Errors**: Version 1.2 introduces more descriptive error messages. When a type error occurs, the message clearly specifies the expected data type.

  - **Example**:
    ```plaintext
    Error: Invalid value for z. Expected a Number.
    ```

---

## **Removed or Refined Features**

- **Implicit Types Removal**: In version 1.2, the language was optimized to avoid automatic type inference. Previously, code could run even if the typing wasn't correctly specified, leading to execution problems. Now, typing is mandatory and explicit.
  
  - **Before**:
    ```plaintext
    let age = 25  # Implicit type
    ```
  - **After**:
    ```plaintext
    let Number age = 25  # Explicit type declaration
    ```

- **Refined Flow Control Syntax**: The `if` control syntax was refined to ensure that all control blocks are correctly followed, eliminating "orphaned" blocks that could execute incorrectly.

---

## **New Features**

- **Type Check on Assignments**: A new type-checking mechanism was added for variable assignments, ensuring that the values match the declared type.
  
  - **Example**:
    ```plaintext
    let Number age = "25"  # Type error
    let Boolean isActive = "true"  # Error: Expected True or False
    ```

- **Stack-based Conditional Flow Control**: The conditional flow control now uses a stack to ensure that `if` and `else` blocks are paired correctly, avoiding the execution of incorrect blocks.

---

## **Backward Compatibility**

Version 1.2 is **not compatible** with previous versions of the language due to substantial changes in typing and flow control. Adapting old code to ensure compatibility with the new version is recommended.

---

## **GeminiScript Mini Tutorial**

**Objective**: Learn the basic concepts of the GeminiScript language, such as variable declarations, flow control, and basic operations.

### **1. Variable Declarations**

In GeminiScript, you need to declare variables with a specific type. There are three main types of variables:

- **Number**: Used for integer numbers.
- **String**: Used for text.
- **Boolean**: Used for logical values `True` or `False`.

**Example**:
```plaintext
let Number age = 25
let String name = "Alice"
let Boolean isActive = True
```

### **2. Basic Operations**

You can perform arithmetic operations, such as addition, subtraction, multiplication, and division, on number variables.

**Example**:
```plaintext
let Number x = 10
let Number y = 5
let Number result = x + y
print(result)  # Output: 15
```

### **3. Flow Control (if/else)**

Flow control is done using the `if` and `else` keywords. The `if` block executes the code if the condition is `True`, and the `else` block executes if the condition is `False`.

**Example**:
```plaintext
let Boolean isSunny = True

if (isSunny)
    print("It's sunny today!")
else
    print("It's cloudy today!")
```

### **4. Lists and Manipulation**

You can use lists to store multiple values and perform operations like adding (`push`) or removing (`pop`) elements.

**Example**:
```plaintext
let List numbers = [1, 2, 3]
push(numbers, 4)
pop(numbers)  # Removes the last value
print(numbers)  # Output: [1, 2, 3]
```

### **5. Functions**

Functions allow you to group a set of instructions and reuse them.

**Example**:
```plaintext
function greet(name)
    print("Hello, " + name + "!")
end

greet("Alice")  # Output: Hello, Alice!
```

---

With this mini tutorial, you learned how to declare variables, use specific types, perform basic arithmetic operations, control flow with `if` and `else`, manipulate lists, and create functions. GeminiScript is designed to be simple and powerful, allowing quick and secure scripting for automation and data manipulation.
