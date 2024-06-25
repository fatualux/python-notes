# Web Scraping in Python

Web scraping is the process of extracting data from websites. Python provides various libraries to facilitate web scraping, such as `BeautifulSoup`, `requests`, and `Selenium`.

![Web Scraping](../../static/images/web_scraping.png)

### Key Libraries

1. **requests**:
   - Used to send HTTP requests.
   - Install:
     ```bash
         pip install requests
     ```

2. **BeautifulSoup**:
   - Used for parsing HTML and XML documents.
   - Install:
     ```bash
         pip install beautifulsoup4
     ```

3. **Selenium**:
   - Used for automating web browser interaction.
   - Install:
     ```bash
         pip install selenium
     ```

### Basic Workflow

1. Send an HTTP request to the target website.
2. Parse the HTML content.
3. Extract the required data.
4. (Optional) Interact with JavaScript elements using Selenium.

### Example: Scraping Static Web Pages

1. **Fetching HTML Content**:
    ```python
        import requests

        url = 'https://example.com'
        response = requests.get(url)

        if response.status_code == 200:
            html_content = response.text
        else:
            print('Failed to retrieve the webpage', response.status_code)
    ```

2. **Parsing HTML Content with BeautifulSoup**:
    ```python
        from bs4 import BeautifulSoup

        soup = BeautifulSoup(html_content, 'html.parser')
        title = soup.title.string
        print('Page Title:', title)

        # Extracting specific elements
        paragraphs = soup.find_all('p')
        for p in paragraphs:
            print(p.text)
    ```

### Example: Scraping Dynamic Web Pages with Selenium

1. **Setting Up Selenium**:
    ```python
        from selenium import webdriver

        driver = webdriver.Chrome(executable_path='/path/to/chromedriver')
        driver.get('https://example.com')
    ```

2. **Interacting with Web Elements**:
    ```python
        search_box = driver.find_element_by_name('q')
        search_box.send_keys('Python')
        search_box.submit()

        results = driver.find_elements_by_css_selector('h3')
        for result in results:
            print(result.text)

        driver.quit()
    ```

### Best Practices

1. **Respect Robots.txt**:
   - Always check the `robots.txt` file of the website to understand the allowed scraping policies.

2. **Rate Limiting**:
   - Implement delays between requests to avoid overloading the server.
    ```python
        import time

        time.sleep(1)  # Sleep for 1 second
    ```

3. **Error Handling**:
   - Handle HTTP errors and exceptions gracefully.
    ```python
        try:
            response = requests.get(url)
            response.raise_for_status()
        except requests.exceptions.HTTPError as err:
            print(f'HTTP error occurred: {err}')
        except Exception as err:
            print(f'An error occurred: {err}')
    ```

