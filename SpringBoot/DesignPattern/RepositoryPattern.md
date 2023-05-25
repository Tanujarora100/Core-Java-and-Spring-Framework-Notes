# REPOSITORY PATTERN

- Intemediary between business logic and data access layer.
- Abstract the implementation of how the database is storing the data and how it is retrieved.
- By Defining a set of contracts that represent the operations that can be performed such as CRUD operations

## Benefits of Repository Pattern:
- **Abstraction**: No Knowledge of data storage mechanism-> Testing Easier.
- **Single Responsibility**: Each Class for separate entity
- **Testability**: Easier Mocking
- **Flexibility**: Loose Coupling-> Can change the underlying data storage technology.
- Keeps the domain objects (representing business entities) **persistence ignorant**.
    - objects are not burdened with the responsibility of knowing how to store or retrieve themselves from the data storage.

## Difference in DAO and Repository Layer: 
### Repository Layer:
- Repository Layer is of specific type of objects, usually handle one type of object like appleRepo.Save()
- Saves the data in the same table in database.

### DAO:
- It is a finder class to find data and store data.
- It is not restricted to only one datatype and can find and store different types of objects.
```java
Collection<Permission> findPermissionsForUser(String userId)
User findUser(String userId)
Collection<User> findUsersForPermission(Permission permission)
```
- It is not limited to a specific table or entity type, allowing you to have a UserDao that deals with user-related operations like finding user permissions, retrieving user details.

## Overall Difference:
- The Repository pattern is more specialized and restricts its operations to a specific type of object
- DAO pattern is more **generic and adaptable to handle various types of objects** and their relationships.
- The Repository pattern provides a **higher-level abstraction** that focuses on domain objects rather than the specific data access mechanism.