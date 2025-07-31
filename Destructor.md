
<h1 align="center">💣 Destructors in C++ | المدمرات في لغة C++</h1>

---

## 🇦🇪 الشرح باللغة العربية

### 💡 ما هو الـ Destructor (المدمّر)؟

الـ Destructor هو دالة خاصة تُستخدم عند "موت" الكائن (Object) — يعني عندما يتم حذفه أو يخرج من النطاق.

### 🧠 تخيل القصة:

- عند إنشاء كائن جديد → يتم استدعاء Constructor.
- عند انتهاء عمر الكائن → يتم استدعاء Destructor.

تخيل عندك وحش في لعبة:
- تنشئ الوحش: يظهر في الشاشة ✅
- يموت الوحش: تختفي آثاره ويُمسح من الذاكرة 💀

### ✅ خصائص الـ Destructor:

- اسمه **نفس اسم الكلاس** لكن يسبقه `~` (tilde).
- **لا يأخذ أي معاملات**.
- **لا يُرجع أي شيء** (no return type).
- يتم استدعاؤه **تلقائيًا** عند انتهاء الكائن.
- يُستخدم لتنظيف الذاكرة والموارد.

---

### 🧰 مثال: Destructor تلقائي عند انتهاء الكائن

```cpp
#include <iostream>
using namespace std;

class Monster {
public:
    Monster() {
        cout << "👾 تم إنشاء وحش جديد!
";
    }

    ~Monster() {
        cout << "💥 تم تدمير الوحش!
";
    }
};

int main() {
    cout << "🚪 بداية اللعبة
";
    Monster m1;
    {
        Monster m2;
        cout << "🧱 داخل كتلة داخلية
";
    } // هنا ينتهي m2 تلقائيًا

    cout << "🎮 نهاية اللعبة
";
    return 0;
}
```

---

### 🧰 مثال: Destructor مع new و delete

```cpp
class Box {
public:
    Box() {
        cout << "📦 تم إنشاء صندوق
";
    }

    ~Box() {
        cout << "🗑️ تم تدمير الصندوق
";
    }
};

int main() {
    Box* ptr = new Box();   // Constructor
    delete ptr;             // Destructor
    return 0;
}
```

🟡 ملاحظة: نسيان `delete` يؤدي إلى تسرب في الذاكرة (Memory Leak).

---

### 📌 مقارنة سريعة

| الوظيفة         | Constructor         | Destructor          |
|----------------|---------------------|---------------------|
| عند الإنشاء     | يعمل تلقائيًا         | ❌ لا يعمل            |
| عند التدمير     | ❌ لا يعمل            | يعمل تلقائيًا         |
| يقبل معاملات؟   | نعم                  | لا                  |
| نوع الإرجاع؟    | لا شيء (بدون نوع)     | لا شيء (بدون نوع)     |
| الاسم           | اسم الكلاس            | `~` واسم الكلاس       |

---

## 🇺🇸 Explanation in English

### 💡 What is a Destructor?

A **Destructor** is a special function that runs automatically when an object **dies** — either goes out of scope or is deleted.

### 🧠 Real-Life Analogy:

Imagine a monster in a game:
- You create it → It appears 👾 (Constructor)
- It dies → You remove it 💥 (Destructor)

### ✅ Features of a Destructor:

- Has the **same name** as the class, but with a `~` in front.
- **Takes no arguments**.
- **Returns nothing**.
- Called **automatically** when the object ends.
- Used to free memory and clean up.

---

### 🧰 Example: Automatic Destructor Call

```cpp
#include <iostream>
using namespace std;

class Monster {
public:
    Monster() {
        cout << "👾 Monster created!
";
    }

    ~Monster() {
        cout << "💥 Monster destroyed!
";
    }
};

int main() {
    cout << "🚪 Game starts
";
    Monster m1;
    {
        Monster m2;
        cout << "🧱 Inside a block
";
    } // m2 gets destroyed here

    cout << "🎮 Game ends
";
    return 0;
}
```

---

### 🧰 Example: Destructor with new and delete

```cpp
class Box {
public:
    Box() {
        cout << "📦 Box Created
";
    }

    ~Box() {
        cout << "🗑️ Box Destroyed
";
    }
};

int main() {
    Box* ptr = new Box();   // Constructor runs
    delete ptr;             // Destructor runs
    return 0;
}
```

🟡 Note: If you forget `delete`, the destructor won't run = memory leak.

---

### 📌 Quick Comparison

| Feature         | Constructor         | Destructor          |
|----------------|---------------------|---------------------|
| On creation     | Runs automatically  | ❌ Doesn't run       |
| On destruction  | ❌ Doesn't run       | Runs automatically  |
| Takes arguments? | Yes                 | No                  |
| Return type?     | None                | None                |
| Name             | Class name          | `~` + Class name     |
