
<h1 align="center">🧠 Abstraction in C++ | التجريد في لغة C++</h1>

---

## 🇦🇪 الشرح باللغة العربية

### 🎩 ما هو التجريد (Abstraction)؟

تخيل نفسك تقود سيارة:
- تضغط على البنزين.
- تلف المقود.
- تشغل السيارة.

لكن هل تعرف كيف يعمل المحرك بالضبط؟ لا!  
أنت تستخدم السيارة بسهولة **بدون معرفة التفاصيل الداخلية**.

وهذا بالضبط ما يعنيه **التجريد** في البرمجة:  
> "إظهار الضروري فقط، وإخفاء التعقيد".

### 🔍 ما الذي يعنيه ذلك في C++؟

- نحدد شكل عام (واجهة) للفئة.
- لا نعرض التفاصيل الداخلية.
- من يستخدم الكود يتعامل فقط مع الشكل الخارجي للدوال، وليس كيف تعمل.

### ✅ الفائدة:

- تقليل التعقيد.
- تسهيل الاستخدام والصيانة.
- تنظيم الكود.

### 🧰 مثال بلغة C++ باستخدام فئة مجردة (abstract class)

```cpp
#include <iostream>
using namespace std;

// فئة مجردة
class Animal {
public:
    virtual void makeSound() = 0; // دالة مجردة
};

// فئة الكلب
class Dog : public Animal {
public:
    void makeSound() override {
        cout << "هو هو! 🐶\n";
    }
};

// فئة القطة
class Cat : public Animal {
public:
    void makeSound() override {
        cout << "مياو! 🐱\n";
    }
};

int main() {
    Dog d;
    Cat c;
    d.makeSound(); // صوت الكلب
    c.makeSound(); // صوت القطة
    return 0;
}
```

### 📌 جدول التلخيص:

| الشيء الحقيقي       | في البرمجة               |
|--------------------|--------------------------|
| تستخدم السيارة      | تستخدم الدالة فقط         |
| لا تعرف المحرك      | لا تعرف تفاصيل التنفيذ     |
| المقود، البنزين      | واجهة بسيطة (دوال مجردة)   |
| المحرك معقد         | التفاصيل مخفية (implementation) |

---

## 🇺🇸 Explanation in English

### 🎩 What is Abstraction?

Think of driving a car:
- You press the accelerator.
- You turn the wheel.
- You start the engine.

But do you know how the engine works exactly? No!  
You use the car **without knowing the internal complexity**.

That’s what **Abstraction** means in programming:  
> "Show only the essential parts, and hide the complexity."

### 🔍 In C++ Terms:

- We create a general form (interface) with no details.
- User interacts with **what the function does**, not **how** it does it.

### ✅ Benefits:

- Reduces complexity.
- Improves usability and maintenance.
- Keeps code clean and modular.

### 🧰 C++ Example using Abstract Class

```cpp
#include <iostream>
using namespace std;

// Abstract base class
class Animal {
public:
    virtual void makeSound() = 0; // pure virtual function
};

// Derived Dog class
class Dog : public Animal {
public:
    void makeSound() override {
        cout << "Woof! 🐶\n";
    }
};

// Derived Cat class
class Cat : public Animal {
public:
    void makeSound() override {
        cout << "Meow! 🐱\n";
    }
};

int main() {
    Dog d;
    Cat c;
    d.makeSound(); // Dog sound
    c.makeSound(); // Cat sound
    return 0;
}
```

### 📌 Summary Table:

| Real-life Concept | Programming Equivalent     |
|------------------|-----------------------------|
| Drive the car     | Use the function            |
| Don’t see engine  | Don’t see implementation    |
| Wheel, pedal      | Interface (abstract method) |
| Complex engine    | Hidden logic (implementation) |
