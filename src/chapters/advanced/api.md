# APIs

APIs (Application Programming Interfaces) are sets of rules that allow software applications to communicate with each other. They define the methods and data formats that applications use to request and exchange information. APIs are crucial for integrating different systems and enabling them to work together seamlessly.

![APIs](../../static/images/api.png)

### Key Concepts

1. **API Endpoint**:
   - An endpoint is a specific URL where an API can be accessed by a client application. It represents a resource or a collection of resources.
   - Example: `https://api.example.com/v1/users`

2. **HTTP Methods**:
   - APIs typically use HTTP methods to perform actions on resources.
     - **GET**: Retrieve information.
     - **POST**: Create a new resource.
     - **PUT**: Update an existing resource.
     - **DELETE**: Remove a resource.

3. **Request and Response**:
   - **Request**: A client sends a request to an API endpoint, specifying the desired action.
   - **Response**: The API server processes the request and sends back a response, usually in JSON format.

### Interacting with APIs in Python

Python provides several libraries to interact with APIs, with `requests` being one of the most popular.

- **Install `requests`**:
    ```python
    pip install requests
    ```

### Making a GET Request

- Example: Fetching data from a public API.
    ```python
    import requests

    response = requests.get('https://api.example.com/v1/users')
    if response.status_code == 200:
        data = response.json()
        print(data)
    else:
        print('Failed to retrieve data', response.status_code)
    ```

### Making a POST Request

- Example: Sending data to an API to create a new resource.
    ```python
    import requests

    url = 'https://api.example.com/v1/users'
    payload = {'name': 'Alice', 'email': 'alice@example.com'}
    response = requests.post(url, json=payload)

    if response.status_code == 201:
        print('User created successfully')
    else:
        print('Failed to create user', response.status_code)
    ```

### Adding Headers

- Example: Including headers in a request.
    ```python
    import requests

    url = 'https://api.example.com/v1/users'
    headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN'}
    response = requests.get(url, headers=headers)

    if response.status_code == 200:
        data = response.json()
        print(data)
    else:
        print('Failed to retrieve data', response.status_code)
    ```

### Handling Errors

- Example: Implementing error handling for requests.
    ```python
    import requests

    def fetch_user(user_id):
        url = f'https://api.example.com/v1/users/{user_id}'
        try:
            response = requests.get(url)
            response.raise_for_status()
            return response.json()
        except requests.exceptions.HTTPError as http_err:
            print(f'HTTP error occurred: {http_err}')
        except Exception as err:
            print(f'Other error occurred: {err}')

    user_data = fetch_user(1)
    if user_data:
        print(user_data)
    ```

### Common Use Cases

1. **Fetching Weather Data**:
    ```python
    import requests

    api_key = 'YOUR_API_KEY'
    city = 'London'
    url = f'http://api.openweathermap.org/data/2.5/weather?q={city}&appid={api_key}'

    response = requests.get(url)
    if response.status_code == 200:
        weather_data = response.json()
        print(weather_data)
    else:
        print('Failed to retrieve weather data', response.status_code)
    ```

2. **Interacting with a REST API**:
    ```python
    import requests

    base_url = 'https://jsonplaceholder.typicode.com'

    def get_posts():
        response = requests.get(f'{base_url}/posts')
        return response.json()

    def create_post(title, body, user_id):
        payload = {'title': title, 'body': body, 'userId': user_id}
        response = requests.post(f'{base_url}/posts', json=payload)
        return response.json()

    posts = get_posts()
    print(posts)

    new_post = create_post('New Post', 'This is a new post.', 1)
    print(new_post)
    ```

