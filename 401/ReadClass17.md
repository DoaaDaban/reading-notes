# Read: Class 17 Read: 17 - Spring Authorization

## [Spring Boot and OAuth2](https://spring.io/guides/tutorials/spring-boot-oauth2/)

### Single Sign On With GitHub

1. create a Spring Boot application
1. create a home page
1. add Spring Security as a dependency. Since you’re wanting to do a "social" login (delegate to GitHub), you should include the Spring Security OAuth 2.0 Client starter
1. configure your app to use GitHub as the authentication provider.
1. Add a New GitHub App
1. Configure application.yml

### What Just Happened?

1. The app, in OAuth 2.0 terms, is a Client Application, and it uses the authorization code grant to obtain an access token from GitHub (the Authorization Server).
1. then uses the access token to ask GitHub for some personal details (only what you permitted it to do), including your login ID and your name.
1. If that process is successful, the app inserts the user details into the Spring Security context so that you are authenticated.

### Add a Welcome Page

1. create a button to go to github login
1. using JQuery send a request to the correct endpoint
1. the endpoint should be like this

   - ```java
       @SpringBootApplication
       @RestController
       public class SocialApplication {

           @GetMapping("/user")
           public Map<String, Object> user(@AuthenticationPrincipal OAuth2User principal) {
               return Collections.singletonMap("name", principal.getAttribute("name"));
           }

           public static void main(String[] args) {
               SpringApplication.run(SocialApplication.class, args);
           }
       }
     ```

1. Making the Home Page Public

### Add a Logout Button

1. On the client, we just need to provide a logout button and some JavaScript to call back to the server to ask for the authentication to be cancelled.
1. The logout() function does a POST to /logout and then clears the dynamic content.
1. Adding a Logout Endpoint

   - ```java
        @Override
        protected void configure(HttpSecurity http) throws Exception {
            // @formatter:off
            http
                // ... existing code here
                .logout(l -> l
                    .logoutSuccessUrl("/").permitAll()
                )
                // ... existing code here
            // @formatter:on
        }
     ```

1. add a filter that creates the cookie. In the `WebSecurityConfigurerAdapter`

   - ```java
        @Override
        protected void configure(HttpSecurity http) throws Exception {
            // @formatter:off
            http
                // ... existing code here
                .csrf(c -> c
                    .csrfTokenRepository(CookieCsrfTokenRepository.withHttpOnlyFalse())
                )
                // ... existing code here
            // @formatter:on
        }
     ```

1. Add the CSRF Token in the Client
   - To make the code a bit simpler, include the js-cookie library
1. Add an Error Page for Unauthenticated Users

### Generating a 401 in the Server

1. the code is dependent on a `WebClient` instance for accessing the GitHub API on behalf of the authenticated user.
1. it loops over the organizations, looking for one that matches "spring-projects"
1. If there is no match, it throws an OAuth2AuthenticationException, and this is picked up by Spring Security and turned in to a 401 response.
1. The `WebClient` has to be created as a bean as well, but that’s trivial because its ingredients are all autowirable by virtue of having used spring-boot-starter-oauth2-client
