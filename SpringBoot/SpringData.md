# SpringData

- Acts as a bridge between database and application
- By Using sprintdata we do not need to write common methods for querying, saving and updating data
- By Extending JPAREPO or MongoRepository we do not need to write methods like getAll(), Save() etc
```java
public interface UserRepository extends MongoRepository<UserEntity, Integer> {

  List<UserEntity> findByUsername(String username);

  @Query("{'posts.content': {$regex: ?0}}")
  List<UserEntity> findUsersWithPostText(String content);

}
```
- By using this custom QUERY parameter we can query the database using this specific query while we use this method.
- In the context of Spring Data and database entities, the *Integer ID* refers to the identifier or primary key of an entity. It is a unique value that identifies a specific record or object in the database table or collection.
    - In most databases, including relational databases like MySQL and NoSQL databases like MongoDB, each record or document typically has a primary key that serves as a unique identifier. The primary key is used to uniquely identify and retrieve individual records.
```java

@Document(collection = "users")
@NoArgsConstructor
public class UserEntity {

  @Id
  public String id;

  public String getId() {
    return id;
  }

  public void setId(String id) {
    this.id = id;
  }

  public String username;

  public String getUsername() {
    return username;
  }

```
- It is important to mark every entity that we need to use with MONGO as a @Document only then spring will be able to Know.
- We are using the @ID on the ID here that means we are using this as primary key.
- That is precisely the advantage of using this pattern. Spring manages the hard work of query generation, connecting and disconnecting to databases and so on so that you can simply invoke one method and continue to focus on the business logic.

## MONGO REPOSITORY
- Spring data Central interface--> Repository
- This Interface is extended by CRUD REPO and LIST CRUD REPO, CRU REPO is generic compared to LIST Crud Repository.
-List CRUD Repository gives a List and CRUD REPO gives an iterable.

- It returns a list to get a unique object we can use pageable or FindFirst
```java
UserEntity findFirstByUsername(String username);
UserEntity findByUsername(String username, Pageable pageable);
```
- Service Layer Code
```java
Pageable pageable = PageRequest.of(0, 1);
UserEntity user = userRepository.findByUsername(username, pageable).getContent().get(0);
```
### ADVANCED QUERY

```java
@Query("{username: ?0}")

List<UserEntity> findUsers(String username);
```
- 0 Denotes the first method parameter to be used to pass this query.
- By using 1, 2 as per our need we can send the parameters to the db for querying it.
- Method naming, as provided by **Spring Data's** query method generation, offers a convenient and convention-based approach to define queries. 
  - It allows you to derive queries based on method names, making it easy to create simple and straightforward queries without explicitly writing the query syntax. 
- With **@Query**, you have full control over the query semantics and can express complex queries. 
  - This approach is beneficial when you require advanced querying capabilities.
  - However, using **@Query** can introduce <u>**tighter coupling**</u> between your application and the underlying technology.
## Mongo template
```java

// ... other code


@Autowired

MongoTemplate mongoTemplate


// ... other code

Query query = new Query();
query.addCriteria(Criteria.where("username").is(username));

// ...

mongoTemplate.findOne(query, User.class);
```
