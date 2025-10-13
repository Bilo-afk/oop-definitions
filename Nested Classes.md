
# 🧩 Nested Classes in C++ | الكلاسات المتداخلة في البرمجة الكائنية

---

## 🇬🇧 English Explanation

### 💡 What is a Nested Class?

In **C++**, a **nested class** is a class that is **defined inside another class**.  
It helps to logically group two classes that are closely related, improving **encapsulation** and **organization**.

> Think of it as a “class inside a class” — a helper class that exists only for the main one.

---

### 🧩 Real-Life Analogy

Imagine a **University** class that represents the whole institution.  
Inside it, we could have a **Department** class — it only makes sense *inside* the university context.  
You wouldn’t have a department without a university, right?

That’s exactly what a **nested class** represents — a class that belongs to another.

---

### ⚙️ Example 1: Basic Nested Class

```cpp
#include <iostream>
#include <string>
using namespace std;

class University {
public:
    class Department {
    private:
        string name;
        int numOfStudents;

    public:
        Department(string n, int s) : name(n), numOfStudents(s) {}

        void display() {
            cout << "Department: " << name << ", Students: " << numOfStudents << endl;
        }
    };

    void showInfo() {
        cout << "This is a university containing multiple departments." << endl;
    }
};

int main() {
    University::Department cs("Computer Engineering", 120);
    cs.display();

    University uni;
    uni.showInfo();

    return 0;
}
```

### 🧠 Explanation

- `Department` is **nested** inside `University`.  
- You access it using **scope resolution** `University::Department`.  
- It helps show that the `Department` **belongs** to `University`.  
- Improves **code organization** when one class depends on another.

---

### ⚙️ Example 2: Private Nested Class (Used Internally)

```cpp
#include <iostream>
using namespace std;

class Bank {
private:
    class Account {
    private:
        int balance;

    public:
        Account(int b) : balance(b) {}
        void showBalance() { cout << "Balance: $" << balance << endl; }
    };

public:
    void openAccount(int initialAmount) {
        Account acc(initialAmount);
        acc.showBalance();
    }
};

int main() {
    Bank bank;
    bank.openAccount(500);
    return 0;
}
```

### 🧠 Explanation

- The nested class `Account` is **private**, meaning it can only be used **inside** `Bank`.  
- This makes sense because we don’t want users to create accounts directly — only through the bank system.  
- It’s a great way to **hide implementation details**.

---

### ⚖️ Advantages of Nested Classes

| Advantage | Description |
|------------|-------------|
| **Encapsulation** | Hides helper classes that are not needed outside |
| **Organization** | Keeps related classes grouped logically |
| **Readability** | Makes the code cleaner and more structured |
| **Access Control** | Can access private/protected members of the outer class if declared as `friend` |

---

## 🇸🇦 الشرح بالعربية

### 💡 ما هي الكلاسات المتداخلة (Nested Classes)؟

في لغة C++ يمكننا تعريف **كلاس داخل كلاس آخر**.  
وهذا يساعد في تنظيم الكود وتجميع الكلاسات المرتبطة ببعضها داخل نطاق واحد.

> الكلاس المتداخل يشبه كلاس مساعد موجود داخل الكلاس الرئيسي.

---

### 🧩 مثال من الحياة الواقعية

تخيل كلاس يمثل **جامعة (University)**.  
داخلها يوجد كلاس آخر يمثل **قسم (Department)**.  
القسم لا يمكن أن يوجد دون الجامعة، لذلك من المنطقي وضعه داخلها.

هذا بالضبط هو مفهوم **Nested Class**.

---

### ⚙️ المثال الأول: كلاس متداخل بسيط

```cpp
#include <iostream>
#include <string>
using namespace std;

class University {
public:
    class Department {
    private:
        string name;
        int numOfStudents;

    public:
        Department(string n, int s) : name(n), numOfStudents(s) {}

        void display() {
            cout << "القسم: " << name << ", عدد الطلاب: " << numOfStudents << endl;
        }
    };

    void showInfo() {
        cout << "هذه جامعة تحتوي على عدة أقسام." << endl;
    }
};

int main() {
    University::Department cs("هندسة الحاسوب", 120);
    cs.display();

    University uni;
    uni.showInfo();

    return 0;
}
```

### 🧠 الشرح

- الكلاس `Department` تم تعريفه داخل الكلاس `University`.  
- نستخدمه عبر `University::Department`.  
- هذا يعني أن `Department` **يتبع** `University`.  
- يساعد على التنظيم والوضوح عندما تكون الكلاسات مرتبطة.

---

### ⚙️ المثال الثاني: كلاس داخلي خاص

```cpp
#include <iostream>
using namespace std;

class Bank {
private:
    class Account {
    private:
        int balance;

    public:
        Account(int b) : balance(b) {}
        void showBalance() { cout << "الرصيد: $" << balance << endl; }
    };

public:
    void openAccount(int initialAmount) {
        Account acc(initialAmount);
        acc.showBalance();
    }
};

int main() {
    Bank bank;
    bank.openAccount(500);
    return 0;
}
```

### 🧠 الشرح

- الكلاس `Account` تم تعريفه داخل `Bank` لكنه **خاص (private)**.  
- لا يمكن لأي كود خارجي الوصول إليه مباشرة.  
- فقط كلاس `Bank` يستطيع استخدامه داخليًا.  
- هذا التصميم مفيد جدًا لإخفاء التفاصيل الداخلية.

---

### ⚖️ مميزات الكلاسات المتداخلة

| الميزة | التوضيح |
|--------|----------|
| **الإخفاء (Encapsulation)** | تُخفي الكلاسات المساعدة غير الضرورية خارج الكلاس |
| **التنظيم** | تجمع الكلاسات المرتبطة في مكان واحد |
| **الوضوح** | تجعل الكود منظمًا وسهل القراءة |
| **التحكم بالوصول** | يمكن أن تصل إلى الأعضاء الخاصة للكلاس الخارجي إذا تم إعلانها كـ `friend` |

---

💡 **الخلاصة:**  
الكلاسات المتداخلة تُستخدم عندما يكون لدينا كلاس رئيسي يحتوي على كلاس مساعد لا معنى له خارجه،  
مما يجعل الكود أكثر ترتيبًا وأمانًا في التصميم.
