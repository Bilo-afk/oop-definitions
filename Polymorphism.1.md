
# 🌀 Polymorphism in C++ | تعدد الأشكال في البرمجة الكائنية (OOP)

---

## 🇬🇧 English Explanation

### 💡 What is Polymorphism?

**Polymorphism** comes from Greek words meaning *"many forms"*.  
In Object-Oriented Programming (OOP), **Polymorphism** allows objects of different classes to respond differently to the same function call.

In simpler terms:  
> The same function behaves **differently** depending on the object that calls it.

---

### 🧩 Real-Life Analogy

Imagine a **"speak()"** action:
- When a **Dog** speaks → it **barks**
- When a **Cat** speaks → it **meows**
- When a **Cow** speaks → it **moos**

Even though the function name is the same (`speak()`), each animal performs a **different behavior**.

This is **Polymorphism** in action — one interface, many implementations.

---

### ⚙️ Example 1: Using Virtual Functions

```cpp
#include <iostream>
using namespace std;

class Animal {
public:
    virtual void speak() { // virtual enables polymorphism
        cout << "Some generic animal sound." << endl;
    }
};

class Dog : public Animal {
public:
    void speak() override {
        cout << "Dog barks!" << endl;
    }
};

class Cat : public Animal {
public:
    void speak() override {
        cout << "Cat meows!" << endl;
    }
};

int main() {
    Animal* animals[3];

    animals[0] = new Animal();
    animals[1] = new Dog();
    animals[2] = new Cat();

    for (int i = 0; i < 3; i++) {
        animals[i]->speak(); // Different output for each class
    }

    for (int i = 0; i < 3; i++) {
        delete animals[i];
    }

    return 0;
}
```

### 🧠 Explanation

- The base class `Animal` has a **virtual function** `speak()`.
- Derived classes (`Dog`, `Cat`) override this function.
- The **same function call** `speak()` produces **different results** depending on the object type.  
  → This is **Runtime Polymorphism** (Dynamic Binding).

---

### ⚙️ Example 2: Function Overloading (Compile-Time Polymorphism)

```cpp
#include <iostream>
using namespace std;

class Calculator {
public:
    int add(int a, int b) {
        return a + b;
    }

    double add(double a, double b) {
        return a + b;
    }

    int add(int a, int b, int c) {
        return a + b + c;
    }
};

int main() {
    Calculator calc;
    cout << calc.add(3, 4) << endl;       // 7
    cout << calc.add(2.5, 4.3) << endl;   // 6.8
    cout << calc.add(1, 2, 3) << endl;    // 6
    return 0;
}
```

### 🧠 Explanation

- Here, **the same function name** `add()` behaves differently depending on the **number** or **type** of parameters.  
- This is called **Compile-Time Polymorphism** (or **Function Overloading**).

---

### ⚖️ Summary Table

| Type | When it Happens | Mechanism | Example |
|------|-----------------|------------|----------|
| **Compile-Time Polymorphism** | During Compilation | Function / Operator Overloading | `add(int, int)` vs `add(double, double)` |
| **Runtime Polymorphism** | During Execution | Virtual Functions & Inheritance | `Animal -> Dog`, `Animal -> Cat` |

---

## 🇸🇦 الشرح بالعربية

### 💡 ما هو تعدد الأشكال (Polymorphism)؟

كلمة **Polymorphism** أصلها يوناني وتعني **“أشكال متعددة”**.  
في البرمجة الكائنية (OOP)، يسمح لنا تعدد الأشكال بأن **تتصرف نفس الدالة بشكل مختلف حسب الكائن** الذي يستدعيها.

بمعنى آخر:
> نفس الدالة، لكن التنفيذ يختلف حسب نوع الكائن.

---

### 🧩 مثال من الحياة الواقعية

تخيل دالة اسمها `speak()`:
- الكلب عندما يتكلم → **ينبح**
- القطة عندما تتكلم → **تموء**
- البقرة عندما تتكلم → **تخوار**

رغم أن اسم الدالة واحد (`speak()`)، إلا أن النتيجة مختلفة — هذا هو **تعدد الأشكال**.

---

### ⚙️ المثال الأول: باستخدام الدوال الافتراضية (Virtual Functions)

```cpp
#include <iostream>
using namespace std;

class Animal {
public:
    virtual void speak() {
        cout << "صوت حيوان عام." << endl;
    }
};

class Dog : public Animal {
public:
    void speak() override {
        cout << "الكلب ينبح!" << endl;
    }
};

class Cat : public Animal {
public:
    void speak() override {
        cout << "القطة تموء!" << endl;
    }
};

int main() {
    Animal* animals[3];

    animals[0] = new Animal();
    animals[1] = new Dog();
    animals[2] = new Cat();

    for (int i = 0; i < 3; i++) {
        animals[i]->speak();
    }

    for (int i = 0; i < 3; i++) {
        delete animals[i];
    }

    return 0;
}
```

### 🧠 الشرح

- الكلاس `Animal` يحتوي على دالة افتراضية `speak()`.  
- الكلاسات المشتقة (`Dog`, `Cat`) تعيد تعريفها.  
- عند استدعاء `speak()` من المؤشر `Animal*`، يتم تنفيذ النسخة الخاصة بكل كلاس.  
  → هذا هو **تعدد الأشكال أثناء التشغيل (Runtime Polymorphism)**.

---

### ⚙️ المثال الثاني: زيادة التحميل (Function Overloading)

```cpp
#include <iostream>
using namespace std;

class Calculator {
public:
    int add(int a, int b) {
        return a + b;
    }

    double add(double a, double b) {
        return a + b;
    }

    int add(int a, int b, int c) {
        return a + b + c;
    }
};

int main() {
    Calculator calc;
    cout << calc.add(3, 4) << endl;       // 7
    cout << calc.add(2.5, 4.3) << endl;   // 6.8
    cout << calc.add(1, 2, 3) << endl;    // 6
    return 0;
}
```

### 🧠 الشرح

- هنا نفس الدالة `add()` تعمل بعدة طرق حسب نوع وعدد المعاملات.  
- هذا يسمى **تعدد الأشكال أثناء الترجمة (Compile-Time Polymorphism)**.

---

### ⚖️ جدول المقارنة

| النوع | وقت التنفيذ | الآلية | المثال |
|--------|-------------|---------|---------|
| **تعدد الأشكال أثناء الترجمة** | وقت الترجمة | زيادة التحميل (Overloading) | `add(int,int)` و `add(double,double)` |
| **تعدد الأشكال أثناء التشغيل** | وقت التشغيل | الوراثة + الدوال الافتراضية | `Animal → Dog`, `Animal → Cat` |

---

💡 **الخلاصة:**  
تعدد الأشكال (Polymorphism) يجعل الكود **مرنًا وقابلًا للتوسع**،  
ويسمح باستخدام نفس الواجهة (مثل `speak()`) لسلوكيات مختلفة حسب نوع الكائن.
