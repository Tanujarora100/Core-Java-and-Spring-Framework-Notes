# Abstract Classes:
- Objects cannot be created from abstract classes because an abstract class is meant to be a base class that provides a common interface and implementation for its subclasses. 
- An abstract class -->serves as a blueprint
cannot be instantiated→compile-time error.
## Why need an Abstract Method?
- define a common interface for a group of related classes.
- Have abstract methods and concrete methods, which are methods with a body.
- allows for creating a hierarchy of classes where subclasses can inherit properties still providing their own unique promote code reuse and maintain consistency in a codebase.
## Why do Abstract Classes have a Constructor?
- An abstract class can have a constructor because it is still a concrete class, meaning that it can be instantiated
- although it cannot be instantiated directly. 
- The constructor of an abstract class is called when an instance of a concrete subclass is created.
• The purpose of the constructor in an abstract class is to provide a way to initialize the state of the object when it is created. This can be useful for setting default values for instance variables or performing other tasks that need to be done every time an instance of a concrete subclass is created.
• Additionally, having a constructor in an abstract class can provide a convenient way to enforce a common initialization process across all subclasses. This can be especially useful when you have multiple subclasses that all need to follow the same initialization process.
• It is important to note that a constructor in an abstract class does not have to be public. It can be protected, private, or package-private, depending on the visibility requirements of the class and its subclasses.
## Can Abstract Classes be Empty?
• Yes, an abstract class can be empty, meaning it can have no methods or fields. An empty abstract class can still be useful in certain situations, such as when you want to create a common base class for a group of related classes but don't need to add any functionality to the base class yet.
• In such cases, you can create an abstract class and define the common interface for the group of related classes, and then provide concrete implementations in the subclasses. This can help enforce a common interface across the subclasses, making it easier to maintain and understand the codebase.
• It is important to note that an abstract class that is empty, except for its constructor, is generally not a good practice. This can make the code more difficult to understand and maintain, as it is not clear what the purpose of the abstract class is. It is usually better to provide a meaningful implementation in an abstract class, or to use an interface if no implementation is needed.
## Why Abstract Methods Cannot be Private?
• Abstract methods cannot be declared as private because the purpose of an abstract method is to be implemented in the concrete subclasses, not just in the abstract class.
• Private methods are only accessible within the same class, so declaring an abstract method as private would make it inaccessible to the concrete subclasses, defeating the purpose of an abstract method.
## Why Abstract Method cannot be FINAL?
• No, an abstract method cannot be declared as final. The final keyword is used to prevent subclasses from overriding a method, but an abstract method is specifically designed to be overridden in concrete subclasses.
## Why Abstract Methods be Static?
• No, an abstract method cannot be declared as static. The static keyword is used to indicate that a method belongs to a class and not to an instance of the class.
• An abstract method is meant to be overridden in concrete subclasses and provides a common interface for those subclasses. The purpose of an abstract method is to define a method signature that must be implemented by concrete subclasses, and the implementation is determined by the specific instance of the concrete subclass.
• Since a static method belongs to a class and not to an instance of the class, it cannot be overridden in concrete subclasses, and therefore cannot provide a way to enforce a common interface. Additionally, static methods cannot be overridden because they are bound to the class and not to an instance of the class, so the implementation of a static method cannot be changed by subclasses.
