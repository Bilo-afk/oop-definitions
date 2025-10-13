
# 🤝 Friend Functions in C++ | الدوال الصديقة في البرمجة الكائنية

---

## 🇬🇧 English Explanation

### 💡 What is a Friend Function?

In **C++**, a **friend function** is a function that has **access to private and protected members** of a class — even though it is **not a member of that class**.

Normally, only class methods can access private data, but by declaring a function as a **friend**, you give it special permission.

> Think of it like giving a guest a temporary access key to your house — they’re not part of the family, but they can still come in!

---

### 🧩 Real-Life Analogy

Imagine a **bank system** where a **manager** (external function) needs to **check the balance** of a customer’s account.  
The manager is not part of the `BankAccount` class, but has special permission to look inside — because he’s a **trusted friend**.

That’s exactly how a **friend function** works.

---

### ⚙️ Example 1: Basic Friend Function

```cpp
#include <iostream>
using namespace std;

class Box {
private:
    int width;

public:
    Box(int w) : width(w) {}

    // Declare friend function
    friend void printWidth(Box b);
};

// Definition of the friend function
void printWidth(Box b) {
    cout << "Box width: " << b.width << endl;
}

int main() {
    Box b1(10);
    printWidth(b1); // Accesses private member width
    return 0;
}
```

### 🧠 Explanation

- The variable `width` is **private**.  
- The function `printWidth()` is **not part of the class**, but it’s declared as a **friend** inside `Box`.  
- Therefore, it can access `width` directly.  
- Without `friend`, the compiler would throw an **access error**.

---

### ⚙️ Example 2: Two Classes Working Together

```cpp
#include <iostream>
using namespace std;

class Rectangle;

class Painter {
public:
    void paint(Rectangle &r);
};

class Rectangle {
private:
    int width, height;

public:
    Rectangle(int w, int h) : width(w), height(h) {}

    // Painter is allowed to access private members
    friend void Painter::paint(Rectangle &r);
};

void Painter::paint(Rectangle &r) {
    cout << "Painting rectangle of " << r.width << "x" << r.height << endl;
}

int main() {
    Rectangle rect(10, 5);
    Painter artist;
    artist.paint(rect);
    return 0;
}
```

### 🧠 Explanation

- The `Painter` class has a method `paint()` that needs access to the **private dimensions** of `Rectangle`.  
- Instead of exposing these members with getters, we make `paint()` a **friend function**.  
- This allows the `Painter` to work **closely** with `Rectangle` without breaking **encapsulation** too much.

---

### ⚖️ Key Notes

| Feature | Description |
|----------|-------------|
| **Friend Function** | Can access private/protected members of a class |
| **Declared Inside** | Class definition using `friend` keyword |
| **Belongs To** | Not a class member |
| **Access Scope** | Friendship is **not inherited** |
| **Best Use Case** | When two entities must work very closely (like Bank ↔ Manager, or Car ↔ Mechanic) |

---

## 🇸🇦 الشرح بالعربية

### 💡 ما هي الدالة الصديقة (Friend Function)؟

في لغة C++، الدالة الصديقة هي دالة **يمكنها الوصول إلى الأعضاء الخاصة (private)** في كلاس معين،  
حتى وإن **لم تكن عضوًا من أعضاء هذا الكلاس**.

عادةً لا يمكن لأي دالة خارجية الوصول إلى البيانات الخاصة داخل الكلاس،  
لكن عندما نعرّفها باستخدام الكلمة **friend**، فإننا نعطيها صلاحية خاصة.

> مثل إعطاء ضيفك مفتاحًا مؤقتًا ليدخل منزلك — ليس من العائلة، لكنه مسموح له بالدخول 🚪🔑

---

### 🧩 مثال من الحياة الواقعية

تخيل نظامًا بنكيًا يحتوي على كلاس `BankAccount`.  
المدير (وهو دالة خارجية) يحتاج أن يطّلع على رصيد العميل.  
رغم أنه ليس جزءًا من `BankAccount`، إلا أن البنك منحه صلاحية خاصة للوصول.  
هذا بالضبط هو عمل **Friend Function**.

---

### ⚙️ المثال الأول: دالة صديقة بسيطة

```cpp
#include <iostream>
using namespace std;

class Box {
private:
    int width;

public:
    Box(int w) : width(w) {}

    friend void printWidth(Box b);
};

void printWidth(Box b) {
    cout << "عرض الصندوق: " << b.width << endl;
}

int main() {
    Box b1(10);
    printWidth(b1);
    return 0;
}
```

### 🧠 الشرح

- المتغير `width` خاص ولا يمكن الوصول إليه من الخارج.  
- الدالة `printWidth()` ليست جزءًا من الكلاس، لكنها معرفة كـ **صديقة**.  
- لذلك يمكنها الوصول إلى `width` مباشرة.  
- بدون الكلمة `friend`، سيعطي المترجم خطأ وصول.

---

### ⚙️ المثال الثاني: التعاون بين كلاسَين

```cpp
#include <iostream>
using namespace std;

class Rectangle;

class Painter {
public:
    void paint(Rectangle &r);
};

class Rectangle {
private:
    int width, height;

public:
    Rectangle(int w, int h) : width(w), height(h) {}

    friend void Painter::paint(Rectangle &r);
};

void Painter::paint(Rectangle &r) {
    cout << "رسم مستطيل أبعاده " << r.width << "x" << r.height << endl;
}

int main() {
    Rectangle rect(10, 5);
    Painter artist;
    artist.paint(rect);
    return 0;
}
```

### 🧠 الشرح

- الكلاس `Rectangle` يحتوي على متغيرين خاصين: `width` و `height`.  
- الكلاس `Painter` يحتاج الوصول إليهما للرسم.  
- لذلك جعلنا الدالة `paint()` دالة صديقة داخل `Rectangle`.  
- وهكذا يستطيع `Painter` الوصول مباشرة دون كسر مبدأ الإخفاء تمامًا.

---

### ⚖️ ملاحظات مهمة

| الخاصية | التوضيح |
|----------|----------|
| **الدالة الصديقة** | يمكنها الوصول إلى الأعضاء الخاصة لكلاس معين |
| **مكان التعريف** | داخل الكلاس باستخدام الكلمة `friend` |
| **الانتماء** | ليست دالة عضو داخل الكلاس |
| **نطاق الصداقة** | الصداقة لا تُورّث |
| **أفضل استخدام** | عندما تحتاج دوال خارجية التعاون المباشر مع الكلاس (مثل بنك ↔ مدير، أو سيارة ↔ ميكانيكي) |

---

💡 **الخلاصة:**  
الدوال الصديقة مفيدة عندما تحتاج الوصول إلى معلومات خاصة في كلاس آخر لأداء وظيفة محددة،  
لكن يجب استخدامها **بحذر** حتى لا يتم كسر مبدأ **الخصوصية (Encapsulation)** في البرمجة الكائنية.
