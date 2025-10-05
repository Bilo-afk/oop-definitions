
# ⚙️ Static (Early) Binding vs Dynamic (Late) Binding in C++ | الربط الثابت مقابل الربط الديناميكي في C++

---

## 🇬🇧 English Explanation

### 🧠 What Is Binding?

**Binding** means connecting a **function call** to the **actual function definition** in memory.  
C++ provides two main types of binding:

- **Static (Early) Binding**
- **Dynamic (Late) Binding**

---

### 🔹 1. Static (Early) Binding

This occurs **at compile time**, meaning the compiler decides which function to call **before the program runs**.

It is the **default behavior** in C++ when functions are **not virtual**.

#### 💡 Real-Life Analogy:

Imagine you’re printing a document using a specific printer that’s already chosen — you can’t change it once you hit “Print.”  
That’s **static binding** — everything is decided **before execution**.

#### 🧱 Example:

```cpp
#include <iostream>
using namespace std;

class Animal {
public:
    void speak() { // Not virtual
        cout << "Animal speaks" << endl;
    }
};

class Dog : public Animal {
public:
    void speak() {
        cout << "Dog barks" << endl;
    }
};

int main() {
    Animal* a = new Dog();
    a->speak(); // Calls Animal's speak() because of static binding
    delete a;
}
```

#### 🧩 Explanation:
- `speak()` is **not virtual**, so the compiler binds the call to `Animal::speak()` **at compile time**.
- Even though the pointer `a` points to a `Dog`, it executes the **base version**.

---

### 🔸 2. Dynamic (Late) Binding

This occurs **at runtime**, meaning the compiler decides **which version to execute while the program runs**.

It happens when a function is declared with the **`virtual`** keyword in the base class.

#### 💡 Real-Life Analogy:

Imagine you press the same “Power” button on a universal remote, but it decides **at runtime** which device (TV, Fan, or AC) to control.  
That’s **dynamic binding** — the decision is made **while running**.

#### 🧱 Example:

```cpp
#include <iostream>
using namespace std;

class Animal {
public:
    virtual void speak() { // Virtual function
        cout << "Animal speaks" << endl;
    }
};

class Dog : public Animal {
public:
    void speak() override {
        cout << "Dog barks" << endl;
    }
};

int main() {
    Animal* a = new Dog();
    a->speak(); // Calls Dog's speak() due to dynamic binding
    delete a;
}
```

#### 🧩 Explanation:
- The function `speak()` is **virtual**, so the compiler waits until runtime to determine which version to call.
- Since `a` actually points to a `Dog`, it calls **Dog’s version**.

---

### ⚖️ Comparison Table

| Feature | Static (Early) Binding | Dynamic (Late) Binding |
|----------|------------------------|------------------------|
| Time of Decision | Compile Time | Runtime |
| Keyword | Default (no keyword) | Requires `virtual` |
| Performance | Faster | Slightly slower |
| Polymorphism | Not supported | Supported |
| Example | Normal function | Virtual function |

---

### 🧠 Summary

- **Static Binding**: The function call is resolved **at compile time**.  
- **Dynamic Binding**: The function call is resolved **at runtime** using `virtual`.  
- **Virtual functions** make C++ **polymorphic**, allowing **dynamic behavior**.

---

## 🇸🇦 الشرح بالعربية

### 🧠 ما هو الربط (Binding)؟

الربط هو عملية **توصيل استدعاء الدالة** بالتعريف الفعلي لها في الذاكرة.  
في C++ يوجد نوعان رئيسيان من الربط:

- **الربط الثابت (Static / Early Binding)**
- **الربط الديناميكي (Dynamic / Late Binding)**

---

### 🔹 1. الربط الثابت (Static / Early Binding)

يحدث **أثناء وقت الترجمة (Compile Time)**، أي أن المترجم يحدد أي دالة سيتم استدعاؤها **قبل تشغيل البرنامج**.

هو السلوك الافتراضي في C++ عندما لا تكون الدالة **افتراضية (virtual)**.

#### 💡 مثال واقعي:

تخيل أنك تطبع ملفًا من طابعة محددة مسبقًا — لا يمكنك تغييرها بعد الضغط على زر “طباعة”.  
هذا يشبه **الربط الثابت** — القرار يتم **قبل التنفيذ**.

#### 🧱 مثال برمجي:

```cpp
#include <iostream>
using namespace std;

class Animal {
public:
    void speak() { // ليست افتراضية
        cout << "الحيوان يتكلم" << endl;
    }
};

class Dog : public Animal {
public:
    void speak() {
        cout << "الكلب ينبح" << endl;
    }
};

int main() {
    Animal* a = new Dog();
    a->speak(); // يستدعي دالة Animal بسبب الربط الثابت
    delete a;
}
```

#### 🧩 الشرح:
- الدالة `speak()` ليست افتراضية، لذلك يقرر المترجم استدعاء `Animal::speak()` أثناء الترجمة.
- حتى لو كان المؤشر يشير إلى كائن من نوع `Dog`، سيُنفذ إصدار الأب.

---

### 🔸 2. الربط الديناميكي (Dynamic / Late Binding)

يحدث **أثناء وقت التشغيل (Runtime)**، أي أن القرار يتخذ **أثناء تنفيذ البرنامج**.

يتم ذلك عندما تُعرف الدالة باستخدام الكلمة المفتاحية **`virtual`** في كلاس الأب.

#### 💡 مثال واقعي:

تخيل أنك تضغط زر “Power” في ريموت شامل، فيقرر **أثناء التشغيل** الجهاز الذي سيعمل (تلفاز أو مروحة أو مكيف).  
هذا يشبه **الربط الديناميكي** — القرار يتم **أثناء التشغيل**.

#### 🧱 مثال برمجي:

```cpp
#include <iostream>
using namespace std;

class Animal {
public:
    virtual void speak() { // دالة افتراضية
        cout << "الحيوان يتكلم" << endl;
    }
};

class Dog : public Animal {
public:
    void speak() override {
        cout << "الكلب ينبح" << endl;
    }
};

int main() {
    Animal* a = new Dog();
    a->speak(); // ينفذ دالة Dog بسبب الربط الديناميكي
    delete a;
}
```

#### 🧩 الشرح:
- لأن الدالة `speak()` افتراضية، ينتظر المترجم حتى وقت التشغيل ليقرر أي دالة سينفذ.
- وبما أن المؤشر يشير إلى كائن من نوع `Dog`، ينفذ دالة `Dog` وليس `Animal`.

---

### ⚖️ جدول المقارنة

| الخاصية | الربط الثابت | الربط الديناميكي |
|----------|---------------|------------------|
| وقت القرار | أثناء الترجمة | أثناء التشغيل |
| الكلمة المفتاحية | لا يحتاج | يحتاج `virtual` |
| الأداء | أسرع | أبطأ قليلًا |
| تعدد الأشكال | غير مدعوم | مدعوم |
| المثال | دالة عادية | دالة افتراضية |

---

### 💡 الخلاصة

- **الربط الثابت**: يتم تحديد الدالة أثناء الترجمة.  
- **الربط الديناميكي**: يتم تحديد الدالة أثناء التشغيل باستخدام `virtual`.  
- **الدوال الافتراضية** تجعل C++ تدعم **تعدد الأشكال الديناميكي (Runtime Polymorphism)**.
