
# 🧲 Static Members in C++ | الأعضاء الثابتة في C++

---

## 🇺🇸 English Explanation

### 🧠 What are Static Members?

**Static members** are variables or functions that belong to the **class itself**, not to any individual object.

### 👦 Simple Analogy

Imagine a classroom:
- Each student has their own name and notebook (these are regular members).
- But there's a counter on the door that tracks how many students entered — this is a **static member**.

This counter:
- Does not belong to one specific student.
- It belongs to the **classroom itself**.

### 🔍 Comparison

| Type        | Belongs to        | One per object? | Requires object? |
|-------------|-------------------|------------------|------------------|
| Non-static  | Individual object | ✅ Yes           | ✅ Yes           |
| Static      | Entire class      | ❌ No (shared)   | ❌ No            |

### 🧰 Example

```cpp
#include <iostream>
using namespace std;

class Student {
public:
    string name;
    static int count;

    Student(string n) {
        name = n;
        count++;
    }

    void show() {
        cout << "👤 Name: " << name << endl;
    }

    static void showCount() {
        cout << "👥 Total Students: " << count << endl;
    }
};

int Student::count = 0;

int main() {
    Student s1("Belal");
    Student s2("Ahmad");

    s1.show();
    s2.show();

    Student::showCount();
    return 0;
}
```

### 📌 Notes

- Static variables must be defined **outside** the class.
- Static members are **shared** between all objects of the class.

---

## 🇸🇦 الشرح باللغة العربية

### 🧠 ما هي الأعضاء الثابتة (Static Members)؟

هي متغيرات أو دوال تنتمي إلى **الكلاس نفسه**، وليست خاصة بأي كائن (Object) معين.

### 👶 تشبيه بسيط

تخيل صف دراسي:
- كل طالب عنده اسمه ودفتره (متغيرات عادية).
- لكن يوجد عداد على باب الصف يحسب عدد الطلاب — هذا هو **متغير ثابت static**.

هذا العداد:
- لا يخص طالب واحد.
- بل يخص الصف ككل (الكلاس نفسه).

### 🔍 مقارنة

| النوع          | تابع لمن؟        | يتكرر مع كل كائن؟ | يحتاج كائن؟ |
|----------------|------------------|-------------------|-------------|
| غير ثابت       | الكائن نفسه       | ✅ نعم             | ✅ نعم        |
| ثابت (static)  | الكلاس بالكامل     | ❌ لا (مشترك)      | ❌ لا         |

### 🧰 مثال بلغة C++

```cpp
#include <iostream>
using namespace std;

class Student {
public:
    string name;
    static int count;

    Student(string n) {
        name = n;
        count++;
    }

    void show() {
        cout << "👤 الاسم: " << name << endl;
    }

    static void showCount() {
        cout << "👥 عدد الطلاب: " << count << endl;
    }
};

int Student::count = 0;

int main() {
    Student s1("بلال");
    Student s2("أحمد");

    s1.show();
    s2.show();

    Student::showCount();
    return 0;
}
```

### 📌 ملاحظات

- المتغيرات الثابتة يتم تعريفها **خارج الكلاس**.
- الأعضاء الثابتة مشتركة بين كل الكائنات من نفس الكلاس.

---

> **Static = Shared Across All Objects**
