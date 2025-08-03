
# 🏗️ Multi-Level Inheritance in C++ | الوراثة متعددة المستويات في C++

---

## 🇺🇸 Explanation in English

### 🧠 What is Multi-Level Inheritance?

Multi-Level Inheritance means a **class inherits from a class that itself inherits from another class**.

Example:  
`Grandfather → Father → Son`

Each child class inherits all the properties and methods of its parent and ancestors.

---

### 👨‍👨‍👦 Real-life Analogy

- 👴 Grandfather: has family name and house.
- 👨 Father: inherits from grandfather, adds a car.
- 👦 Son: inherits everything from father and grandfather, and adds his toy.

> The son ends up with **all features from his ancestors** + his own.

---

### 🧰 C++ Code Example

```cpp
#include <iostream>
using namespace std;

class Grandfather {
public:
    void familyName() {
        cout << "👴 Family name: Alhamid\n";
    }
};

class Father : public Grandfather {
public:
    void drive() {
        cout << "🚗 Father is driving the car.\n";
    }
};

class Son : public Father {
public:
    void play() {
        cout << "🎮 Son is playing with his toy.\n";
    }
};

int main() {
    Son belal;
    belal.familyName();  // from Grandfather
    belal.drive();       // from Father
    belal.play();        // from Son
    return 0;
}
```

---

### 📌 Key Benefits

| Benefit               | Why It Matters                         |
|-----------------------|-----------------------------------------|
| ✅ Code reuse          | No need to rewrite shared functionality |
| ✅ Clear hierarchy     | Shows natural family-like structure     |
| ✅ Extendable design   | Easy to add more features in new classes|

---

### 🔁 Comparison Table

| Inheritance Type        | Structure            | Example                      |
|-------------------------|----------------------|-------------------------------|
| Single Inheritance      | A → B                | Animal → Dog                  |
| Multi-Level Inheritance | A → B → C            | Grandfather → Father → Son   |
| Multiple Inheritance    | A + B → C            | Artist + Athlete → Superstar |

---

> In Multi-Level Inheritance, each new class gets smarter and richer with inherited power 💡

---

## 🇸🇦 الشرح باللغة العربية

### 🧠 ما هي الوراثة متعددة المستويات (Multi-Level Inheritance)؟

هي عندما يرث كلاس من كلاس، وهذا الكلاس نفسه يكون قد ورث من كلاس آخر.

مثال:  
`الجد ← الأب ← الإبن`

كل كلاس يرث **كل شيء من الذي سبقه**، ويضيف خصائصه الخاصة.

---

### 👨‍👨‍👦 تشبيه من الحياة الواقعية

- 👴 الجد: عنده اسم العائلة وبيت.
- 👨 الأب: ورث من الجد، وأصبح لديه سيارة.
- 👦 الإبن: ورث كل شيء من الأب والجد، وأصبح لديه لعبة.

> النتيجة: الإبن عنده **كل شيء من الجد والأب** + أشياءه الخاصة.

---

### 🧰 مثال بلغة C++

```cpp
#include <iostream>
using namespace std;

class Grandfather {
public:
    void familyName() {
        cout << "👴 اسم العائلة: الحميـد\n";
    }
};

class Father : public Grandfather {
public:
    void drive() {
        cout << "🚗 الأب يقود السيارة.\n";
    }
};

class Son : public Father {
public:
    void play() {
        cout << "🎮 الإبن يلعب بلعبته.\n";
    }
};

int main() {
    Son belal;
    belal.familyName();  // من الجد
    belal.drive();       // من الأب
    belal.play();        // من الإبن
    return 0;
}
```

---

### 📌 فوائد الوراثة المتعددة المستويات

| الفائدة                  | لماذا هي مهمة؟                        |
|--------------------------|----------------------------------------|
| ✅ إعادة استخدام الكود     | لا داعي لتكرار الوظائف المشتركة        |
| ✅ هيكل منطقي وواضح        | يشبه علاقات العائلة                   |
| ✅ سهولة التوسعة والتطوير  | يمكنك إضافة ميزات جديدة بسهولة         |

---

### 🔁 مقارنة بين أنواع الوراثة

| نوع الوراثة               | الشكل               | المثال                        |
|---------------------------|----------------------|-------------------------------|
| Single Inheritance         | A ← B                | حيوان ← كلب                   |
| Multi-Level Inheritance    | A ← B ← C            | جد ← أب ← إبن                 |
| Multiple Inheritance       | A + B → C            | رسام + رياضي ← نجم شامل       |

---

> الوراثة متعددة المستويات = كل جيل يضيف قيمة، ويورث القوة للجيل اللي بعده 💪
