
# Environment Variables

Environment variables are used to store configuration settings and other information that applications need to function. They provide a way to separate code from configuration, making applications more flexible and secure.

![Environment Variables](../../static/images/env_variables.png)

### Key Concepts

1. **Environment Variable**:
   - A variable that is set outside the application, typically in the operating system or a configuration file.
   - Example: `API_KEY=12345abcde`

2. **Sensitive Information**:
   - Environment variables are often used to store sensitive information such as API keys, tokens, and database credentials to keep them out of the source code.
   - Example: `DB_PASSWORD=mysecretpassword`

### Using Environment Variables in Python

Python provides several ways to access environment variables, with the `os` module being the most common.

### Setting Environment Variables

- **Setting in the Operating System**:
    ```bash
        export API_KEY=12345abcde
    ```

- **Setting in a `.env` File**:
    Create a `.env` file in your project directory:
    ```bash
        API_KEY=12345abcde
    ```

### Accessing Environment Variables

- **Using `os` Module**:
    ```python
        import os

        api_key = os.getenv('API_KEY')
        print(api_key)
    ```

### Using `python-dotenv` to Load `.env` Files

- **Install `python-dotenv`**:
    ```bash
        pip install python-dotenv
    ```

- **Load Environment Variables from `.env` File**:
    ```python
        from dotenv import load_dotenv
        import os

        load_dotenv()  # Load environment variables from .env file

        api_key = os.getenv('API_KEY')
        print(api_key)
    ```

### Hiding Sensitive Variables

- **Keep `.env` File Out of Version Control**:
    Add `.env` to your `.gitignore` file to prevent it from being committed to version control.
    ```bash
        # .gitignore
        .env
    ```

### Example: Using Environment Variables in a Python Application

1. **Create `.env` File**:
    ```bash
        API_KEY=12345abcde
        DB_PASSWORD=mysecretpassword
    ```

2. **Load and Use Environment Variables**:
    ```python
        from dotenv import load_dotenv
        import os

        load_dotenv()  # Load environment variables from .env file

        api_key = os.getenv('API_KEY')
        db_password = os.getenv('DB_PASSWORD')

        print(f'API Key: {api_key}')
        print(f'Database Password: {db_password}')
    ```

### Common Use Cases

1. **Accessing API Keys**:
    ```python
        import os
        import requests
        from dotenv import load_dotenv

        load_dotenv()  # Load environment variables

        api_key = os.getenv('API_KEY')
        url = f'https://api.example.com/data?api_key={api_key}'

        response = requests.get(url)
        print(response.json())
    ```

2. **Connecting to a Database**:
    ```python
        import os
        import psycopg2
        from dotenv import load_dotenv

        load_dotenv()  # Load environment variables

        db_password = os.getenv('DB_PASSWORD')

        connection = psycopg2.connect(
            database="mydatabase",
            user="myuser",
            password=db_password,
            host="localhost",
            port="5432"
        )

        cursor = connection.cursor()
        cursor.execute("SELECT version();")
        record = cursor.fetchone()
        print(f"You are connected to - {record}\n")

        cursor.close()
        connection.close()
    ```

