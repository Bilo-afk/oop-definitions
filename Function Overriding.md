
# 🔁 Function Overriding in C++ | إعادة تعريف الدوال في C++

---

## 🇺🇸 Explanation in English

### 🧠 What is Function Overriding?

Function overriding occurs when a **derived (child) class** defines a **function with the same name and parameters** as a function in its **base (parent) class**, but **with a different implementation**.

---

### 👦 Simple Analogy

Imagine:

- The **Parent** says: “I am a person.”
- The **Child** says: “I am a student.”

Both have a `speak()` function, but the **child overrides** the parent’s version with its own.

---

### 🎯 Why Use It?

- To **customize behavior** in the child class.
- To allow **different actions** for different derived classes, using the same function name.

---

### 🧰 Example in C++

```cpp
#include <iostream>
using namespace std;

class Person {
public:
    void speak() {
        cout << "👤 I am a person.\n";
    }
};

class Student : public Person {
public:
    void speak() {
        cout << "🎓 I am a student.\n";
    }
};

int main() {
    Person p;
    Student s;

    p.speak(); // Output: I am a person.
    s.speak(); // Output: I am a student.
    return 0;
}
```

---

### 📌 Important Notes

- The function in the base class **must be public**.
- The name and parameters **must be identical**.
- No need to use `override` keyword in basic C++, but it can be used for clarity.

---

### 🧩 Overloading vs. Overriding

| Feature            | Overloading                        | Overriding                          |
|--------------------|------------------------------------|-------------------------------------|
| Same class?        | ✅ Yes                             | ❌ No (between parent & child)      |
| Same function name?| ✅ Yes                             | ✅ Yes                              |
| Same parameters?   | ❌ No (different)                  | ✅ Yes (identical)                  |
| Purpose            | Different versions of same name   | Redefine behavior in child class   |

---

> Overriding = Redefining parent’s method to suit the child’s behavior.

---

## 🇸🇦 الشرح باللغة العربية

### 🧠 ما هي إعادة تعريف الدوال (Function Overriding)؟

هي عندما يقوم **كلاس الابن** بكتابة **دالة بنفس اسم ومعاملات** دالة موجودة في **الكلاس الأب**،  
لكن **بتنفيذ مختلف ومخصص له**.

---

### 👶 تشبيه بسيط

تخيل:

- **الأب** لما يتكلم بيقول: “أنا إنسان”.
- **الابن** لما يتكلم بيقول: “أنا طالب”.

كلاهما عنده دالة `speak()`، لكن الابن كتب نسخته الخاصة → **غـطّى** (Override) نسخة الأب.

---

### 🎯 لماذا نستخدمها؟

- لتخصيص سلوك الدالة في الكلاس الابن.
- لكتابة أكواد أكثر مرونة تعتمد على الوراثة.

---

### 🧰 مثال بلغة C++

```cpp
#include <iostream>
using namespace std;

class Person {
public:
    void speak() {
        cout << "👤 أنا إنسان.\n";
    }
};

class Student : public Person {
public:
    void speak() {
        cout << "🎓 أنا طالب.\n";
    }
};

int main() {
    Person p;
    Student s;

    p.speak(); // الناتج: أنا إنسان
    s.speak(); // الناتج: أنا طالب
    return 0;
}
```

---

### 📌 ملاحظات هامة

- يجب أن تكون دالة الأب `public` لكي ترثها الكلاسات الأخرى.
- الاسم والمعاملات يجب أن يكونا **متطابقين تمامًا**.
- لا حاجة لاستخدام `override` في C++ التقليدية، لكن يمكن إضافته لتوضيح المقصود.

---

### 🧩 الفرق بين Overloading و Overriding

| المقارنة             | Overloading (زيادة التحميل)       | Overriding (إعادة التعريف)         |
|----------------------|------------------------------------|------------------------------------|
| داخل نفس الكلاس؟     | ✅ نعم                             | ❌ لا (بين الأب والابن)             |
| نفس اسم الدالة؟      | ✅ نعم                             | ✅ نعم                              |
| نفس المعاملات؟       | ❌ لا (تختلف)                      | ✅ نعم (نفسها)                      |
| الهدف؟               | تنويع في نفس الاسم                | تغيير السلوك في كلاس الابن         |

---

> Overriding = إعادة تعريف دالة الأب لتناسب سلوك الابن.
