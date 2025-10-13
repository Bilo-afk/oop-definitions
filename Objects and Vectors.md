
# 🧩 Objects and Vectors in C++ | الكائنات والفكتور في البرمجة الكائنية

---

## 🇬🇧 English Explanation

### 💡 Concept Overview
In **C++**, a **vector** is a dynamic array that can grow or shrink in size.  
It can hold any type of data, including **objects** of classes.

This means you can store multiple **objects** of a class inside a `vector`, just like storing numbers or strings.

---

### 🧩 Real-Life Analogy

Think of a **parking lot** as a vector, and each **car** as an object.  
When a new car arrives, you add it to the parking lot.  
When you want to see all cars, you go through each one and check its info.

That’s exactly what happens when you add **objects** to a **vector**.

---

### ⚙️ Example Code (From Dr. Mohammed Abu-Hadhoud)

```cpp
//ProgrammingAdvices.com
//Mohammed Abu-Hadhoud
#include<iostream>
#include<vector>
using namespace std;

class clsA {
public:
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
    vector<clsA> v1;
    short NumberOfObjects = 5;

    // Inserting objects into vector
    for (int i = 0; i < NumberOfObjects; i++) {
        v1.push_back(clsA(i));
    }

    // Printing object contents
    for (int i = 0; i < NumberOfObjects; i++) {
        v1[i].Print();
    }

    system("pause>0");
}
```

---

### 🧠 Step-by-Step Explanation

#### 1️⃣ Class Definition
```cpp
class clsA {
public:
    int x;
    clsA(int value) { x = value; }
    void Print() { cout << "The value of x=" << x << endl; }
};
```
A simple class with a variable `x`, a constructor to assign it, and a function to print it.

#### 2️⃣ Creating a Vector
```cpp
vector<clsA> v1;
short NumberOfObjects = 5;
```
We create a **vector named `v1`** to store multiple objects of type `clsA`.

#### 3️⃣ Adding Objects to the Vector
```cpp
for (int i = 0; i < NumberOfObjects; i++) {
    v1.push_back(clsA(i));
}
```
The loop creates 5 objects with values (0,1,2,3,4) and adds each one using `push_back()`.

#### 4️⃣ Accessing Objects from the Vector
```cpp
for (int i = 0; i < NumberOfObjects; i++) {
    v1[i].Print();
}
```
We loop through the vector and call `Print()` on each object.

📤 **Output:**
```
The value of x=0
The value of x=1
The value of x=2
The value of x=3
The value of x=4
```

---

### ⚖️ Summary Table

| Function | Description |
|-----------|--------------|
| `vector<clsA>` | Creates a dynamic list of `clsA` objects |
| `push_back()` | Adds an object to the end of the vector |
| `v1[i]` | Access the i-th object in the vector |
| `Print()` | Method inside the class to display data |

---

### 💡 Conclusion
Vectors allow us to store and manage multiple **objects** dynamically.  
They are powerful tools for organizing and iterating over complex data structures in C++.

---

## 🇸🇦 الشرح بالعربية

### 💡 المفهوم العام
في لغة **C++**، الفكتور `vector` هو عبارة عن **مصفوفة ديناميكية** يمكنها أن تتوسع أو تتقلص تلقائيًا.  
ويمكن أن تحتوي على أي نوع من البيانات، بما في ذلك **الكائنات (Objects)** من الكلاسات.

بالتالي، يمكننا تخزين عدة كائنات من كلاس واحد داخل فكتور واحد بسهولة.

---

### 🧩 تشبيه واقعي
تخيل أن عندك **موقف سيارات** 🅿️ يمثل الفكتور،  
وكل **سيارة** 🚗 تمثل كائنًا (Object).  
كل مرة تأتي سيارة جديدة → تضيفها للموقف (`push_back`).  
وإذا أردت أن ترى كل السيارات → تمر عليها وتعرض معلوماتها (`Print()`).

---

### ⚙️ الكود مع الشرح

```cpp
#include<iostream>
#include<vector>
using namespace std;

class clsA {
public:
    clsA(int value) { x = value; }
    int x;
    void Print() { cout << "The value of x=" << x << endl; }
};

int main() {
    vector<clsA> v1;
    short NumberOfObjects = 5;

    for (int i = 0; i < NumberOfObjects; i++) {
        v1.push_back(clsA(i));
    }

    for (int i = 0; i < NumberOfObjects; i++) {
        v1[i].Print();
    }

    system("pause>0");
}
```

---

### 🧠 الشرح خطوة بخطوة

#### 1️⃣ تعريف الكلاس
الكلاس يحتوي على متغير `x`، ودالة `Print()` لطباعة القيمة، وباني (Constructor) لإعطاء قيمة لـ `x`.

#### 2️⃣ إنشاء الفكتور
```cpp
vector<clsA> v1;
```
أنشأنا فكتور يمكنه تخزين كائنات من نوع `clsA`.

#### 3️⃣ إضافة كائنات
```cpp
v1.push_back(clsA(i));
```
يتم إنشاء كائن جديد وإضافته للفكتور في نهاية القائمة.

#### 4️⃣ الطباعة
```cpp
v1[i].Print();
```
نمر على كل كائن ونطبع قيمته.

📤 الناتج:
```
The value of x=0
The value of x=1
The value of x=2
The value of x=3
The value of x=4
```

---

### ⚖️ مقارنة سريعة

| الدالة | الوظيفة |
|--------|----------|
| `vector<clsA>` | إنشاء قائمة ديناميكية من الكائنات |
| `push_back()` | إضافة كائن جديد إلى نهاية الفكتور |
| `v1[i]` | الوصول إلى كائن معين داخل الفكتور |
| `Print()` | دالة داخل الكلاس لعرض بيانات الكائن |

---

### 💡 الخلاصة
الفكتورات في C++ تسمح لك بتخزين عدد غير محدود من الكائنات بطريقة ديناميكية.  
يمكنك استخدامها لتنظيم البيانات المعقدة بسهولة وتكرارها بكفاءة.

