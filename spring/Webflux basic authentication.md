Uses [[http/Basic Authentication]] standard

## required dependencies

Include in the `pom.xml`

```xml
<dependency>
	<groupId>org.springframework.boot</groupId>
	<artifactId>spring-boot-starter-security</artifactId>
</dependency>
<dependency>
	<groupId>org.springframework.security</groupId>
	<artifactId>spring-security-config</artifactId>
</dependency>
```

## Configuration

Define:
- Activate `@EnableWebFluxSecurity`
- `SecurityWebFilterChain`
- `MapReactiveUserDetailsService`

```java
@Configuration
@EnableWebFluxSecurity
public class SecurityConfig {

    @Bean
    public SecurityWebFilterChain securityFilterChain(ServerHttpSecurity http) {
        return http
                .csrf().disable()
                .authorizeExchange()
                .pathMatchers("/").permitAll()
                .anyExchange().authenticated()
                .and()
                .httpBasic()
                .and()
                .formLogin().disable()
                .build();
    }

    @Bean
    public MapReactiveUserDetailsService userDetailsService() {
        UserDetails user = User.builder()
                .username("user")
                .password("{noop}user")
                .roles("USER")
                .build();
        UserDetails admin = User.builder()
                .username("admin")
                .password("{noop}admin")
                .roles("ADMIN")
                .build();
        return new MapReactiveUserDetailsService(user, admin);
    }

}
```

## Other findings

- Users needs to have defined roles, otherwise a Null Pointer exception will be thrown by Spring
- Authorization base on roles can be used to filter out users per method

Referenced article contains more information about:
- Inject users from MongoDB
- Central Authentication/Authorization central exception handler

References:
- [spring webflux rest authentication](https://www.devglan.com/spring-cloud/spring-webflux-rest-authentication)
- [Spring Security 5 for Reactive applications](https://www.baeldung.com/spring-security-5-reactive)