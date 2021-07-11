# Read: Class 12 Read: 12 - Spring RESTful Routing & Static Files

## [Baeldung: Spring Request Mapping](https://www.baeldung.com/spring-requestmapping)

- I learned about:

1. @RequestMapping Basics:
   - `@RequestMapping(value = "/ex/foos", method = RequestMethod.GET)`
   - The HTTP method parameter has no default. So, if we don't specify a value, it's going to map to any HTTP request.
1. RequestMapping and HTTP Headers

   - `@RequestMapping(value = "/ex/foos", headers = "key=val", method = GET)`
   - add multiple headers via the headers attribute of @RequestMapping:

   ```java
   @RequestMapping(
   value = "/ex/foos",
   headers = { "key1=val1", "key2=val2" }, method = GET)
   ```

   - We can map a request based on its Accept header via the @RequestMapping headers `headers = "Accept=application/json")`
   - mapping with the headers attribute will automatically be converted to the new produces mechanism starting with Spring 3.1, so the results will be identical.

   ```java
   @RequestMapping(
   value = "/ex/foos",
   method = RequestMethod.GET,
   produces = "application/json"
   )
   ```

   - produces supports multiple values `produces = { "application/json", "application/xml" }`
   - the new produces and consumes mechanisms, which behave differently from most other annotations: When specified at the type level, the method-level annotations do not complement but override the type-level information.

1. @PathVariable

   - ```java
        @RequestMapping(value = "/ex/foos/{id}", method = GET)
        @ResponseBody
        public String getFoosBySimplePathWithPathVariable(
        @PathVariable("id") long id) {
         return "Get a specific Foo with id=" + id;
     }
     ```

1. Multiple @PathVariable
   - @RequestMapping(value = "/ex/foos/{fooid}/bar/{barid}", method = GET)
   - (@PathVariable long fooid, @PathVariable long barid)
1. @PathVariable With Regex
   - EX: restrict the mapping to only accept numerical values for the id: `@RequestMapping(value = "/ex/bars/{numericId:[\\d]+}", method = GET)`
1. RequestMapping With Request Parameters

   - (@RequestParam("id") long id)

1. @RequestMapping — Multiple Paths Mapped to the Same Controller Method

   - `value = { "/ex/advanced/bars", "/ex/advanced/foos" },`

1. @RequestMapping — Multiple HTTP Request Methods to the Same Controller Method

   - method = { RequestMethod.PUT, RequestMethod.POST }

1. @RequestMapping — a Fallback for All Requests

   - @RequestMapping(value = "\*", method = RequestMethod.GET)
   - @RequestMapping(value = "\*", method = { RequestMethod.GET, RequestMethod.POST ... })

1. Ambiguous Mapping Error

   - The ambiguous mapping error occurs when Spring evaluates two or more request mappings to be the same for different controller methods. A request mapping is the same when it has the same HTTP method, URL, parameters, headers, and media type.

1. New Request Mapping Shortcuts
   - @GetMapping
   - @PostMapping
   - @PutMapping
   - @DeleteMapping
   - @PatchMapping

## [Spring guide: Accessing Data with JPA](https://spring.io/guides/gs/accessing-data-jpa/)

- I learned about:

1. The class annotated with @Entity, indicating that it is a JPA entity. (Because no @Table annotation exists, it is assumed that this entity is mapped to a table named of the class name.)
1. The Customer object’s id property is annotated with @Id so that JPA recognizes it as the object’s ID. The id property is also annotated with @GeneratedValue to indicate that the ID should be generated automatically.

### Create Simple Queries

### Create an Application Class

1. @SpringBootApplication is a convenience annotation that adds all of the following:
   - @Configuration: Tags the class as a source of bean definitions for the application context.
   - @EnableAutoConfiguration: Tells Spring Boot to start adding beans based on classpath settings, other beans, and various property settings.
   - @ComponentScan: Tells Spring to look for other components, configurations, and services in the com/example package, letting it find the controllers.

### Build an executable JAR

1. If you use Gradle, you can run the application by using ./gradlew bootRun. Alternatively, you can build the JAR file by using ./gradlew build and then run the JAR file, as follows:

`java -jar build/libs/gs-accessing-data-jpa-0.1.0.jar`

## [Baeldung: Comparing repositories](https://www.baeldung.com/spring-data-repositories)

- I learned about:

1. every repository in Spring Data extends the generic Repository interface, but beyond that, they do each have different functionality.

### Spring Data Repositories

1. the JpaRepository – which extends PagingAndSortingRepository and, in turn, the CrudRepository. Each of these defines its own functionality:
   - CrudRepository provides CRUD functions
   - PagingAndSortingRepository provides methods to do pagination and sort records
   - JpaRepository provides JPA related methods such as flushing the persistence context and delete records in a batch
1. because of this inheritance relationship, the JpaRepository contains the full API of CrudRepository and PagingAndSortingRepository.

1. start with a simple Product entity:

```java
@Entity
public class Product {

    @Id
    private long id;
    private String name;

    // getters and setters
}
```

```java
@Repository
public interface ProductRepository extends JpaRepository<Product, Long> {
    Product findByName(String productName);
}
// The Spring Data Repository will auto-generate the implementation based on the name we provided it.
```

### CrudRepository

1. CrudRepository interface:

```java
public interface CrudRepository<T, ID extends Serializable>
  extends Repository<T, ID> {

    <S extends T> S save(S entity);

    T findOne(ID primaryKey);

    Iterable<T> findAll();

    Long count();

    void delete(T entity);

    boolean exists(ID primaryKey);
}
```

1. CRUD functionality:

   - save(…) – save an Iterable of entities. Here, we can pass multiple objects to save them in a batch
   - findOne(…) – get a single entity based on passed primary key value
   - findAll() – get an Iterable of all available entities in database
   - count() – return the count of total entities in a table
   - delete(…) – delete an entity based on the passed object
   - exists(…) – verify if an entity exists based on the passed primary key value

### PagingAndSortingRepository

```java
public interface PagingAndSortingRepository<T, ID extends Serializable>
  extends CrudRepository<T, ID> {

    Iterable<T> findAll(Sort sort);

    Page<T> findAll(Pageable pageable);
}
```

1. This interface provides a method findAll(Pageable pageable), which is the key to implementing Pagination.

1. When using Pageable, we create a Pageable object with certain properties and we've to specify at least:

   - Page size
   - Current page number
   - Sorting

### JpaRepository

```java
public interface JpaRepository<T, ID extends Serializable> extends
  PagingAndSortingRepository<T, ID> {

    List<T> findAll();

    List<T> findAll(Sort sort);

    List<T> save(Iterable<? extends T> entities);

    void flush();

    T saveAndFlush(T entity);

    void deleteInBatch(Iterable<T> entities);
}
```

1. methods in brief:

   - findAll() – get a List of all available entities in database
   - findAll(…) – get a List of all available entities and sort them using the provided condition
   - save(…) – save an Iterable of entities. Here, we can pass multiple objects to save them in a batch
   - flush() – flush all pending task to the database
   - saveAndFlush(…) – save the entity and flush changes immediately
   - deleteInBatch(…) – delete an Iterable of entities. Here, we can pass multiple objects to delete them in a batch

### Downsides of Spring Data Repositories

1. we couple our code to the library and to its specific abstractions, such as `Page` or `Pageable`; that's of course not unique to this library – but we do have to be careful not to expose these internal implementation details
1. by extending e.g. CrudRepository, we expose a complete set of persistence method at once. This is probably fine in most circumstances as well but we might run into situations where we'd like to gain more fine-grained control over the methods exposed, e.g. to create a ReadOnlyRepository that doesn't include the save(…) and delete(…) methods of CrudRepository
