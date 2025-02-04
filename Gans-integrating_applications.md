# Ian Gans - Integrating Applications Research

## Prompt 1

### **Prompt:**

I am working on a group project that requires integrating at least four internal APIs and one public API using Python and Flask. I want to structure the development to include multiple backend programs, one of which must connect to a database. The frontend will use only static HTML pages. What would be the best approach to designing this system?

### **Response:**

You can create multiple Flask applications that serve as microservices, each exposing their own RESTful APIs. One service can manage user authentication, another can handle a task management system, and a third can serve as an employee directory tied to a database (e.g., PostgreSQL or SQLite). The public API (e.g., a weather API) can be accessed from one of the internal services and exposed to the frontend. Flask's `Blueprints` can help organize routes effectively, and an API gateway can facilitate communication between services.

## Prompt 2

### **Prompt:**

How can I ensure my development follows SOLID principles and best practices while implementing OOP?

### **Response:**

To adhere to SOLID principles:

- **Single Responsibility Principle (SRP):** Each class and function should have a distinct purpose (e.g., separate database access logic from business logic).
- **Open-Closed Principle (OCP):** Design modules that can be extended without modifying existing code, such as using abstract base classes.
- **Liskov Substitution Principle (LSP):** Use inheritance properly by ensuring derived classes can be used interchangeably with their base class.
- **Interface Segregation Principle (ISP):** Keep interfaces minimal so that classes only implement necessary methods.
- **Dependency Inversion Principle (DIP):** Depend on abstractions rather than concrete implementations to promote flexibility and testing.

Using Flask with Blueprints, SQLAlchemy for database ORM, and well-defined service classes will help maintain a clean structure.

## Prompt 3

### **Prompt:**

Can I use Python to call backend APIs?

### **Response:**

Yes, Python provides multiple ways to call backend APIs. The `requests` library is commonly used for making HTTP requests, while Flask itself allows internal communication between APIs via service-to-service calls. Example:

```python
import requests
response = requests.get("http://localhost:5001/api/data")
print(response.json())
```

For more complex applications, using `gRPC` or `GraphQL` can improve efficiency.

## Prompt 4

### **Prompt:**

Would structuring the project this way make collaboration among 3-6 developers easier while reducing version control conflicts?

### **Response:**

Yes, breaking the project into separate services allows different team members to work independently on various components without interfering with each other. Using Git with feature branches, pull requests, and CI/CD pipelines helps manage conflicts and maintain quality. Defining clear API contracts using OpenAPI (Swagger) ensures smooth integration across different services.

## Prompt 5

### **Prompt:**

How can I implement parallel testing using pytest, Selenium, Playwright, Postman, and Robot Framework?

### **Response:**

Parallel testing can be achieved by:

- **pytest**: Using `pytest-xdist` to run unit tests concurrently.
- **Selenium & Playwright**: Running UI tests in headless mode across multiple browsers.
- **Postman**: Using Newman CLI to execute API tests in parallel.
- **Robot Framework**: Configuring parallel execution with `Pabot`.
- **CI/CD**: Leveraging GitHub Actions or Jenkins to distribute test execution.

## Prompt 6

### **Prompt:**

My project will include a task management application, a weather application using a public API, and an employee directory with a database. All will be accessible via the web. Can you provide a detailed project plan for a team of 3-6 members?

### **Response:**

**Project Plan:**

1. **Week 1-2:** Define API contracts, set up Flask applications, database schema, and Git repository.
2. **Week 3-4:** Develop core functionalities for each service.
3. **Week 5-6:** Implement API integration and UI templates.
4. **Week 7:** Conduct unit, integration, and acceptance testing.
5. **Week 8:** Deploy to cloud (e.g., AWS, Heroku) and conduct final review.

## Prompt 7

### **Prompt:**

Can you extend this to include a student lab for teaching pytest, Selenium, Playwright, Postman, and Robot Framework?

### **Response:**

Yes, the lab will cover:

- Writing unit tests in pytest.
- Automating UI interactions using Selenium and Playwright.
- API testing with Postman.
- Creating Robot Framework test cases for end-to-end acceptance testing.

## Prompt 8

### **Prompt:**

What Selenium and Playwright test cases should we include?

### **Response:**

Tests should cover:

- Form submissions and validation
- Clicking buttons and links
- Dropdown selection
- Mouse and keyboard interactions
- Page navigation and layout verification
- CRUD operations and error handling

## Prompt 9

### **Prompt:**

Can you provide user stories for sprint planning and test case development?

### **Response:**

Example user stories:

- "As a user, I can add a task so that I can track my work."
- "As a user, I can view real-time weather updates from the public API."
- "As an admin, I can manage employee records in the directory."

These stories define acceptance criteria for Robot Framework and pytest test cases.

## Prompt 10

### **Prompt:**

Ensure student labs are covered.

### **Response:**

Student labs will be included, providing hands-on experience with testing tools.

## Prompt 11

### **Prompt:**

The application must follow maintainability, scalability, testability, and robustness principles. It should include at least one public API and four internal APIs.

### **Response:**

The application should:

- Use modular architecture for maintainability.
- Scale horizontally by deploying microservices separately.
- Have unit tests for testability.
- Implement exception handling and logging for robustness.

## Reflection

### **Learning Outcomes**

I learned how to design scalable applications with APIs, modular structure, and effective testing strategies. The project reinforced best practices in software development.

### **Challenges Faced**

Ensuring smooth integration of testing tools was challenging. Understanding API dependencies and test automation strategies required extra research.

### **Personal Growth**

This project enhanced my ability to plan, test, and collaborate on large-scale applications. I now appreciate structured testing and design principles even more.

