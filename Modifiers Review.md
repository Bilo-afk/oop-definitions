
# 🔐 Access Specifiers in C++ | محددات الوصول في C++

---

## 🇺🇸 Explanation in English

### 🧠 What are Access Specifiers?

Access specifiers (or modifiers) determine **who can access class members (variables or functions)** from outside the class or from derived classes.

---

## 🚪 Types of Access Specifiers

| Specifier   | Access Level                                  |
|-------------|-----------------------------------------------|
| `public`    | Accessible everywhere                         |
| `protected` | Accessible inside the class and derived classes |
| `private`   | Accessible only inside the same class         |

---

## 👨‍🏫 Real-Life Analogy

- `public`: Like an open park — anyone can enter.
- `protected`: Like a family-only event — only family members (derived classes) allowed.
- `private`: Like your locked bedroom — only you have access.

---

## 🧰 Practical Example

```cpp
#include <iostream>
using namespace std;

class Person {
public:
    string name;          // Public
protected:
    string nationality;   // Protected
private:
    int age;              // Private

public:
    Person(string n, string nat, int a) {
        name = n;
        nationality = nat;
        age = a;
    }

    void displayInfo() {
        cout << "Name: " << name << endl;
        cout << "Nationality: " << nationality << endl;
        cout << "Age: " << age << endl;
    }
};

class Student : public Person {
public:
    Student(string n, string nat, int a) : Person(n, nat, a) {}

    void showStudent() {
        cout << "Student Name: " << name << endl;          // OK
        cout << "Nationality: " << nationality << endl;    // OK
        // cout << "Age: " << age << endl;                // ❌ Error (private)
    }
};

int main() {
    Person p("Belal", "Syrian", 20);
    p.displayInfo();

    Student s("Belal", "Syrian", 20);
    s.showStudent();

    cout << s.name << endl;          // ✅ OK
    // cout << s.nationality << endl; // ❌ Error
    // cout << s.age << endl;         // ❌ Error

    return 0;
}
```

---

## 🧪 Summary Table

| Access Area      | `public` | `protected` | `private` |
|------------------|----------|-------------|-----------|
| Inside class     | ✅       | ✅          | ✅        |
| Derived class    | ✅       | ✅          | ❌        |
| Outside class    | ✅       | ❌          | ❌        |

---

## 🛠️ Default Behavior

- In `class`, default is `private`.
- In `struct`, default is `public`.

---

## ✅ When to Use?

| Use Case                         | Best Access Specifier |
|----------------------------------|------------------------|
| Everyone needs access            | `public`               |
| Only derived classes need access | `protected`            |
| Internal use only                | `private`              |

---

## 🇸🇦 الشرح باللغة العربية

### 🧠 ما هي محددات الوصول (Access Specifiers)؟

هي كلمات تتحكم في **من يستطيع الوصول إلى خصائص ودوال الكلاس** من خارج الكلاس أو من خلال الوراثة.

---

## 🚪 أنواع محددات الوصول

| النوع         | من يستطيع الوصول؟                                |
|---------------|--------------------------------------------------|
| `public`      | الجميع (داخل وخارج الكلاس)                       |
| `protected`   | داخل الكلاس والكلاسات المشتقة فقط                |
| `private`     | فقط داخل نفس الكلاس                              |

---

## 👨‍🏫 تشبيه من الحياة الواقعية

- `public`: كأنك فاتح حديقة عامة — الكل يدخل.
- `protected`: كأنك عامل مناسبة عائلية — فقط الورثة يدخلوا.
- `private`: كأنك قافل باب غرفتك — بس أنت تدخل.

---

## 🧰 مثال عملي

```cpp
#include <iostream>
using namespace std;

class Person {
public:
    string name;          // عام
protected:
    string nationality;   // محمي
private:
    int age;              // خاص

public:
    Person(string n, string nat, int a) {
        name = n;
        nationality = nat;
        age = a;
    }

    void displayInfo() {
        cout << "الاسم: " << name << endl;
        cout << "الجنسية: " << nationality << endl;
        cout << "العمر: " << age << endl;
    }
};

class Student : public Person {
public:
    Student(string n, string nat, int a) : Person(n, nat, a) {}

    void showStudent() {
        cout << "اسم الطالب: " << name << endl;           // ✅ مسموح
        cout << "الجنسية: " << nationality << endl;       // ✅ مسموح
        // cout << "العمر: " << age << endl;              // ❌ خطأ
    }
};

int main() {
    Person p("بلال", "سوري", 20);
    p.displayInfo();

    Student s("بلال", "سوري", 20);
    s.showStudent();

    cout << s.name << endl;          // ✅ مسموح
    // cout << s.nationality << endl; // ❌ خطأ
    // cout << s.age << endl;         // ❌ خطأ

    return 0;
}
```

---

## 🧪 ملخص الجدول

| مكان الاستخدام    | `public` | `protected` | `private` |
|-------------------|----------|-------------|-----------|
| داخل نفس الكلاس    | ✅       | ✅           | ✅         |
| في الكلاس المشتق   | ✅       | ✅           | ❌         |
| خارج الكلاس        | ✅       | ❌           | ❌         |

---

## 🛠️ السلوك الافتراضي

- في `class` الافتراضي هو `private`.
- في `struct` الافتراضي هو `public`.

---

## ✅ متى نستخدم كل نوع؟

| الحالة                             | النوع المناسب         |
|------------------------------------|------------------------|
| إذا كان يجب للجميع الوصول          | `public`               |
| فقط الكلاسات المشتقة تحتاج الوصول  | `protected`            |
| استخدام داخلي فقط                  | `private`              |
