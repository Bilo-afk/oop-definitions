# 🧬 Inheritance Types \| أنواع الوراثة

## English Explanation 🇬🇧

Inheritance is one of the most important concepts in Object-Oriented
Programming (OOP).\
It allows a class (child/derived class) to acquire properties and
behaviors (methods) of another class (parent/base class).

### Types of Inheritance in C++:

1.  **Single Inheritance**
    -   A derived class inherits from a single base class.

    ``` cpp
    class Parent { };
    class Child : public Parent { };
    ```
2.  **Multiple Inheritance**
    -   A derived class inherits from more than one base class.

    ``` cpp
    class A { };
    class B { };
    class C : public A, public B { };
    ```
3.  **Multilevel Inheritance**
    -   A chain of inheritance where a class is derived from another
        derived class.

    ``` cpp
    class A { };
    class B : public A { };
    class C : public B { };
    ```
4.  **Hierarchical Inheritance**
    -   Multiple derived classes inherit from the same base class.

    ``` cpp
    class A { };
    class B : public A { };
    class C : public A { };
    ```
5.  **Hybrid Inheritance**
    -   A combination of two or more types of inheritance.

    ``` cpp
    class A { };
    class B : public A { };
    class C { };
    class D : public B, public C { };
    ```

------------------------------------------------------------------------

## الشرح بالعربية 🇸🇦

الوراثة (Inheritance) هي أحد أهم مفاهيم **البرمجة كائنية التوجه
(OOP)**.\
تسمح للـ **كلاس الابن (Child/Derived Class)** أن يرث الخصائص والدوال من
**كلاس الأب (Parent/Base Class)**.

### أنواع الوراثة في ++C:

1.  **الوراثة المفردة (Single Inheritance)**
    -   كلاس يرث من كلاس واحد فقط.

    ``` cpp
    class Parent { };
    class Child : public Parent { };
    ```
2.  **الوراثة المتعددة (Multiple Inheritance)**
    -   كلاس يرث من أكثر من كلاس واحد.

    ``` cpp
    class A { };
    class B { };
    class C : public A, public B { };
    ```
3.  **الوراثة متعددة المستويات (Multilevel Inheritance)**
    -   سلسلة وراثة حيث يرث كلاس من كلاس مشتق آخر.

    ``` cpp
    class A { };
    class B : public A { };
    class C : public B { };
    ```
4.  **الوراثة الهرمية (Hierarchical Inheritance)**
    -   عدة كلاسات ترث من نفس الكلاس الأب.

    ``` cpp
    class A { };
    class B : public A { };
    class C : public A { };
    ```
5.  **الوراثة الهجينة (Hybrid Inheritance)**
    -   مزيج من أكثر من نوع وراثة.

    ``` cpp
    class A { };
    class B : public A { };
    class C { };
    class D : public B, public C { };
    ```

------------------------------------------------------------------------

✅ This README provides a **clear explanation** of inheritance types in
**both English and Arabic**, with **C++ examples**.
