# 🚀 42 C++ Class Generator

When you start coding in C++ at 42, you’ll quickly realize:

👉 **“I have to write a LOT of classes…”**

Re-typing the same constructors, destructors, copy constructors, assignment operators, and header guards for every single class is tedious and error-prone. This repository provides two powerful ways to automate C++ class creation, helping you save time and focus on the actual logic.

---

### 📦 Features

-   **Canonical Form Ready:** Automatically generates the four essential functions:
    -   Default Constructor
    -   Copy Constructor
    -   Copy Assignment Operator
    -   Destructor
-   **Automatic Header Guards:** Creates include guards based on your class name to prevent header conflicts.
-   **Debug-Friendly:** Includes `std::cout` messages in constructors and destructors to help you trace object lifetimes.
-   **Two Ways to Work:** Choose between a simple command-line script or powerful, integrated VSCode snippets.

---

## 🖥️ Option 1: The Bash Script (`make_class.sh`)

This method is perfect if you want to generate both the `.hpp` and `.cpp` files from your terminal in one go.

### 📂 Setup

1.  Download the `make_class.sh` script into your project directory.
2.  Open your terminal and make the script executable. This command gives your system permission to run the file as a script.

    ```bash
    chmod +x make_class.sh
    ```

### ⚡ Usage

Run the script from your terminal, followed by the name of your class.

```bash
./make_class.sh MyClass
```

This command will instantly generate two files for you: `MyClass.hpp` and `MyClass.cpp`, fully populated with the necessary boilerplate.

### ✅ Example Output

Here’s what the generated `MyClass.hpp` will look like:

```cpp
// MyClass.hpp
#ifndef MYCLASS_HPP
# define MYCLASS_HPP

# include <iostream>

class MyClass {
  public:
    MyClass();
    MyClass(const MyClass &other);
    MyClass &operator=(const MyClass &other);
    ~MyClass();

  private:
    // Add here
};

#endif // MYCLASS_HPP
```

---

## 🖋️ Option 2: VSCode Snippets (`42header` & `42class`)

If you use Visual Studio Code, snippets are a game-changer. They let you insert pre-made code blocks directly inside your editor just by typing a keyword.
Like when you type if then enter in VSC it generate the code snippet for the if condition. Isn't fun! Let's do it.

### 🔧 How to Install the Snippets

1.  Open Visual Studio Code.
2.  Press **`Ctrl+Shift+P`** (or **`Cmd+Shift+P`** on Mac) to open the Command Palette.
3.  Type **`Configure User Snippets`** and select it.
    
4.  A dropdown will appear. Select **`cpp.json`** (for C++).
5.  VSCode will open a file named `cpp.json`. **Copy the entire content** of the `cpp.json` file from this repository and paste it into the `cpp.json` file you have open.
6.  Save the file. That's it! The snippets are now installed.

### ✨ How to Use the Snippets

You now have two powerful commands available directly in your editor.

#### **Snippet 1: `42header`** (for `.hpp` files)

1.  Create a new header file (e.g., `MyClass.hpp`).
2.  Inside the empty file, type `42header`.
3.  Press **`Tab`** or **`Enter`**.

The entire header boilerplate will appear instantly! The snippet is smart—it uses the filename (`MyClass`) to automatically name your class and header guards.

![GIF showing the 42header snippet expanding in VSCode](https://i.imgur.com/gYJgqf5.gif)

#### **Snippet 2: `42class`** (for `.cpp` files)

1.  Create a new source file (e.g., `MyClass.cpp`).
2.  Inside the empty file, type `42class`.
3.  Press **`Tab`** or **`Enter`**.

The full implementation of the canonical form will be generated. It even automatically includes your corresponding `.hpp` file.

![GIF showing the 42class snippet expanding in VSCode](https://i.imgur.com/k2tZ3bV.gif)

### 💡 Pro Tip: Using Tabstops

The snippets include **tabstops**, which are placeholders you can cycle through using the **`Tab`** key. This lets you quickly jump to the parts of the class you need to customize, like adding member variables or defining copy logic.



---

## 🎯 Which Should You Use?

| Method | Best For | Why? |
| :--- | :--- | :--- |
| **Bash Script** | Quickly scaffolding files from the terminal. | Generates both `.hpp` and `.cpp` at once. Great if you aren't a heavy VSCode user. |
| **VSCode Snippets** | A seamless, in-editor workflow. | Extremely fast and flexible. The tabstops and automatic naming make it feel like magic. |

You can even use both! Generate the base files with the script, then open them in VSCode to continue your work.

---

## 🤝 Contribute

Found a bug or have an idea for an improvement? Feel free to open an issue or submit a pull request. Let's make C++ at 42 a little bit easier for everyone!

