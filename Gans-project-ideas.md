# Gans-Project-Ideas.md

## Prompt 1

**Prompt:** What are good small projects that would allow me to demonstrate pytest for unit and integration testing, postman, selenium, playwright and robot framework testing. It needs to be able to be modularized so that 3 - 6 people can work on it and minimize having version control conflict using GitHub. The project needs to have at least 3 internal APIs and use a free public one. The selenium needs to be able to test at least 6 of the following in the UI:

- Form Submissions: Test form filling, submissions, and validation messages.  
- Link and Button Clicks: Automate clicking on various links and buttons to ensure they lead to the correct actions or pages.  
- Dropdown Menus: Test interactions with dropdown menus, including selecting various options.  
- Mouse Actions: Simulate mouse actions like clicks, double-clicks, hover, and drag-and-drop.  
- Keyboard Inputs: Test keyboard interactions, including text input and keyboard shortcuts.  
- Layout Testing: Check the layout and positioning of UI components.  
- Page Navigation: Test navigation between different pages or sections of the application.  
- Data Entry and Retrieval: Test CRUD (Create, Read, Update, Delete) operations on data.  
- Data Validation: Ensure the correctness of data processing and output.  
- Error Messages: Test for correct error messages under various error conditions.  
- Handling Exceptions: Ensure the application handles unexpected exceptions gracefully.  

**Response:**
A suitable project idea is a "Task Management System." This system will allow users to create, update, delete, and view tasks. The application will have a user authentication system, a task tracking feature, and an analytics dashboard. 
- **Internal APIs:** User authentication, task management, reporting.
- **External API:** Utilize a public calendar API for scheduling.
- **UI Testing with Selenium:** Form submission, link clicks, dropdowns, keyboard inputs, and CRUD operations.
- **Modularization:**
  - `auth_service`: Handles user authentication
  - `task_service`: Manages task CRUD operations
  - `reporting_service`: Generates reports
  - `frontend`: Flask-based UI
  - `testing`: Includes pytest for unit testing, Selenium, Playwright, and Robot Framework tests.

---

## Prompt 2

**Prompt:** Create a project plan and structure for this.

**Response:**
**Project Plan:**
- **Week 1-2:** Set up GitHub repository, define folder structure, assign team roles.
- **Week 3-4:** Develop authentication and task management services.
- **Week 5-6:** Integrate reporting service and external API.
- **Week 7-8:** Develop UI and testing suite.
- **Week 9-10:** Debug, optimize, and finalize project.

**Folder Structure:**
```
project_name/
│── app/
│   ├── auth_service/
│   ├── task_service/
│   ├── reporting_service/
│   ├── frontend/
│── tests/
│── docs/
│── requirements.txt
│── README.md
│── .github/
```

---

## Prompt 3

**Prompt:** Break out the backend more so they can work and use Flask to develop with Python.

**Response:**
- `auth_service`: Flask-based authentication with JWT.
- `task_service`: Flask API to handle task CRUD operations.
- `reporting_service`: Flask API to generate reports and summaries.
- `frontend`: Flask with Jinja2 templates for UI.

---

## Prompt 4

**Prompt:** Revise to complete in 4 sprints with each sprint being two weeks.

**Response:**
- **Sprint 1:** Set up project, create authentication.
- **Sprint 2:** Develop task management API.
- **Sprint 3:** Integrate reporting service.
- **Sprint 4:** UI development, testing, and finalizing.

---

## Prompt 5

**Prompt:** Create a detailed test plan with test cases.

**Response:**
Test plan includes unit, integration, and UI testing with Selenium. Test cases cover form submissions, link/button clicks, dropdowns, mouse actions, keyboard inputs, layout checks, page navigation, CRUD operations, data validation, error handling, and exception management.

---

## Prompt 6

**Prompt:** Recommended strategy for `user_model.py` in Flask.

**Response:**
Use Flask-SQLAlchemy for database models, implement user authentication with JWT, and create validation methods.

---

## Prompt 7

**Prompt:** Recommended strategy for `library/utils.py`.

**Response:**
Develop helper functions for common tasks like password hashing, request validation, and logging.

---

## Prompt 8

**Prompt:** Dependencies between `user_model.py` and `library/utils.py`.

**Response:**
`utils.py` should provide utility functions for `user_model.py`, ensuring modularity and reuse.

---

## Prompt 9

**Prompt:** Mermaid diagram for resolving dependencies.

**Response:**
Generate a diagram showing data flow and dependencies between modules.

---

## Prompt 10

**Prompt:** UI development strategy.

**Response:**
Develop UI with Flask and Jinja2, using Bootstrap for styling and JavaScript for dynamic interactions.

---

## Prompt 11

**Prompt:** Revise project structure for Flask.

**Response:**
Adjust project structure to better fit Flask application conventions.

---

## Prompt 12

**Prompt:** Provide details under `app/`.

**Response:**
Expand `app/` to include `routes.py`, `models.py`, `services/`, and `templates/`.

---

## Prompt 13

**Prompt:** Edge test cases.

**Response:**
Provide test cases covering boundary conditions and unexpected user inputs.

---

## Prompt 14

**Prompt:** Alternative project idea meeting requirements.

**Response:**
A "Movie Review Platform" with APIs for authentication, reviews, and analytics.

---

## Prompt 15

**Prompt:** Pokemon-themed project idea.

**Response:**
A "Pokemon Trading Platform" with APIs for authentication, trading, and inventory management.

---

## Prompt 16

**Prompt:** Open-ended additional project idea.

**Response:**
A "Weather-Based Event Planner" using Flask and external weather APIs.

---

## Reflection

This assignment provided valuable insights into modular architecture and testing strategies for software development. The project emphasized the importance of maintainability, scalability, and testability while also reinforcing collaboration through GitHub version control. AI played a crucial role in structuring the project, offering guidance on API development, UI testing, and sprint planning. 

One challenge faced was ensuring all services were properly modularized to minimize merge conflicts in a team setting. Defining clear responsibilities for each service and aligning unit tests with integration tests helped address this issue. 

Through this exercise, I developed a better appreciation for structured planning and testing, particularly in designing test cases that account for UI and backend dependencies. The assignment strengthened my understanding of Flask-based APIs, test automation tools like Selenium and pytest, and the integration of multiple services in a collaborative environment. 

Overall, this experience has enhanced my ability to develop scalable applications while ensuring thorough testing coverage, preparing me for real-world software development projects.

