
# 🧬 Inheritance in C++ | الوراثة في C++

---

## 🇺🇸 Explanation in English

### 🧠 What is Inheritance?

> Inheritance means: **a class can receive properties and behaviors from another class**.

---

### 👦 Simple Analogy – The Family

Imagine a **Parent**:
- Has a name, a house, a last name.

Now imagine a **Child**:
- Inherits the name, the house, and the last name **from the parent**.
- But also has their own toys or school.

That’s **inheritance**!

---

### 💡 Why Use It?

- To **reuse code** instead of repeating it.
- To keep classes **logical and organized**.

---

### ✅ Golden Rule

> If you can say: "X is a kind of Y" → Use inheritance.

Examples:
- 🐶 Dog is a kind of Animal → `Dog` inherits from `Animal`.
- 🚗 Car is a kind of Vehicle → `Car` inherits from `Vehicle`.
- 👨‍🎓 Student is a kind of Person → `Student` inherits from `Person`.

---

### 🧰 Code Example

```cpp
#include <iostream>
using namespace std;

class Animal {
public:
    void eat() {
        cout << "🐾 Animal is eating...\n";
    }

    void sleep() {
        cout << "💤 Animal is sleeping...\n";
    }
};

class Dog : public Animal {
public:
    void bark() {
        cout << "🐶 Dog is barking!\n";
    }
};

int main() {
    Dog myDog;
    myDog.eat();     // from Animal
    myDog.sleep();   // from Animal
    myDog.bark();    // from Dog
    return 0;
}
```

---

### 📌 Breakdown

- `Dog` didn’t define `eat()` or `sleep()` itself.
- But it can use them **because it inherited from `Animal`**.
- It also added its own behavior: `bark()`.

---

### 🧩 Analogy Table

| Real World             | In Code          |
|------------------------|------------------|
| Parent has a car       | Class has methods |
| Child inherits the car | Class inherits    |
| Child has their toy    | Class adds new methods |

---

### 📚 Types of Inheritance in C++

| Type       | Meaning                           |
|------------|-----------------------------------|
| `public`   | Regular inheritance ✅             |
| `private`  | Inherited internally only         |
| `protected`| A mix of public and private       |

🔑 Just focus on `public` for now — it's the most common and beginner-friendly.

---

> Inheritance = Getting everything from your parent, then building your own touch.

---

## 🇸🇦 الشرح باللغة العربية

### 🧠 ما هي الوراثة (Inheritance)؟

> الوراثة تعني أن **كلاس يأخذ خصائص ودوال من كلاس ثاني**.

---

### 👶 تشبيه بسيط – العائلة

عندنا **أب**:
- عنده اسم، لقب، بيت.

و**ابن**:
- ورث الاسم والبيت واللقب **من الأب**.
- لكن عنده أشياء خاصة فيه، مثل ألعاب أو مدرسة.

هذا هو مفهوم **الوراثة**!

---

### 💡 لماذا نستخدم الوراثة؟

- لإعادة استخدام الكود بدل ما نعيد كتابته.
- لتنظيم الكلاسات بشكل منطقي.

---

### ✅ القاعدة الذهبية

> إذا بتقدر تقول: "X هو نوع من Y" → استخدم الوراثة.

أمثلة:
- 🐶 الكلب هو نوع من حيوان → `Dog` يرث من `Animal`.
- 🚗 السيارة نوع من مركبة → `Car` يرث من `Vehicle`.
- 👨‍🎓 الطالب نوع من شخص → `Student` يرث من `Person`.

---

### 🧰 مثال عملي بلغة C++

```cpp
#include <iostream>
using namespace std;

class Animal {
public:
    void eat() {
        cout << "🐾 الحيوان يأكل...\n";
    }

    void sleep() {
        cout << "💤 الحيوان ينام...\n";
    }
};

class Dog : public Animal {
public:
    void bark() {
        cout << "🐶 الكلب ينبح!\n";
    }
};

int main() {
    Dog myDog;
    myDog.eat();     // من Animal
    myDog.sleep();   // من Animal
    myDog.bark();    // من Dog
    return 0;
}
```

---

### 📌 شرح المثال

- `Dog` ما كتبنا فيه `eat()` أو `sleep()`.
- لكنه قدر يستخدمهم لأنه **ورثهم من `Animal`**.
- وأضفنا عليه دالة خاصة فيه: `bark()`.

---

### 🧩 جدول التشبيه النهائي

| في الحياة         | في الكود             |
|-------------------|----------------------|
| الأب عنده سيارة    | كلاس فيه دوال         |
| الابن ورث السيارة  | كلاس يرث من كلاس آخر   |
| الابن عنده ألعاب   | كلاس أضاف دوال خاصة   |

---

### 📚 أنواع الوراثة في C++

| النوع         | الشرح                    |
|---------------|--------------------------|
| `public`      | الوراثة العادية ✅        |
| `private`     | وراثة داخلية فقط         |
| `protected`   | حالة وسط                 |

📌 ركّز فقط على `public` بالبداية — هو الأسهل والأشهر.

---

> الوراثة = أن ترث كل شيء من الأب، ثم تضيف بصمتك الخاصة 👨‍👦
