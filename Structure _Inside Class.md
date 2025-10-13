
# 🧱 Structure Inside Class in C++ | البنية داخل الكلاس في البرمجة الكائنية

---

## 🇬🇧 English Explanation

### 💡 What is a Structure Inside a Class?

In **C++**, we can define a **structure (struct)** **inside a class**.  
This allows us to group related data together **within** the scope of a class — providing better organization and encapsulation.

A **struct inside a class** behaves like a **mini data container** that belongs only to that class.

> Think of it as having a “helper box” inside your class to keep small related items together.

---

### 🧩 Real-Life Analogy

Imagine a **Company** class that represents a business.  
Inside it, you might want to have a **structure for Employee data** — like name, age, and salary.  
This structure doesn’t need to exist on its own, it’s only meaningful **inside the company**.

---

### ⚙️ Example 1: Basic Structure Inside a Class

```cpp
#include <iostream>
#include <string>
using namespace std;

class Company {
public:
    // Structure inside class
    struct Employee {
        string name;
        int age;
        double salary;
    };

    void displayEmployee(Employee e) {
        cout << "Name: " << e.name << ", Age: " << e.age << ", Salary: $" << e.salary << endl;
    }
};

int main() {
    Company::Employee emp1 = {"John Doe", 30, 5000.0};
    Company comp;
    comp.displayEmployee(emp1);
    return 0;
}
```

### 🧠 Explanation

- We created a `struct Employee` **inside** the `Company` class.  
- To create an object from it, we use `Company::Employee emp;`  
- This shows that the structure **belongs to** the class `Company`.  
- The class can use it for its internal logic or data management.

---

### ⚙️ Example 2: Nested Structure Used Internally

```cpp
#include <iostream>
#include <string>
using namespace std;

class School {
private:
    struct Student {
        string name;
        int grade;
    };

    Student topStudent;

public:
    School(string n, int g) {
        topStudent.name = n;
        topStudent.grade = g;
    }

    void showTopStudent() {
        cout << "Top Student: " << topStudent.name << " (Grade " << topStudent.grade << ")" << endl;
    }
};

int main() {
    School s("Alice", 95);
    s.showTopStudent();
    return 0;
}
```

### 🧠 Explanation

- Here, the structure `Student` is **private**, meaning it’s **only used inside the class**.  
- It’s a good design choice when the structure is not needed outside.  
- This helps keep the data **organized and encapsulated**.

---

### ⚖️ Advantages

| Benefit | Description |
|----------|-------------|
| **Encapsulation** | Keeps related data inside the class only |
| **Organization** | Groups small related data structures logically |
| **Reusability** | The class can create multiple instances of its internal struct |
| **Readability** | Makes code cleaner and easier to understand |

---

## 🇸🇦 الشرح بالعربية

### 💡 ما هي البنية داخل الكلاس (Structure Inside Class)؟

في لغة C++ يمكننا تعريف **بنية (struct)** **داخل الكلاس**.  
وهذا يسمح لنا بتجميع البيانات المرتبطة ببعضها **داخل نطاق الكلاس نفسه** مما يزيد التنظيم والوضوح.

تعمل البنية داخل الكلاس كأنها **حاوية بيانات صغيرة** مخصصة فقط لذلك الكلاس.

> تخيلها كصندوق صغير داخل الكلاس يحتفظ بمعلومات فرعية ومترابطة.

---

### 🧩 مثال من الحياة الواقعية

تخيل عندك كلاس يمثل **شركة (Company)**.  
بداخلها تريد تخزين بيانات الموظفين مثل الاسم والعمر والراتب.  
هذه البيانات منطقياً تخص الشركة فقط، لذلك نضعها في **بنية داخل الكلاس**.

---

### ⚙️ المثال الأول: بنية بسيطة داخل الكلاس

```cpp
#include <iostream>
#include <string>
using namespace std;

class Company {
public:
    struct Employee {
        string name;
        int age;
        double salary;
    };

    void displayEmployee(Employee e) {
        cout << "الاسم: " << e.name << ", العمر: " << e.age << ", الراتب: $" << e.salary << endl;
    }
};

int main() {
    Company::Employee emp1 = {"محمد أحمد", 28, 4500.0};
    Company comp;
    comp.displayEmployee(emp1);
    return 0;
}
```

### 🧠 الشرح

- تم تعريف `struct Employee` داخل الكلاس `Company`.  
- لإنشاء كائن من هذه البنية نكتب: `Company::Employee emp;`  
- هذا يعني أن البنية **تتبع الكلاس Company** فقط.  
- نستخدمها داخل الكلاس لتنظيم بيانات معينة مثل الموظفين.

---

### ⚙️ المثال الثاني: بنية داخلية خاصة

```cpp
#include <iostream>
#include <string>
using namespace std;

class School {
private:
    struct Student {
        string name;
        int grade;
    };

    Student topStudent;

public:
    School(string n, int g) {
        topStudent.name = n;
        topStudent.grade = g;
    }

    void showTopStudent() {
        cout << "أفضل طالب: " << topStudent.name << " (الدرجة: " << topStudent.grade << ")" << endl;
    }
};

int main() {
    School s("علي حسن", 98);
    s.showTopStudent();
    return 0;
}
```

### 🧠 الشرح

- هنا تم تعريف البنية `Student` داخل الكلاس `School` ولكنها **خاصة (private)**.  
- لا يمكن لأي كود خارجي الوصول إليها مباشرة.  
- تُستخدم فقط لتنظيم بيانات معينة داخل الكلاس.  
- هذا يُعتبر تصميمًا جيدًا لأنه يحافظ على **الترتيب والخصوصية**.

---

### ⚖️ المميزات

| الميزة | التوضيح |
|--------|----------|
| **الإخفاء (Encapsulation)** | تجعل البيانات الداخلية محصورة داخل الكلاس فقط |
| **التنظيم** | تجمع البيانات المرتبطة معًا بطريقة منطقية داخل الكلاس |
| **إعادة الاستخدام** | يمكن للكلاس إنشاء عدة نسخ من نفس البنية الداخلية |
| **سهولة القراءة** | تجعل الكود منظمًا وسهل الفهم |

---

💡 **الخلاصة:**  
استخدام البنى داخل الكلاسات طريقة ذكية لتنظيم البيانات الصغيرة التي تخص الكلاس فقط،  
مما يجعل الكود أكثر وضوحًا وقوة في التصميم.
