
# 🔄 Passing Objects to Functions in C++ | تمرير الكائنات إلى الدوال في البرمجة الكائنية

---

## 🇬🇧 English Explanation

### 💡 Concept Overview
In **C++**, objects can be passed to functions just like other data types (such as `int`, `string`, or `bool`).  
When passing objects to functions, there are two main ways to do it:

| Method | Description |
|---------|--------------|
| **Pass by Value** | The function receives a **copy** of the object — changes inside the function do **not** affect the original. |
| **Pass by Reference** | The function receives a **reference** (address) to the original object — changes **do** affect the original. |

---

### 🧩 Real-Life Analogy

Imagine you have an **ID card**:

- 🧾 **By Value:** You give your friend a **photocopy** of your ID — if he writes on it, your real ID remains unchanged.  
- 🪪 **By Reference:** You give your friend your **original ID** — if he writes on it, your ID changes permanently.

That’s exactly the difference between **By Value** and **By Reference**.

---

### ⚙️ Example Code Explained

```cpp
// ProgrammingAdvices.com
// Mohammed Abu-Hadhoud
#include<iostream>
using namespace std;

class clsA {
public:
    int x;
    void Print() {
        cout << "The value of x=" << x << endl;
    }
};

// Object passed by value → Original will NOT change
void Fun1(clsA A1) {
    A1.x = 100;
}

// Object passed by reference → Original WILL change
void Fun2(clsA &A1) {
    A1.x = 200;
}

int main() {
    clsA A1;
    A1.x = 50;

    cout << "\nA.x before calling function1:\n";
    A1.Print();

    // Pass by Value (copy)
    Fun1(A1);
    cout << "\nA.x after calling function1 byval:\n";
    A1.Print();

    // Pass by Reference (original)
    Fun2(A1);
    cout << "\nA.x after calling function2 byref:\n";
    A1.Print();

    system("pause>0");
}
```

---

### 🧠 Step-by-Step Explanation

#### 1️⃣ Initial Value
```cpp
A1.x = 50;
```
The variable `x` starts with **50**.

#### 2️⃣ Pass by Value → `Fun1(A1)`
- A **copy** of `A1` is created.  
- Inside `Fun1`, the copied `x` becomes **100**, but the **original A1.x** remains **50**.  

📤 Output:
```
A.x after calling function1 byval:
The value of x=50
```

#### 3️⃣ Pass by Reference → `Fun2(A1)`
- The function gets the **real A1**, not a copy.  
- Inside `Fun2`, setting `A1.x = 200` changes the **original object**.  

📤 Output:
```
A.x after calling function2 byref:
The value of x=200
```

---

### ⚖️ Comparison Summary

| Method | What is Passed | Does it Affect Original? | Memory Usage |
|---------|----------------|--------------------------|---------------|
| **By Value** | Copy of the object | ❌ No | More memory |
| **By Reference** | Reference (address) | ✅ Yes | Less memory |

---

### 💡 Conclusion
Passing objects **By Value** is safe when you don’t want to modify the original.  
Passing them **By Reference** is useful when you need to **change or update** the original object.

---

## 🇸🇦 الشرح بالعربية

### 💡 المفهوم العام
في لغة **C++** يمكن تمرير الكائنات إلى الدوال تمامًا مثل المتغيرات العادية (`int`, `string`, `bool` …).  
وهناك طريقتان أساسيتان لتمرير الكائن:

| الطريقة | الشرح |
|----------|--------|
| **By Value (بالقيمة)** | يتم إرسال **نسخة** من الكائن، وأي تعديل داخل الدالة لا يؤثر على الأصل. |
| **By Reference (بالمرجع)** | يتم إرسال **العنوان الحقيقي للكائن**، وأي تعديل يؤثر على الأصل مباشرة. |

---

### 🧩 تشبيه واقعي

تخيل أنك تمتلك **بطاقة هوية**:

- 🧾 **By Value:** تعطي صديقك **صورة من البطاقة**، إذا كتب عليها شيء فلن تتأثر بطاقتك الأصلية.  
- 🪪 **By Reference:** تعطيه **البطاقة الأصلية**، فإذا كتب عليها شيء فالتغيير سيكون دائمًا.

هذا هو الفرق بين التمرير بالقيمة والتمرير بالمرجع.

---

### ⚙️ الكود مع الشرح

```cpp
#include<iostream>
using namespace std;

class clsA {
public:
    int x;
    void Print() {
        cout << "The value of x=" << x << endl;
    }
};

// تمرير الكائن بالقيمة → لا يؤثر على الأصل
void Fun1(clsA A1) {
    A1.x = 100;
}

// تمرير الكائن بالمرجع → يؤثر على الأصل
void Fun2(clsA &A1) {
    A1.x = 200;
}

int main() {
    clsA A1;
    A1.x = 50;

    cout << "\nA.x before calling function1:\n";
    A1.Print();

    // تمرير بالقيمة (نسخة)
    Fun1(A1);
    cout << "\nA.x after calling function1 byval:\n";
    A1.Print();

    // تمرير بالمرجع (الأصل)
    Fun2(A1);
    cout << "\nA.x after calling function2 byref:\n";
    A1.Print();

    system("pause>0");
}
```

---

### 🧠 الشرح خطوة بخطوة

#### 🔹 قبل استدعاء أي دالة:
`x` = 50

#### 🔹 عند استدعاء `Fun1(A1)`:
تم إرسال **نسخة من الكائن**.  
الدالة عدلت النسخة فقط (`x=100`)، لكن الكائن الأصلي بقي كما هو (`x=50`).

📤 الناتج:
```
The value of x=50
```

#### 🔹 عند استدعاء `Fun2(A1)`:
تم إرسال **العنوان الحقيقي للكائن**، لذلك التعديل (`x=200`) أثّر على الأصل مباشرة.

📤 الناتج:
```
The value of x=200
```

---

### ⚖️ مقارنة سريعة

| الطريقة | ما يتم تمريره | هل يؤثر على الأصل؟ | استهلاك الذاكرة |
|----------|----------------|----------------------|------------------|
| **By Value (بالقيمة)** | نسخة من الكائن | ❌ لا | أعلى |
| **By Reference (بالمرجع)** | العنوان الحقيقي | ✅ نعم | أقل |

---

### 💡 الخلاصة
- ✅ استخدم **By Value** عندما لا تريد تعديل الأصل.  
- ✅ استخدم **By Reference** عندما ترغب بتحديث الكائن مباشرة.  
- 🧠 تذكّر: الكائنات تُعامل في C++ مثل أي نوع بيانات آخر، يمكن تمريرها بحرية بين الدوال.

