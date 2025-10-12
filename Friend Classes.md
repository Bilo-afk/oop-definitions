
# 🤝 Friend Classes in C++ | الكلاسات الصديقة في البرمجة الكائنية

---

## 🇬🇧 English Explanation

### 💡 What is a Friend Class?

In **C++**, a **friend class** is a class that has **special access** to the private and protected members of another class.  
Normally, private data is **hidden** from other classes, but by declaring a class as a *friend*, we allow it to access internal details directly.

> Think of it like giving a “special backstage pass” to another class.

---

### 🧩 Real-Life Analogy

Imagine you own a **house**. Normally, **no one can enter your locked rooms**, right?  
But you might give your **best friend** a **spare key** so they can access your home when needed.  
That’s exactly what a **friend class** does — it grants **special access** to another class.

---

### ⚙️ Example 1: Basic Friend Class

```cpp
#include <iostream>
using namespace std;

class Engine; // Forward declaration

class Car {
private:
    int fuel;

public:
    Car(int f) : fuel(f) {}

    // Declare Engine as a friend class
    friend class Engine;
};

class Engine {
public:
    void showFuel(Car &c) {
        cout << "Fuel level: " << c.fuel << " liters." << endl;
    }
};

int main() {
    Car myCar(50);
    Engine eng;
    eng.showFuel(myCar); // Engine can access Car's private member
    return 0;
}
```

### 🧠 Explanation

- Normally, the variable `fuel` inside `Car` is **private**.  
- But because `Engine` is declared as a **friend class**, it can access `fuel` directly.  
- Without the `friend` keyword, this access would **not be allowed**.

---

### ⚙️ Example 2: Friendship in Real Design

```cpp
#include <iostream>
using namespace std;

class BankAccount;

class ATM {
public:
    void withdraw(BankAccount &account, int amount);
};

class BankAccount {
private:
    int balance;

public:
    BankAccount(int bal) : balance(bal) {}

    friend class ATM; // Allow ATM to access balance
};

void ATM::withdraw(BankAccount &account, int amount) {
    if (amount <= account.balance) {
        account.balance -= amount;
        cout << "Withdrawal successful. Remaining balance: " << account.balance << endl;
    } else {
        cout << "Insufficient funds!" << endl;
    }
}

int main() {
    BankAccount acc(500);
    ATM atm;
    atm.withdraw(acc, 200);
    return 0;
}
```

### 🧠 Explanation

- Here, `BankAccount` hides the `balance` (it's private).  
- But we want the `ATM` class to access it directly.  
- By declaring `ATM` as a **friend**, we allow secure, controlled access.  
- This models real-world trust between systems (like a bank system and an ATM).

---

### ⚖️ Key Notes

| Feature | Description |
|----------|-------------|
| **Friend Class** | A class that can access private/protected members of another class |
| **Defined Using** | `friend class ClassName;` |
| **Access Scope** | Friendship is **not inherited** |
| **Use Case** | When two classes are closely related (e.g., Car ↔ Engine, Bank ↔ ATM) |
| **Caution** | Avoid excessive friendship — it breaks **encapsulation** |

---

## 🇸🇦 الشرح بالعربية

### 💡 ما هي الكلاسات الصديقة (Friend Classes)؟

في لغة C++، الكلاس الصديق هو كلاس **يسمح له بالوصول إلى الأعضاء الخاصة (private)** في كلاس آخر.  
بشكل عام، البيانات الخاصة لا يمكن الوصول إليها من خارج الكلاس،  
لكن عندما نعلن كلاسًا آخر كـ **صديق**، نمنحه **صلاحية خاصة** للدخول إلى هذه البيانات.

> بمعنى آخر: كأنك تعطي "مفتاح البيت" لصديقك المقرب 🚪🔑

---

### 🧩 مثال من الحياة الواقعية

تخيل أنك تملك **منزلًا**، وغرفك الخاصة مقفلة.  
لكنك تثق بصديقك المقرّب، فتعطيه **مفتاحًا إضافيًا** ليدخل متى احتاج.  
هذا بالضبط ما تفعله **Friend Class** — تمنح كلاسًا آخر حق الوصول الخاص.

---

### ⚙️ المثال الأول: كلاس صديق بسيط

```cpp
#include <iostream>
using namespace std;

class Engine; // تعريف مسبق

class Car {
private:
    int fuel;

public:
    Car(int f) : fuel(f) {}

    friend class Engine; // نعلن أن Engine صديق
};

class Engine {
public:
    void showFuel(Car &c) {
        cout << "كمية الوقود: " << c.fuel << " لتر." << endl;
    }
};

int main() {
    Car myCar(50);
    Engine eng;
    eng.showFuel(myCar);
    return 0;
}
```

### 🧠 الشرح

- المتغير `fuel` داخل `Car` خاص (private).  
- لكن بفضل إعلان `Engine` كـ **كلاس صديق**، أصبح بإمكانه الوصول إلى `fuel`.  
- بدون كلمة `friend`، هذا الكود لن يعمل.

---

### ⚙️ المثال الثاني: تصميم واقعي (حساب بنكي وصراف آلي)

```cpp
#include <iostream>
using namespace std;

class BankAccount;

class ATM {
public:
    void withdraw(BankAccount &account, int amount);
};

class BankAccount {
private:
    int balance;

public:
    BankAccount(int bal) : balance(bal) {}

    friend class ATM; // نعلن أن ATM صديق
};

void ATM::withdraw(BankAccount &account, int amount) {
    if (amount <= account.balance) {
        account.balance -= amount;
        cout << "تمت عملية السحب بنجاح. الرصيد المتبقي: " << account.balance << endl;
    } else {
        cout << "رصيد غير كافٍ!" << endl;
    }
}

int main() {
    BankAccount acc(500);
    ATM atm;
    atm.withdraw(acc, 200);
    return 0;
}
```

### 🧠 الشرح

- الكلاس `BankAccount` يحتوي على متغير خاص `balance`.  
- الكلاس `ATM` يحتاج للوصول إليه ليقوم بعمليات السحب.  
- بإعلان `ATM` كصديق، يمكنه الوصول بشكل مباشر وآمن.  
- هذا يشبه العلاقة بين البنك والصراف الآلي في الواقع.  

---

### ⚖️ ملاحظات مهمة

| الخاصية | التوضيح |
|----------|----------|
| **الكلاس الصديق** | كلاس يمكنه الوصول إلى الأعضاء الخاصة لكلاس آخر |
| **طريقة التعريف** | `friend class ClassName;` |
| **نطاق الوصول** | الصداقة لا تنتقل بالوراثة |
| **حالات الاستخدام** | عند وجود علاقة قوية بين كلاسَين (مثل سيارة ↔ محرك أو بنك ↔ صراف آلي) |
| **تنبيه** | لا تفرط باستخدام الصداقة لأنها تقلل من مبدأ الإخفاء (Encapsulation) |

---

💡 **الخلاصة:**  
الكلاسات الصديقة مفيدة عندما تحتاج كائنات معينة أن تعمل معًا بشكل وثيق،  
لكن يجب استخدامها بحذر للحفاظ على مبدأ الخصوصية في البرمجة الكائنية.
