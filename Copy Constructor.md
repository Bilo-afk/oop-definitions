
<h1 align="center">📋 Copy Constructor in C++ | النسخ في C++</h1>

---

## 🇺🇸 Explanation in English

### 🧠 What is a Copy Constructor?

A **Copy Constructor** is a special function in C++ used to **create a new object** as a **copy of an existing object**.

### 🧒 Simple Analogy:

Imagine you have a student named **Ahmed** with a name and age.  
You want to make another student with **exactly the same data**.

Instead of writing the same info again, you say:  
“Just copy Ahmed and create Ali.” → That’s what a copy constructor does.

---

### ✅ When is it used?

C++ uses the copy constructor automatically when:
- You pass an object **by value** to a function.
- You **return** an object by value from a function.
- You write: `Student s2 = s1;`

---

### 🧰 Example in C++

```cpp
#include <iostream>
using namespace std;

class Student {
public:
    string name;
    int age;

    // Normal constructor
    Student(string n, int a) {
        name = n;
        age = a;
    }

    // Copy constructor
    Student(const Student& other) {
        name = other.name;
        age = other.age;
        cout << "📋 Student copied!\n";
    }

    void show() {
        cout << "👤 Name: " << name << ", Age: " << age << endl;
    }
};

int main() {
    Student s1("Belal", 20);
    Student s2 = s1; // Copy constructor is called here

    s2.show();
    return 0;
}
```

---

### 📌 Summary:

| Question                  | Answer                                 |
|--------------------------|----------------------------------------|
| What is it?              | Creates a new object as a copy         |
| When is it used?         | When copying an existing object        |
| Do I always need it?     | Only when using pointers or dynamic memory |
| Syntax                   | `ClassName(const ClassName& other)`    |

---

## 🇦🇪 الشرح باللغة العربية

### 🧠 ما هو Copy Constructor؟

الـ **Copy Constructor** هو دالة خاصة في C++ تُستخدم لإنشاء كائن جديد **بنفس بيانات كائن آخر موجود**.

---

### 👦 تشبيه بسيط:

تخيل عندك طالب اسمه **أحمد** فيه اسم وعمر.  
بدك تنشئ طالب جديد اسمه **علي**، ويكون **نسخة طبق الأصل** عن أحمد.

بدل ما تعيد كتابة البيانات، تقول للبرنامج:  
"انسخ أحمد وحط المعلومات في علي" ← هون بيشتغل Copy Constructor.

---

### ✅ متى يتم استخدامه تلقائيًا؟

- عند تمرير الكائن **بالقيمة** لدالة.
- عند **إرجاع** كائن من دالة.
- عند كتابة: `Student s2 = s1;`

---

### 🧰 مثال عملي بلغة C++

```cpp
#include <iostream>
using namespace std;

class Student {
public:
    string name;
    int age;

    // Constructor عادي
    Student(string n, int a) {
        name = n;
        age = a;
    }

    // Copy Constructor
    Student(const Student& other) {
        name = other.name;
        age = other.age;
        cout << "📋 تم نسخ الطالب!\n";
    }

    void show() {
        cout << "👤 الاسم: " << name << ", العمر: " << age << endl;
    }
};

int main() {
    Student s1("بلال", 20);
    Student s2 = s1; // يتم استدعاء Copy Constructor

    s2.show();
    return 0;
}
```

---

### 📌 الخلاصة:

| السؤال                     | الجواب                                   |
|---------------------------|------------------------------------------|
| ما هو؟                    | دالة تنشئ نسخة من كائن موجود            |
| متى يُستخدم؟              | عند نسخ كائن موجود                       |
| هل يجب عليّ كتابته دائمًا؟ | فقط إذا كنت تستخدم مؤشرات أو new        |
| الشكل العام               | `ClassName(const ClassName& other)`     |

---

<p align="center"><b>النسخ الذكي يبدأ من Copy Constructor ✨</b></p>
