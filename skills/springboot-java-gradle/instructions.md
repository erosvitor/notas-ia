
# Coding standards and Guidelines

## Dependencies
- Organize the dependencies according to their purpose and should include a comment indicating their purpose.

## External configurations
- Use `application.properties` file.

## Package structure
The purpose of each package.
- config: Holds classes annotated with @Configuration.
- controller: Holds classes annotated with @RestController.
- dao: Holds classes that extend JpaRepository.
- dto: Holds classes to shape custom API request and response data.
- exception: Holds custom domain exceptions and classes utilizing `@RestControllerAdvice`.
- service: Holds classes annotated with `@Service`.
- mapper: Holds classes for object mapping.
- model: Holds classes annotated with `@Entity`.
- util: Holds utilitary classes.

## JPA Mapping
- Create into `model` package.
- Map entities using the `@Entity` annotation.
- Use singular for entity class name.
- Use `LocalDateTime` for timestamps.
- Use `@ManyToOne(fetch = FetchType.LAZY)`.

## Data Access Objects (DAOs)
- Create into `dao` package.
- Use the suffix `DAO` after entity name.

## Services
- Create into `service` package.
- Use the suffix `Service` after entity name.
- Use the pattern `Interface + Impl`
- Use the `@Service` annotation.
- Don't use `@Transaction` annotation.

## Controllers
- Create into `controller` package.
- Use the suffix `Controller` after entity name.
- Use the pattern `Interface + Impl`
- Use mapping annotations only in Impl
- Include `/api/v1/` into `@RequestMapping` annotation
- Endpoints shoud be validate payload using `@Valid`

## Data transference between layers
- Use design pattern DTO
- Use as name `entity name+DTO`

## Object mapping
- Create mapping classes into `mapper` package.
- Use the suffix `Mapper`

## Others guidelines
- Always use `var` for declaration variables and objects when possible.


