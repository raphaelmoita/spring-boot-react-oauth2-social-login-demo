### SpringSocialApplication

- Spring bootstrap class

### AppProperties

- loads properties from ```/resources/application.yml```
- it is ```@Autowired``` in many services

### SecurityConfig

- extends ```WebSecurityConfigurerAdapter```
- it override ```void configure(AuthenticationManagerBuilder authenticationManagerBuilder)```. It uses a ```CustomUserDetailsService``` (implements UserDetailsService) to load user information from database. Also set a password encoder as ```new BCryptPasswordEncoder()```
- it overrides ```void configure(HttpSecurity http)``` and set the following values:
  - cors(): enable CORS - https://spring.io/guides/gs/rest-service-cors/ 
  - sessionManagement().sessionCreationPolicy(SessionCreationPolicy.STATELESS) - https://www.baeldung.com/spring-security-session
  - 
### WebMvcConfig
  
  - implements ```WebMvcConfigurer```
  - it overrrides ```void addCorsMappings(CorsRegistry registry) {``` and set all allowed stuff accessible bt CORS
