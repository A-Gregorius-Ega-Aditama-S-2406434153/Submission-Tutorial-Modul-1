# Submission-Tutorial-Modul-1

### Gregorius Ega Aditama Sudjali
### NPM: 2406434153

## Reflection 1:

```text
You already implemented two new features using Spring Boot. Check again your source code
and evaluate the coding standards that you have learned in this module. Write clean code
principles and secure coding practices that have been applied to your code. If you find any
mistake in your source code, please explain how to improve your code. Please write your
reflection inside the repository's README.md file.
```

## Answer:
```text
I reviewed my source code by following the instruction and evaluated it based on the coding standards from this module, and overall
I think my structure is fairly clean because I separate responsibilities across layers: my `ProductController` focuses
on handling HTTP requests and preparing data for the view, my `ProductService` (interface + implementation) acts as the 
business layer, and my `ProductRepository` manages the data storage. I also apply the clean code principle of 
programming to an interface by having the controller depend on `ProductService` instead of the implementation 
class, which reduces coupling and makes the code easier to test or change later. In addition, 
I use clear, consistent method names such as `create()` and `findAll()` so the intent of each method is easy 
to understand, and I follow Spring conventions by using annotations like `@Controller`,
`@Service`, and `@Repository` to make each component’s role explicit. For secure coding practices, I use `POST` for 
creating products rather than `GET`, which aligns with safe HTTP semantics for state-changing operations, and I use 
the redirect-after-post pattern (`redirect:list`) to prevent duplicate submissions when users refresh the page.
I also avoid risky patterns such as building SQL queries or running commands using user input in these classes, which 
reduces the likelihood of injection-style vulnerabilities at this stage. However, I did find 
a mistake in my code: I named some files incorrectly, which breaks Java conventions and can reduce readability and 
maintainability (for example, in Java the public class name must match the filename exactly). To improve this, I should
rename files so every public class matches its filename (e.g., `ProductServiceImpl.java` must contain `public class
ProductServiceImpl`, and `ProductController.java` must contain `public class ProductController`) and keep 
naming consistent across packages. Beyond naming, I can further improve my code by switching from field
injection (`@Autowired` on fields) to constructor injection for better immutability and testing, adding
input validation (for example using `@Valid` and validation annotations or using a DTO instead of 
binding directly to the entity), and improving the repository API so it returns a `List<Product>` directly 
instead of an `Iterator<Product>` to avoid extra conversion logic in the service layer.
```

