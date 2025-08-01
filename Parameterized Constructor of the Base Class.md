
# 🏗️ Parameterized Constructor of the Base Class | المُنشئ المُعَمم للكلاس الأب في C++

---

## 🇺🇸 Explanation in English

### 🧠 What is it?

When a **base class** has a **constructor that requires parameters**,  
then any **derived class (child class)** must call that constructor **explicitly** using an **initializer list**.

---

### 👦 Simple Analogy

Imagine a base class `Person` that always needs a **name** when created.  
Now you want to create a `Student` class that inherits from `Person`.

You must **pass the name** to the `Person` constructor from the `Student` constructor using this syntax:
```cpp
Student(string n, int g) : Person(n)
```

---

### 🧰 Code Example

```cpp
#include <iostream>
using namespace std;

class Person {
public:
    string name;

    Person(string n) {
        name = n;
        cout << "👤 Person created: " << name << endl;
    }
};

class Student : public Person {
public:
    int grade;

    Student(string n, int g) : Person(n) {
        grade = g;
        cout << "🎓 Student created with grade: " << grade << endl;
    }
};

int main() {
    Student s1("Belal", 100);
    return 0;
}
```

---

### 📌 Key Notes

| Situation                            | What to do                           |
|--------------------------------------|--------------------------------------|
| Base class has no parameters         | Nothing needed in child class        |
| Base class has required parameters   | Must use `: BaseClass(parameters)`   |
| If you forget to call it             | Compiler error                       |

---

> Always remember: If your base class constructor takes arguments, you **must** call it from your derived class.

---

## 🇸🇦 الشرح باللغة العربية

### 🧠 ما هو؟

إذا كان **الكلاس الأب** يحتوي على **constructor بمدخلات (بارامترات)**،  
فإن **الكلاس الابن** يجب أن **ينادي هذا المنشئ يدويًا** باستخدام ما يسمى **initializer list**.

---

### 👶 تشبيه بسيط

تخيل كلاس `Person` لا يمكن إنشاؤه بدون اسم.  
ولما تعمل كلاس `Student` يرث من `Person`، لازم **تمّرر الاسم** للأب داخل منشئ الطالب:

```cpp
Student(string n, int g) : Person(n)
```

---

### 🧰 مثال عملي بلغة C++

```cpp
#include <iostream>
using namespace std;

class Person {
public:
    string name;

    Person(string n) {
        name = n;
        cout << "👤 تم إنشاء شخص: " << name << endl;
    }
};

class Student : public Person {
public:
    int grade;

    Student(string n, int g) : Person(n) {
        grade = g;
        cout << "🎓 تم إنشاء طالب بدرجة: " << grade << endl;
    }
};

int main() {
    Student s1("بلال", 100);
    return 0;
}
```

---

### 📌 ملاحظات هامة

| الحالة                            | ماذا تفعل؟                              |
|----------------------------------|------------------------------------------|
| الكلاس الأب بدون مدخلات         | لا حاجة لفعل أي شيء في الابن              |
| الكلاس الأب يطلب مدخلات         | يجب كتابة `: BaseClass(parameters)`      |
| نسيت تنادي constructor الأب     | يعطيك خطأ في الترجمة (compiler error)     |

---

> تذكر دائمًا: إذا كان كلاس الأب يحتاج بارامترات، **لازم تناديه يدويًا** من الكلاس الابن.
