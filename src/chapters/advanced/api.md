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

