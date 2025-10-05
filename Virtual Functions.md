
# 🧠 Virtual Functions in C++ | الدوال الافتراضية في C++

---

## 🇬🇧 English Explanation

### 💡 What Are Virtual Functions?

A **Virtual Function** in C++ is a function in a base class that is **declared with the keyword `virtual`**, allowing it to be **overridden** in derived classes.

When a virtual function is called through a **base class pointer or reference**, the **derived class version** of the function is executed — **not** the base class version.

This is the foundation of **runtime polymorphism** in Object-Oriented Programming.

---

### 🧩 Real-Life Analogy

Imagine a **Remote Control**.  
It can control different devices like a **TV**, **Fan**, or **AC** — but the same button (like “Power”) performs a **different action** for each device.  

Similarly, a **base class function** (`turnOn()`) can have **different implementations** in derived classes (`TV`, `Fan`, etc.) — this is done using **virtual functions**.

---

### 🧱 Example Code

```cpp
#include <iostream>
using namespace std;

class Device {
public:
    virtual void turnOn() {
        cout << "Turning on a generic device..." << endl;
    }
};

class TV : public Device {
public:
    void turnOn() override {
        cout << "Turning on the TV." << endl;
    }
};

class Fan : public Device {
public:
    void turnOn() override {
        cout << "Turning on the Fan." << endl;
    }
};

int main() {
    Device* d1 = new TV();
    Device* d2 = new Fan();

    d1->turnOn();  // Executes TV's version
    d2->turnOn();  // Executes Fan's version

    delete d1;
    delete d2;
}
```

---

### ⚙️ Explanation

1. The `Device` class defines a **virtual function** `turnOn()`.  
2. `TV` and `Fan` override this function with their own versions.  
3. When we call `turnOn()` through a **base class pointer**, C++ automatically decides **at runtime** which version to execute.  

Without `virtual`, the **base class version** would always run — even if the pointer points to a derived object.

---

### ⚖️ Why Use Virtual Functions?

✅ To achieve **dynamic behavior**.  
✅ To implement **runtime polymorphism**.  
✅ To make programs **extensible** (easily add new types).  

---

### 🧠 Key Notes

- Declared using `virtual` keyword.  
- Typically used with **base class pointers or references**.  
- If not overridden, the **base class version** is executed.  
- You can make a function **pure virtual** (`= 0`) to create an **abstract class**.  

---

## 🇸🇦 الشرح بالعربية

### 💡 ما هي الدوال الافتراضية؟

الدالة الافتراضية (**Virtual Function**) هي دالة تُعرف داخل **كلاس الأب** باستخدام الكلمة المفتاحية `virtual`،  
وتُستخدم للسماح بإعادة تعريفها (**override**) في الكلاسات المشتقة.

عند استدعاء هذه الدالة عبر **مؤشر أو مرجع من نوع كلاس الأب**، يتم تنفيذ **دالة الابن** وليس الأب — وهذا يُسمى **تعدد الأشكال أثناء التشغيل (Runtime Polymorphism)**.

---

### 🧩 مثال واقعي

تخيل **جهاز تحكم عن بُعد (Remote Control)**.  
يمكنه تشغيل أجهزة مختلفة مثل **التلفاز** و**المروحة** و**المكيف**.  
زر “Power” نفسه موجود في كل الأجهزة، لكن سلوكه مختلف حسب الجهاز.  

بنفس الطريقة، يمكن أن تحتوي دالة `turnOn()` في كلاس الأب على نسخ مختلفة في كلاسات الأبناء — ويتم ذلك باستخدام **الدوال الافتراضية**.

---

### 🧱 مثال برمجي

```cpp
#include <iostream>
using namespace std;

class Device {
public:
    virtual void turnOn() {
        cout << "تشغيل جهاز عام..." << endl;
    }
};

class TV : public Device {
public:
    void turnOn() override {
        cout << "تشغيل التلفاز." << endl;
    }
};

class Fan : public Device {
public:
    void turnOn() override {
        cout << "تشغيل المروحة." << endl;
    }
};

int main() {
    Device* d1 = new TV();
    Device* d2 = new Fan();

    d1->turnOn();  // ينفذ دالة TV
    d2->turnOn();  // ينفذ دالة Fan

    delete d1;
    delete d2;
}
```

---

### ⚙️ الشرح

1. الكلاس `Device` يحتوي على دالة افتراضية `turnOn()`.  
2. كلا الكلاسين `TV` و `Fan` أعادا تعريف هذه الدالة.  
3. عند استدعائها عبر مؤشر من نوع `Device*`، يتم تنفيذ الدالة الخاصة بالكلاس المشتق.  

بدون الكلمة `virtual` سيتم تنفيذ دالة الأب فقط دائمًا.

---

### ⚖️ لماذا نستخدم الدوال الافتراضية؟

✅ لتحقيق **التعدد الشكلي أثناء التشغيل (Runtime Polymorphism)**.  
✅ لتسهيل **إضافة أنواع جديدة دون تعديل الكود الأساسي**.  
✅ لجعل البرنامج أكثر **مرونة وقابلية للتوسع**.  

---

### 🧠 ملاحظات مهمة

- تُعلن باستخدام الكلمة المفتاحية `virtual`.  
- تُستخدم غالبًا مع **المؤشرات أو المراجع** من كلاس الأب.  
- إذا لم تُعاد تعريفها، تُنفذ دالة الأب الافتراضية.  
- يمكن جعلها **دالة افتراضية خالصة (Pure Virtual)** بكتابة `= 0` لإنشاء **كلاس مجرد (Abstract Class)**.  

---

💡 **الخلاصة:**  
الدوال الافتراضية تمنحنا **التحكم الديناميكي** في السلوك البرمجي،  
وتُستخدم لبناء برامج مرنة وقابلة للتوسع في بيئة الكائنات (OOP).
