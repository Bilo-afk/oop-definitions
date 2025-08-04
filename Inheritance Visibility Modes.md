
# 🔒 Inheritance Visibility Modes in C++ | أنماط رؤية الوراثة في C++

---

## 🇺🇸 Explanation in English

### 🧠 What are Inheritance Visibility Modes?

When one class inherits from another, we specify how it inherits using a visibility mode:  
```cpp
class Derived : public Base { ... };
```

The keyword before `Base` — `public`, `protected`, or `private` — is the **inheritance mode**.  
It determines **how access specifiers from the base class behave in the derived class**.

---

### 🚪 The Three Modes

| Inheritance Mode | What Happens?                                                  |
|------------------|----------------------------------------------------------------|
| `public`         | Public and protected members stay the same.                    |
| `protected`      | Public becomes protected, protected stays protected.           |
| `private`        | Both public and protected become private.                      |

> 🔐 `private` members in the base class are **never inherited**, regardless of the mode.

---

### 👨‍👦 Analogy

- **Public inheritance** = Inheriting the family name and sharing it with the world.
- **Protected inheritance** = Inheriting the name but keeping it within the family.
- **Private inheritance** = Inheriting the name but keeping it to yourself only.

---

### 🧰 Example in C++

```cpp
#include <iostream>
using namespace std;

class Base {
public:
    int pub = 1;
protected:
    int prot = 2;
private:
    int priv = 3;
};

class PublicChild : public Base {
public:
    void show() {
        cout << "Public: " << pub << endl;     // ✅
        cout << "Protected: " << prot << endl; // ✅
        // cout << priv << endl;              // ❌ Not allowed
    }
};

class ProtectedChild : protected Base {
public:
    void show() {
        cout << "Public (now protected): " << pub << endl;   // ✅
        cout << "Protected: " << prot << endl;               // ✅
    }
};

class PrivateChild : private Base {
public:
    void show() {
        cout << "Public (now private): " << pub << endl;     // ✅
        cout << "Protected (now private): " << prot << endl; // ✅
    }
};

int main() {
    PublicChild pc;
    pc.show();
    cout << pc.pub << endl; // ✅ Accessible because it's still public

    // ProtectedChild ppc;
    // cout << ppc.pub << endl; ❌ Not accessible (now protected)

    // PrivateChild prc;
    // cout << prc.pub << endl; ❌ Not accessible (now private)

    return 0;
}
```

---

### 📌 Summary Table

| Base Member     | `public` inheritance | `protected` inheritance | `private` inheritance |
|------------------|----------------------|--------------------------|------------------------|
| `public`         | stays public         | becomes protected        | becomes private        |
| `protected`      | stays protected      | stays protected          | becomes private        |
| `private`        | not inherited        | not inherited            | not inherited          |

---

### ✅ When to Use?

| Mode        | When to Use It                                                  |
|-------------|------------------------------------------------------------------|
| `public`    | When the derived class is a true subtype and should expose all base features |
| `protected` | When the base features are for derived classes only             |
| `private`   | When you only want to use base features internally              |

---

## 🇸🇦 الشرح باللغة العربية

### 🧠 ما هي أنماط رؤية الوراثة؟

عند وراثة كلاس من كلاس آخر، نحدد طريقة الوراثة باستخدام `public`, `protected`, أو `private`:

```cpp
class Derived : public Base { ... };
```

الكلمة قبل `Base` تُعرف بـ "نمط الوراثة"، وهي تتحكم في **كيف تنتقل صلاحيات الوصول** من الأب إلى الابن.

---

### 🚪 الأنماط الثلاثة

| نوع الوراثة     | ماذا يحدث؟                                                   |
|------------------|-------------------------------------------------------------|
| `public`         | تبقى صلاحيات `public` و `protected` كما هي.                 |
| `protected`      | `public` تصبح `protected`، و`protected` تبقى `protected`.    |
| `private`        | `public` و `protected` تتحول إلى `private`.                  |

> ⚠️ ملاحظة: أي عنصر `private` في الكلاس الأب لا يُورث أبدًا.

---

### 👨‍👦 تشبيه واقعي

- `public`: ورثت اسم العائلة وشاركت به علنًا.
- `protected`: ورثته لكن فقط داخل العائلة.
- `private`: ورثته واحتفظت به لنفسك فقط.

---

### 🧰 مثال عملي بلغة C++

```cpp
#include <iostream>
using namespace std;

class Base {
public:
    int pub = 1;
protected:
    int prot = 2;
private:
    int priv = 3;
};

class PublicChild : public Base {
public:
    void show() {
        cout << "عام: " << pub << endl;         // ✅
        cout << "محمي: " << prot << endl;       // ✅
        // cout << priv << endl;                // ❌ غير مسموح
    }
};

class ProtectedChild : protected Base {
public:
    void show() {
        cout << "عام (أصبح محمي): " << pub << endl;   // ✅
        cout << "محمي: " << prot << endl;             // ✅
    }
};

class PrivateChild : private Base {
public:
    void show() {
        cout << "عام (أصبح خاص): " << pub << endl;     // ✅
        cout << "محمي (أصبح خاص): " << prot << endl;   // ✅
    }
};

int main() {
    PublicChild pc;
    pc.show();
    cout << pc.pub << endl; // ✅ لأنه بقي عام

    // ProtectedChild ppc;
    // cout << ppc.pub << endl; ❌ أصبح محمي

    // PrivateChild prc;
    // cout << prc.pub << endl; ❌ أصبح خاص

    return 0;
}
```

---

### 📌 جدول تلخيصي

| العضو في الأب     | `public` وراثة | `protected` وراثة | `private` وراثة |
|--------------------|----------------|-------------------|-----------------|
| `public`           | يبقى `public`  | يصبح `protected`  | يصبح `private`  |
| `protected`        | يبقى `protected`| يبقى `protected` | يصبح `private`  |
| `private`          | لا يُورث        | لا يُورث           | لا يُورث         |

---

### ✅ متى تستخدم كل نوع؟

| النوع        | متى نستخدمه؟                                                  |
|--------------|---------------------------------------------------------------|
| `public`     | عندما تريد أن يستخدم الكلاس الابن جميع وظائف الأب علنًا.      |
| `protected`  | عندما تكون الوظائف فقط للكلاسات المشتقة.                      |
| `private`    | عندما لا تريد كشف أي شيء من الأب خارج الكلاس الجديد.         |
