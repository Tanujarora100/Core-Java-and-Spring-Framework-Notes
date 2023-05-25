# How to Achieve Inheritance in Java:
- Using the **Extends** Keyword in Java.
- We can increase the **visibility of super methods but cannot reduce** it.
- If we make a same method in child class then child class method overrides the same method of parent class.
    -   We **cannot change the return type or add parameters** or signature, we can change it's implementation. 
    -  We need to **make a new method if we want to change the return type of a super class method**.
- We Cannot inherit the Constructor as it has the same class name so we do not inherit the constructors.
- Parent class Constructor gets called first-->Child Class constructor called.
- We can use the reference of a parent class but create an object of child class.
    - All the properties of the parent class are already inherited by the object as the constructor of the parent class is called before the object is being created so all the properties are given to the object of the child class.


# Generalization and Specialization:
- These common entities can be then put into a parent class which in our case is a Message Class.  This phenomenon is called  Generalization.
- Now most of the common entities are pulled out from each of these classes, but they want to do at least one thing differently ( behaviour ) and/or add more data. 
    - This phenomenon is called  Specialization.
    - That way each child class (representing one message type) remains independent of other child classes.
