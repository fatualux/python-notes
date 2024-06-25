
# Requests Library in Python

The `requests` library is one of the most popular libraries in Python for making HTTP requests. It abstracts the complexities of making requests behind a simple API, allowing you to send HTTP requests with minimal effort.

## Installation

To install the `requests` library, you can use pip:

```bash
    pip install requests
```

## Basic Usage

### Sending a GET Request

To send a GET request to a specified URL and fetch the response:

```python
    import requests

    response = requests.get('https://api.example.com/data')
    print(response.status_code)
    print(response.json())
```

### Sending a POST Request

To send a POST request with a payload:

```python
    import requests

    url = 'https://api.example.com/data'
    payload = {'key1': 'value1', 'key2': 'value2'}
    response = requests.post(url, json=payload)
    print(response.status_code)
    print(response.json())
```

## HTTP Methods

### GET

The `GET` method is used to request data from a specified resource.

```python
    response = requests.get('https://api.example.com/data')
    print(response.json())
```

### POST

The `POST` method is used to send data to a server to create/update a resource.

```python
    payload = {'key1': 'value1', 'key2': 'value2'}
    response = requests.post('https://api.example.com/data', json=payload)
    print(response.json())
```

### PUT

The `PUT` method is used to update a current resource with new data.

```python
    payload = {'key1': 'new_value1'}
    response = requests.put('https://api.example.com/data/1', json=payload)
    print(response.json())
```

### DELETE

The `DELETE` method is used to delete a specified resource.

```python
    response = requests.delete('https://api.example.com/data/1')
    print(response.status_code)
```

## Handling Responses

### Checking Status Codes

You can check the status code of a response to determine if the request was successful.

```python
    response = requests.get('https://api.example.com/data')
    if response.status_code == 200:
        print('Success!')
    else:
        print('Failed with status code:', response.status_code)
```

### Accessing JSON Data

If the response contains JSON data, you can access it using the `.json()` method.

```python
    response = requests.get('https://api.example.com/data')
    data = response.json()
    print(data)
```

### Custom Headers

You can send custom headers with your request.

```python
    headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN'}
    response = requests.get('https://api.example.com/data', headers=headers)
    print(response.json())
```

## Timeout and Error Handling

### Setting a Timeout

You can set a timeout for your request to prevent it from hanging indefinitely.

```python
    try:
        response = requests.get('https://api.example.com/data', timeout=5)
        print(response.json())
    except requests.Timeout:
        print('The request timed out')
```

### Handling Exceptions

You can handle different types of exceptions using a try-except block.

```python
    try:
        response = requests.get('https://api.example.com/data')
        response.raise_for_status()  # Raise an HTTPError for bad responses
        print(response.json())
    except requests.HTTPError as err:
        print('HTTP error occurred:', err)
    except requests.RequestException as err:
        print('Error occurred:', err)
```

