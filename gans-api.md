# Gans API Learning Exercise

## Prompt A

**Prompt:**
I am having a difficult time understanding APIs and why it is important to know how to develop them in today's world. Please provide a tutorial with examples to help me better understand.

**Response:**

### What is an API?
An API (Application Programming Interface) is a set of rules that allows different software applications to communicate with each other. It acts as a bridge between different applications, allowing them to share data and functionality.

### Why are APIs Important?
- **Integration:** APIs allow different systems to integrate, allowing businesses to use third-party services.
- **Automation:** They enable automated workflows between applications.
- **Scalability:** APIs provide a way for developers to add new features without overhauling the existing codebase.

### Example of an API
Suppose you are developing a weather application. Instead of building a weather data source, you can use a public API like OpenWeatherMap:

```python
import requests

response = requests.get('https://api.openweathermap.org/data/2.5/weather?q=Raleigh&appid=your_api_key')
print(response.json())
```

## Prompt B

**Prompt:**
If I was designing the above web application to allow for additional features and working with a collaborative team, how would I structure the above to minimize version control conflict?

**Response:**

### Best Practices for Collaborative Development
1. **Use GitHub and Branching:**
   - Create a main branch for production-ready code.
   - Use feature branches for each new functionality.
2. **API Documentation:**
   - Use Swagger or Postman for clear API documentation.
3. **Modular Code:**
   - Separate code into modules (e.g., routes, services, models).

### Example Folder Structure
```
project_root
│
├── app
│   ├── models
│   ├── routes
│   ├── services
│
├── tests
├── requirements.txt
├── app.py
```

## Prompt C

**Prompt:**
How would I add a public API to the above code?

**Response:**

### Adding a Public API
Use Flask to integrate a public API. Example:

```python
from flask import Flask, jsonify
import requests

app = Flask(__name__)

@app.route('/weather', methods=['GET'])
def get_weather():
    response = requests.get('https://api.openweathermap.org/data/2.5/weather?q=Raleigh&appid=your_api_key')
    return jsonify(response.json())

if __name__ == '__main__':
    app.run(debug=True)
```

## Prompt D

**Prompt:**
I do not want to make this application public; what I want is to use an existing free public API and add it to the code.

**Response:**

### Using an Existing API Without Publicizing Your App
To keep your app private, only use the API for internal purposes and do not expose it. Example:

```python
import requests

API_KEY = 'your_api_key'

response = requests.get(f'https://api.openweathermap.org/data/2.5/weather?q=Raleigh&appid={API_KEY}')
print(response.json())
```

### Tips
- Do not expose your API keys in public repositories.
- Use `.env` files to store sensitive information.

## Prompt E

**Prompt:**
Since this is a web application, revise as necessary and add the web components needed if using Flask and Python.

**Response:**

### Full Flask Application

```python
from flask import Flask, render_template, request
import requests

app = Flask(__name__)

@app.route('/', methods=['GET'])
def home():
    city = request.args.get('city', 'Raleigh')
    response = requests.get(f'https://api.openweathermap.org/data/2.5/weather?q={city}&appid=your_api_key')
    weather = response.json()
    return render_template('index.html', weather=weather)

if __name__ == '__main__':
    app.run(debug=True)
```

## Prompt F

**Prompt:**
How can I effectively test and debug an API during development?

**Response:**

### Using Postman for API Testing
Another crucial aspect of working with APIs is testing them to ensure they function as expected. Postman is a popular tool used to test APIs without writing code. Here’s how you can use Postman:

1. **Open Postman** and enter the API endpoint (e.g., `http://localhost:5000/weather`).
2. Select the request type (GET, POST, etc.).
3. Click **Send** to test the API.
4. View the response and ensure it matches the expected output.

Postman helps developers validate their API's functionality before deploying it.

