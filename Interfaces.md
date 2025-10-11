
# 🧩 Interfaces, Pure Virtual Functions, and Abstract Classes in C++  
## واجهات البرمجة، الدوال الافتراضية البحتة، والفئات المجردة في C++

---

## 🇬🇧 English Explanation

### 💡 What is an Interface / Abstract Class?

In **Object-Oriented Programming (OOP)**, an **Abstract Class** is a class that **cannot be instantiated directly**.  
It acts like a **blueprint** — defining what functions subclasses must implement, **without providing full implementation**.

A **Pure Virtual Function** is a virtual function that has **no definition in the base class**.  
Instead, it forces derived classes to provide their own version.

```cpp
virtual void draw() = 0;
```

The `= 0` syntax makes a function **pure virtual**, and the class containing it becomes **abstract**.

---

### 🧩 Real-Life Analogy

Think of an **interface** as a **contract** or **blueprint**.

For example:  
Imagine an abstract class called **Shape**.  
It says:  
> “Every shape must be able to draw itself.”  

But it doesn’t explain *how* each shape should do it — that’s left for subclasses like **Circle**, **Square**, or **Triangle**.

So:
- `Shape` = contract (abstract class)
- `draw()` = pure virtual function
- `Circle`, `Square` = classes that implement this contract

---

### ⚙️ Example 1: Abstract Class and Pure Virtual Function

```cpp
#include <iostream>
using namespace std;

class Shape {
public:
    // Pure virtual function
    virtual void draw() = 0;

    void info() {
        cout << "This is a shape." << endl;
    }
};

class Circle : public Shape {
public:
    void draw() override {
        cout << "Drawing a Circle!" << endl;
    }
};

class Square : public Shape {
public:
    void draw() override {
        cout << "Drawing a Square!" << endl;
    }
};

int main() {
    Shape* shapes[2];
    shapes[0] = new Circle();
    shapes[1] = new Square();

    for (int i = 0; i < 2; i++) {
        shapes[i]->draw();
    }

    for (int i = 0; i < 2; i++) {
        delete shapes[i];
    }

    return 0;
}
```

### 🧠 Explanation

- The class `Shape` has a **pure virtual function** `draw()`.  
- Because of that, `Shape` becomes an **abstract class**.  
- You cannot create an object of `Shape` directly.  
- Derived classes (`Circle`, `Square`) **must** implement `draw()`.  
- This allows us to use **Polymorphism** to call the correct function dynamically.

---

### ⚙️ Example 2: Interface-Like Behavior

```cpp
#include <iostream>
using namespace std;

// Interface
class Printable {
public:
    virtual void print() = 0; // Pure virtual
};

class Report : public Printable {
public:
    void print() override {
        cout << "Printing Report..." << endl;
    }
};

class Invoice : public Printable {
public:
    void print() override {
        cout << "Printing Invoice..." << endl;
    }
};

int main() {
    Printable* docs[2];
    docs[0] = new Report();
    docs[1] = new Invoice();

    for (int i = 0; i < 2; i++) {
        docs[i]->print();
    }

    for (int i = 0; i < 2; i++) {
        delete docs[i];
    }

    return 0;
}
```

### 🧠 Explanation

- `Printable` acts as an **interface** because it only defines **what** should happen (`print()`), not **how**.  
- Each subclass gives its own version of the behavior.

---

### ⚖️ Summary Table

| Concept | Description | Can be Instantiated? | Example |
|----------|--------------|----------------------|----------|
| **Virtual Function** | Can be overridden | ✅ Yes | `virtual void draw()` |
| **Pure Virtual Function** | Must be overridden | ❌ No | `virtual void draw() = 0;` |
| **Abstract Class** | Contains ≥1 pure virtual function | ❌ No | `Shape`, `Printable` |
| **Interface** | All functions are pure virtual | ❌ No | `Printable` |

---

## 🇸🇦 الشرح بالعربية

### 💡 ما هي الواجهة أو الكلاس المجرد (Interface / Abstract Class)؟

في البرمجة الكائنية (OOP)، الكلاس المجرد هو كلاس **لا يمكن إنشاء كائن منه مباشرة**،  
بل يُستخدم كـ **قالب (Blueprint)** يحدد ما يجب على الكلاسات الأخرى تنفيذه.

الدالة الافتراضية البحتة (Pure Virtual Function) هي دالة **ليس لها تعريف داخل الكلاس الأب**،  
ويجب على الكلاس الابن أن يقوم بتعريفها بنفسه.

```cpp
virtual void draw() = 0;
```

وجود `= 0` يجعل الدالة **افتراضية بحتة**، والكلاس الذي يحتويها يصبح **مجردًا (Abstract)**.

---

### 🧩 مثال من الحياة الواقعية

تخيل أن عندك كلاس اسمه **Shape (شكل)** يقول:
> "كل شكل يجب أن يرسم نفسه."  

لكنه لا يحدد كيف يتم الرسم، هذه مهمة الكلاسات المشتقة مثل:  
**Circle (دائرة)** و **Square (مربع)** و **Triangle (مثلث)**.

- `Shape` → العقد (الكلاس المجرد)  
- `draw()` → الدالة الافتراضية البحتة  
- `Circle`, `Square` → كلاس يطبق هذا العقد

---

### ⚙️ المثال الأول: الكلاس المجرد والدالة الافتراضية البحتة

```cpp
#include <iostream>
using namespace std;

class Shape {
public:
    virtual void draw() = 0;

    void info() {
        cout << "هذا شكل عام." << endl;
    }
};

class Circle : public Shape {
public:
    void draw() override {
        cout << "رسم دائرة!" << endl;
    }
};

class Square : public Shape {
public:
    void draw() override {
        cout << "رسم مربع!" << endl;
    }
};

int main() {
    Shape* shapes[2];
    shapes[0] = new Circle();
    shapes[1] = new Square();

    for (int i = 0; i < 2; i++) {
        shapes[i]->draw();
    }

    for (int i = 0; i < 2; i++) {
        delete shapes[i];
    }

    return 0;
}
```

### 🧠 الشرح

- الكلاس `Shape` يحتوي على دالة افتراضية بحتة `draw()`.  
- لذلك لا يمكن إنشاء كائن من `Shape` مباشرة.  
- الكلاسات المشتقة (`Circle`, `Square`) يجب أن تنفذ الدالة `draw()`.  
- عند استدعاء `draw()` من خلال المؤشر `Shape*`، ينفذ السلوك المناسب حسب نوع الكائن.  

---

### ⚙️ المثال الثاني: الواجهة (Interface)

```cpp
#include <iostream>
using namespace std;

class Printable {
public:
    virtual void print() = 0;
};

class Report : public Printable {
public:
    void print() override {
        cout << "طباعة التقرير..." << endl;
    }
};

class Invoice : public Printable {
public:
    void print() override {
        cout << "طباعة الفاتورة..." << endl;
    }
};

int main() {
    Printable* docs[2];
    docs[0] = new Report();
    docs[1] = new Invoice();

    for (int i = 0; i < 2; i++) {
        docs[i]->print();
    }

    for (int i = 0; i < 2; i++) {
        delete docs[i];
    }

    return 0;
}
```

### 🧠 الشرح

- الكلاس `Printable` يمثل واجهة (Interface) لأنه لا يحتوي على أي تنفيذ فعلي، فقط تعريف لما يجب تنفيذه.  
- كل كلاس مشتق يقوم بتنفيذ الدالة `print()` بطريقة مختلفة.  

---

### ⚖️ جدول المقارنة

| المفهوم | الوصف | هل يمكن إنشاء كائن؟ | المثال |
|----------|--------|----------------------|----------|
| **الدالة الافتراضية** | يمكن إعادة تعريفها في الكلاس الابن | ✅ نعم | `virtual void draw()` |
| **الدالة الافتراضية البحتة** | يجب إعادة تعريفها في الكلاس الابن | ❌ لا | `virtual void draw() = 0;` |
| **الكلاس المجرد** | يحتوي على دالة افتراضية بحتة واحدة على الأقل | ❌ لا | `Shape`, `Printable` |
| **الواجهة (Interface)** | كل الدوال فيه افتراضية بحتة | ❌ لا | `Printable` |

---

💡 **الخلاصة:**  
الـ **Interfaces** و **Abstract Classes** تسمحان بتصميم أنظمة مرنة ومنظمة،  
حيث تحدد القواعد العامة وتترك التفاصيل للكلاسات التي ترث منها.
