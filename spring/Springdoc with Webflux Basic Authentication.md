Allow list for swagger files to be ignored in the spring security authentication configuration: 

- `"/v3/api-docs/**"`
- `"/swagger-ui/**"`
- `"/swagger-ui.html"`

## Authentication configuration with annotation


```java
@Configuration
@OpenAPIDefinition(info = @Info(title = "My API", version = "v1"))
@SecurityScheme(
    name = "basicAuth",
    type = SecuritySchemeType.HTTP,
    scheme = "basic"
)
public class OpenApi30Config {

}
```

---
[How to secure spring boot swagger ui with basic authenticaiton](https://keepgrowing.in/java/springboot/how-to-secure-spring-boot-swagger-ui-with-basic-authentication/) -> document contains the specificacion in Spirngdoc OopenAPI the definition of the Authentication Schema