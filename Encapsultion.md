
<h1 align="center">🔒 Encapsulation in C++ | التغليف في لغة C++</h1>

---

## 🇦🇪 الشرح باللغة العربية

### 🎁 ما هو التغليف (Encapsulation)؟

تخيل عندك **علبة سحرية** فيها أزرار من الخارج، لكنك لا تستطيع رؤية ما بداخلها.  
كل زر يؤدي وظيفة، ولكن لا أحد يعرف التفاصيل داخل العلبة.  
هكذا يعمل التغليف في البرمجة!

### 🔐 ماذا يعني ذلك في البرمجة؟

- نضع **المتغيرات** داخل "علبة" (`class`).
- ونضيف **أزرار** (دوال `functions`) للتحكم بها.
- لا نسمح لأي شخص بتغيير البيانات مباشرة.
- فقط نسمح باستخدام الأزرار المحددة لذلك.

### ✅ الفائدة:

- حماية البيانات من التعديل الخاطئ.
- تنظيم الكود وجعله أكثر أمانًا وسهولة في الاستخدام.

### 🧰 مثال بلغة C++

```cpp
#include <iostream>
using namespace std;

// تعريف الصنف Student
class Student {
private:
    int age; // متغير خاص - لا يمكن الوصول له من الخارج

public:
    // دالة لتعيين العمر مع تحقق
    void setAge(int a) {
        if (a >= 0 && a <= 120)
            age = a;
        else
            cout << "⚠️ عمر غير منطقي!\n";
    }

    // دالة للحصول على قيمة العمر
    int getAge() {
        return age;
    }
};

int main() {
    Student s1;
    s1.setAge(25);                     // استخدام الدالة لتعيين العمر
    cout << "📌 العمر هو: " << s1.getAge() << endl; // استخدام الدالة للحصول عليه
    return 0;
}
```

### 📌 التلخيص في جدول:

| الشيء الحقيقي     | في البرمجة        |
|------------------|------------------|
| علبة سحرية         | class (فئة)       |
| ما بداخل العلبة    | البيانات (متغيرات) |
| الأزرار            | الدوال (functions) |
| لا تلمس الداخل!     | نستخدم `private`   |
| استخدم الأزرار فقط | نستخدم `public`    |

---

## 🇺🇸 Explanation in English

### 🎁 What is Encapsulation?

Imagine you have a **magic box** with buttons on the outside.  
You press a button and something happens inside, but you **don’t know how** it works.  
This is exactly what Encapsulation means in programming!

### 🔐 In Programming Terms:

- We hide **data (variables)** inside a `class`.
- We provide **buttons** (`functions`) to interact with the data.
- No one can directly modify the internal data.
- Only specific, safe access is allowed through functions.

### ✅ Benefits:

- Protects data from accidental corruption.
- Keeps code organized, clean, and safe.

### 🧰 Example in C++

```cpp
#include <iostream>
using namespace std;

// Student class
class Student {
private:
    int age; // hidden data

public:
    // function to safely set the age
    void setAge(int a) {
        if (a >= 0 && a <= 120)
            age = a;
        else
            cout << "⚠️ Invalid age!\n";
    }

    // function to get the age
    int getAge() {
        return age;
    }
};

int main() {
    Student s1;
    s1.setAge(25);                       // using function to set age
    cout << "📌 Age is: " << s1.getAge() << endl; // using function to get age
    return 0;
}
```

### 📌 Summary Table:

| Real-life Concept | Programming Equivalent |
|------------------|------------------------|
| Magic Box         | `class`                |
| Inside the Box    | Data (`variables`)     |
| Buttons           | `functions`            |
| Don't touch inside | Use `private`         |
| Only use buttons  | Use `public`           |
