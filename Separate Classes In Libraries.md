
# 🧱 Separate Classes in Libraries in C++ | فصل الكلاسات في مكتبات مستقلة

---

## 🇬🇧 English Explanation

### 💡 What Does "Separate Classes in Libraries" Mean?

In **C++**, large projects are often split into **multiple files** or **libraries** to make the code more **modular**, **organized**, and **maintainable**.  
Each **class** is placed in its own **header (.h)** and **source (.cpp)** file, or even compiled into a **library (.lib / .a)**.

> Think of it like building a city: each building (class) has its own design (file), but together they form one complete system.

---

### 🧩 Real-Life Analogy

Imagine a **car factory**:
- One team builds the **engine**.  
- Another works on the **wheels**.  
- Another handles the **body**.  

Each part is built separately, but when combined, they form a complete **car**.  
That’s exactly how **separate classes in libraries** work in C++.

---

### ⚙️ Example 1: Separate Class Files

#### 📁 Project Structure
```
Car.h
Car.cpp
Engine.h
Engine.cpp
main.cpp
```

#### 🧱 Car.h
```cpp
#ifndef CAR_H
#define CAR_H
#include "Engine.h"
class Car {
private:
    Engine engine;
public:
    void start();
};
#endif
```

#### ⚙️ Car.cpp
```cpp
#include "Car.h"
#include <iostream>
using namespace std;

void Car::start() {
    cout << "Starting the car..." << endl;
    engine.run();
}
```

#### ⚙️ Engine.h
```cpp
#ifndef ENGINE_H
#define ENGINE_H
class Engine {
public:
    void run();
};
#endif
```

#### ⚙️ Engine.cpp
```cpp
#include "Engine.h"
#include <iostream>
using namespace std;

void Engine::run() {
    cout << "Engine is running smoothly!" << endl;
}
```

#### 🧩 main.cpp
```cpp
#include "Car.h"

int main() {
    Car myCar;
    myCar.start();
    return 0;
}
```

### 🧠 Explanation

- Each class (`Car`, `Engine`) is **separated into its own files**.  
- This improves **readability** and **team collaboration**.  
- The compiler combines everything during **compilation**.  
- You can later turn these files into a **library** (`.lib` or `.a`) and reuse them in other projects.

---

### ⚙️ Example 2: Building a Library

```bash
g++ -c Engine.cpp Car.cpp
ar rcs libvehicle.a Engine.o Car.o
g++ main.cpp -L. -lvehicle -o main.exe
./main.exe
```

This creates a **static library** `libvehicle.a` that can be reused across projects.  
Developers can link it instead of rewriting the same code.

---

### ⚖️ Advantages

| Advantage | Description |
|------------|-------------|
| **Modularity** | Each class can be developed independently |
| **Reusability** | Classes can be reused across projects via libraries |
| **Maintainability** | Easier to debug, fix, or upgrade one class at a time |
| **Team Collaboration** | Multiple developers can work on different files simultaneously |

---

## 🇸🇦 الشرح بالعربية

### 💡 ما معنى فصل الكلاسات في مكتبات مستقلة؟

في لغة C++، عندما يكبر المشروع، من الأفضل **تقسيم الكود إلى ملفات متعددة** بحيث يحتوي كل كلاس على ملفه الخاص.  
يمكن أيضًا تحويل هذه الملفات إلى **مكتبات (Libraries)** لاستخدامها في مشاريع أخرى.

> تخيل أنك تبني مدينة: كل مبنى (كلاس) له مخططه الخاص، لكن جميعها تشكل نظامًا واحدًا متكاملًا.

---

### 🧩 مثال من الحياة الواقعية

تخيل مصنع سيارات:
- قسم المحركات يصنع **Engine**.  
- قسم الهيكل يصنع **Body**.  
- قسم الإلكترونيات يصنع **Dashboard**.  

كل قسم يعمل بشكل مستقل، لكن بالنهاية يجتمع الكل ليُشكّل **سيارة كاملة**.  
وهكذا تعمل فكرة فصل الكلاسات في مكتبات في البرمجة.

---

### ⚙️ المثال الأول: فصل الكلاسات في ملفات مستقلة

#### 📁 هيكل المشروع
```
Car.h
Car.cpp
Engine.h
Engine.cpp
main.cpp
```

#### 🧱 Car.h
```cpp
#ifndef CAR_H
#define CAR_H
#include "Engine.h"
class Car {
private:
    Engine engine;
public:
    void start();
};
#endif
```

#### ⚙️ Car.cpp
```cpp
#include "Car.h"
#include <iostream>
using namespace std;

void Car::start() {
    cout << "تشغيل السيارة..." << endl;
    engine.run();
}
```

#### ⚙️ Engine.h
```cpp
#ifndef ENGINE_H
#define ENGINE_H
class Engine {
public:
    void run();
};
#endif
```

#### ⚙️ Engine.cpp
```cpp
#include "Engine.h"
#include <iostream>
using namespace std;

void Engine::run() {
    cout << "المحرك يعمل بسلاسة!" << endl;
}
```

#### 🧩 main.cpp
```cpp
#include "Car.h"

int main() {
    Car myCar;
    myCar.start();
    return 0;
}
```

### 🧠 الشرح

- كل كلاس (مثل `Car` و `Engine`) له ملف تعريف `.h` وملف تنفيذ `.cpp`.  
- هذا يسهل تنظيم المشروع والعمل الجماعي.  
- أثناء الترجمة، يتم **دمج جميع الملفات تلقائيًا**.  
- يمكن لاحقًا تحويل هذه الملفات إلى **مكتبة** (`.lib` أو `.a`) لاستخدامها في مشاريع أخرى.

---

### ⚙️ المثال الثاني: إنشاء مكتبة

```bash
g++ -c Engine.cpp Car.cpp
ar rcs libvehicle.a Engine.o Car.o
g++ main.cpp -L. -lvehicle -o main.exe
./main.exe
```

هنا قمنا بإنشاء مكتبة ثابتة **libvehicle.a** يمكن ربطها مع أي مشروع آخر دون الحاجة لإعادة كتابة الكود.

---

### ⚖️ المميزات

| الميزة | التوضيح |
|--------|----------|
| **التقسيم (Modularity)** | كل كلاس يتم تطويره بشكل مستقل |
| **إعادة الاستخدام (Reusability)** | يمكن إعادة استخدام الكلاسات في مشاريع أخرى عبر المكتبات |
| **سهولة الصيانة (Maintainability)** | يمكن إصلاح أو تحديث أي كلاس دون التأثير على البقية |
| **العمل الجماعي (Collaboration)** | يمكن لعدة مطورين العمل على أجزاء مختلفة من المشروع في نفس الوقت |

---

💡 **الخلاصة:**  
فصل الكلاسات في ملفات أو مكتبات مستقلة هو أسلوب احترافي في هندسة البرمجيات  
يساعد على بناء مشاريع كبيرة، منظمة، وسهلة التطوير وإعادة الاستخدام.
