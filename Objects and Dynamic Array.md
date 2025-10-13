
# 🧮 Objects and Dynamic Array in C++ | الكائنات والمصفوفة الديناميكية في البرمجة الكائنية

---

## 🇬🇧 English Explanation

### 💡 Concept Overview
In **C++**, a **dynamic array** is an array whose size is determined at runtime, not at compile time.  
We use the keyword `new` to allocate memory dynamically.

Objects, like integers or strings, can also be stored in dynamic arrays.  
This is useful when we don't know how many objects we need until the program runs.

---

### 🧩 Real-Life Analogy
Imagine a **hotel** 🏨:  
- A **static array** is like reserving 5 rooms no matter how many guests come.  
- A **dynamic array** is like opening new rooms **only when needed**.

This gives flexibility and better memory management.

---

### ⚙️ Example Code (From Dr. Mohammed Abu-Hadhoud)

```cpp

#include<iostream>
using namespace std;

class clsA {
public:

    // Dummy Constructor
    clsA() {}

    // Parameterized Constructor
    clsA(int value) {
        x = value;
    }

    int x;

    void Print() {
        cout << "The value of x=" << x << endl;
    }
};

int main() {
    short NumberOfObjects = 5;

    // Allocating dynamic array of objects
    clsA* arrA = new clsA[NumberOfObjects];

    // Assigning values using constructor
    for (int i = 0; i < NumberOfObjects; i++) {
        arrA[i] = clsA(i);
    }

    // Printing object contents
    for (int i = 0; i < NumberOfObjects; i++) {
        arrA[i].Print();
    }

    // Freeing the allocated memory
    delete[] arrA;

    return 0;
}
```

---

### 🧠 Step-by-Step Explanation

#### 1️⃣ Defining the Class
```cpp
class clsA {
public:
    int x;
    clsA() {}
    clsA(int value) { x = value; }
    void Print() { cout << "The value of x=" << x << endl; }
};
```
A simple class with a member `x`, constructors, and a print function.

#### 2️⃣ Allocating Dynamic Array
```cpp
clsA* arrA = new clsA[NumberOfObjects];
```
Allocates memory dynamically in the **heap** for 5 objects of `clsA`.  
Each object calls the **default constructor**.

#### 3️⃣ Assigning Values
```cpp
arrA[i] = clsA(i);
```
For each object, we assign a new value using the parameterized constructor.

#### 4️⃣ Printing Data
```cpp
arrA[i].Print();
```
Displays all the values stored in the objects.

📤 **Output:**
```
The value of x=0
The value of x=1
The value of x=2
The value of x=3
The value of x=4
```

#### 5️⃣ Deleting the Array
```cpp
delete[] arrA;
```
Releases the allocated memory to avoid memory leaks.

---

### ⚖️ Comparison Table

| Type | Allocation | Size Known At | Needs Delete | Memory Area |
|------|-------------|---------------|---------------|--------------|
| **Static Array** | Compile-time | Before program runs | ❌ No | Stack |
| **Dynamic Array** | Runtime | During execution | ✅ Yes | Heap |

---

### 💡 Summary
- **Dynamic arrays** give flexibility to create objects when needed.  
- Use `new` to allocate and `delete[]` to free memory.  
- Perfect for cases when the number of objects is unknown before the program runs.

---

## 🇸🇦 الشرح بالعربية

### 💡 المفهوم العام
في لغة **C++**، المصفوفة الديناميكية هي مصفوفة يتم تحديد حجمها **أثناء تشغيل البرنامج** وليس أثناء كتابة الكود.  
نستخدم الكلمة `new` لحجز مساحة في الذاكرة ديناميكيًا.

يمكننا تخزين **الكائنات (Objects)** في هذه المصفوفة تمامًا كما نخزن الأرقام أو النصوص.

---

### 🧩 تشبيه واقعي
تخيل أن عندك **فندق** 🏨:  
- المصفوفة الثابتة هي أنك تحجز 5 غرف فقط من البداية حتى لو ما في ضيوف.  
- المصفوفة الديناميكية تعني أنك تفتح عدد الغرف بناءً على عدد الضيوف الفعليين.

هذا يعطي مرونة كبيرة في استخدام الذاكرة.

---

### ⚙️ الكود مع الشرح

```cpp
#include<iostream>
using namespace std;

class clsA {
public:
    clsA() {}
    clsA(int value) { x = value; }
    int x;
    void Print() { cout << "The value of x=" << x << endl; }
};

int main() {
    short NumberOfObjects = 5;

    clsA* arrA = new clsA[NumberOfObjects];

    for (int i = 0; i < NumberOfObjects; i++) {
        arrA[i] = clsA(i);
    }

    for (int i = 0; i < NumberOfObjects; i++) {
        arrA[i].Print();
    }

    delete[] arrA;

    return 0;
}
```

---

### 🧠 الشرح خطوة بخطوة

#### 1️⃣ تعريف الكلاس
الكلاس يحتوي على متغير `x`، ودالة `Print()` لطباعة قيمته، وباني (constructor) لإعطائه قيمة.

#### 2️⃣ إنشاء مصفوفة ديناميكية
```cpp
clsA* arrA = new clsA[NumberOfObjects];
```
هذه الجملة تحجز مساحة في الذاكرة لتخزين 5 كائنات من نوع `clsA`.

#### 3️⃣ تعبئة المصفوفة
```cpp
arrA[i] = clsA(i);
```
كل كائن في المصفوفة يأخذ قيمة مختلفة من `i` (0 إلى 4).

#### 4️⃣ الطباعة
```cpp
arrA[i].Print();
```
تمر على كل كائن وتطبع محتواه.

📤 الناتج:
```
The value of x=0
The value of x=1
The value of x=2
The value of x=3
The value of x=4
```

#### 5️⃣ حذف المصفوفة
```cpp
delete[] arrA;
```
تُستخدم لحذف المصفوفة وتفريغ الذاكرة بعد الانتهاء.

---

### ⚖️ مقارنة سريعة

| النوع | طريقة الحجز | متى يعرف الحجم؟ | هل تحتاج delete؟ | مكان التخزين |
|--------|--------------|------------------|------------------|----------------|
| **Static Array** | أثناء كتابة الكود | قبل التشغيل | ❌ لا | Stack |
| **Dynamic Array** | أثناء التشغيل | وقت التنفيذ | ✅ نعم | Heap |

---

### 💡 الخلاصة
- المصفوفات الديناميكية مهمة جدًا لما ما تعرف عدد الكائنات مسبقًا.  
- تعطي مرونة كبيرة في التعامل مع البيانات.  
- تذكّر دائمًا حذفها باستخدام `delete[]` بعد الانتهاء لتجنب تسريب الذاكرة.

