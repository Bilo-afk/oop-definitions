
<h1 align="center">🏗️ Constructors in C++ | المنشئات في لغة C++</h1>

---

## 🇦🇪 الشرح باللغة العربية

### 🧒 ما هو الـ Constructor (المنشئ)؟

تخيل أنك تصنع لعبة جديدة 🎮  
كل مرة تنشئ اللعبة لازم تعطيها إعدادات مثل الاسم والمستوى.  
بدل ما تكرر نفس الخطوات، يوجد دالة سحرية تعمل تلقائيًا اسمها **Constructor**!

### 🔍 تعريف بسيط:

> الـ Constructor هو دالة خاصة داخل الكلاس تعمل تلقائيًا عند إنشاء كائن (object) من هذا الكلاس.

### ✅ خصائص الـ Constructor:

- اسمه **نفس اسم الكلاس تمامًا**.
- **لا يملك نوع إرجاع** (لا void ولا int...).
- يعمل تلقائيًا عند استخدام الكلاس.

---

### 🧰 مثال 1: Constructor بسيط

```cpp
#include <iostream>
using namespace std;

class Student {
public:
    // Constructor بدون معطيات
    Student() {
        cout << "🎉 تم إنشاء طالب جديد!\n";
    }
};

int main() {
    Student s1;  // يتم استدعاء Constructor تلقائيًا
    Student s2;
    return 0;
}
```

🟢 **الناتج:**
```
🎉 تم إنشاء طالب جديد!
🎉 تم إنشاء طالب جديد!
```

---

### 🧰 مثال 2: Constructor مع معطيات

```cpp
#include <iostream>
using namespace std;

class Student {
public:
    string name;
    int age;

    // Constructor يأخذ الاسم والعمر
    Student(string n, int a) {
        name = n;
        age = a;
    }

    void show() {
        cout << "الاسم: " << name << ", العمر: " << age << endl;
    }
};

int main() {
    Student s1("بلال", 20);
    s1.show();  // يطبع: الاسم: بلال, العمر: 20
    return 0;
}
```

---

### 📌 تلخيص:

| المفهوم الحقيقي        | في البرمجة             |
|-----------------------|------------------------|
| صنع لعبة جديدة         | إنشاء كائن (Object)    |
| إعداد اللعبة تلقائيًا   | Constructor يعمل تلقائيًا |
| نفس اسم اللعبة         | اسم Constructor = اسم الكلاس |

---

## 🇺🇸 Explanation in English

### 🧒 What is a Constructor?

Imagine you're making a new game 🎮  
Each time, you need to set up name, level, and settings.  
Instead of repeating steps, there's a magic function called **Constructor** that sets it up automatically!

### 🔍 Simple Definition:

> A constructor is a special function inside a class that runs automatically when an object is created.

### ✅ Key Features:

- Has **the same name** as the class.
- **No return type** (not even void).
- **Runs automatically** when you create an object.

---

### 🧰 Example 1: Basic Constructor

```cpp
#include <iostream>
using namespace std;

class Student {
public:
    // Constructor without parameters
    Student() {
        cout << "🎉 A new student has been created!\n";
    }
};

int main() {
    Student s1;  // Constructor runs automatically
    Student s2;
    return 0;
}
```

🟢 **Output:**
```
🎉 A new student has been created!
🎉 A new student has been created!
```

---

### 🧰 Example 2: Constructor with Parameters

```cpp
#include <iostream>
using namespace std;

class Student {
public:
    string name;
    int age;

    // Constructor with arguments
    Student(string n, int a) {
        name = n;
        age = a;
    }

    void show() {
        cout << "Name: " << name << ", Age: " << age << endl;
    }
};

int main() {
    Student s1("Belal", 20);
    s1.show();  // Prints: Name: Belal, Age: 20
    return 0;
}
```

---

### 📌 Summary Table:

| Real-life Concept     | In Programming             |
|----------------------|----------------------------|
| Making a new game     | Creating an object         |
| Auto-initialize game  | Constructor runs by itself |
| Same name as the game | Constructor = class name   |
